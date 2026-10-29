# Log keputusan

Satu entri per keputusan, nomor naik terus (K01, K02, …), tidak pernah dihapus. Cari dengan `grep K07 notes/keputusan.md`.
Wajib dicatat: setiap penyimpangan dari arahan/contoh, pilihan di antara beberapa opsi, dan bug yang mengubah desain.

Dua jenis penyimpangan: **melawan arahan** (butuh alasan kuat dan konfirmasi pemilik) dan **beda dari contoh** (wajar, cukup dijelaskan).
Status: ✅ sesuai arahan · 🔁 beda dari contoh · 🔧 revisi atas keputusan sebelumnya (sebut K lama) · 💬 menunggu/sudah dikonfirmasi

Format:

```text
## K00 — Judul singkat
Tanggal: YYYY-MM-DD · Tag: mandatori|bebas|bonus|improvisasi · Status: ✅|🔁|🔧|💬
Konteks: apa masalahnya (1–2 kalimat)
Keputusan: apa yang dipilih
Alasan: kenapa; opsi lain yang ditolak
Bukti: hasil uji / angka / commit
```

---

## K01 — Waterfall dengan gerbang persetujuan per fase
Tanggal: 2026-10-29 · Tag: bebas · Status: 🔁
Konteks: `CLAUDE.md` meminta irisan tipis ujung ke ujung; pemilik meminta waterfall (problem statement → design → implementation).
Keputusan: tiga fase berurutan, tiap fase menunggu OK pemilik. Di F3 tetap dibangun kasir minimal lebih dulu, baru fitur lain.
Alasan: perintah pemilik; irisan tipis dipertahankan di dalam F3 agar masalah integrasi tetap cepat ketahuan.
Bukti: percakapan 2026-10-29, pemilik menjawab "OK".

## K02 — Semua fase dikerjakan sebagai Claude artifact
Tanggal: 2026-10-29 · Tag: bebas · Status: 🔁
Konteks: rencana awal memakai repo, SQLite, dan Streamlit seperti Rakfilm.
Keputusan: dokumen fase dan aplikasi dibuat sebagai artifact; tidak ada kode di `src/`. Aturan kritis (stok tidak negatif, transaksi atomik) ditegakkan di kode aplikasi, bukan skema database.
Alasan: perintah pemilik; biaya nol. Konsekuensi: tidak ada server, jadi risiko R1 dan R3 dicatat di F1.
Bukti: -

## K03 — Catatan disimpan di repo ini (starter-project), bukan repo baru
Tanggal: 2026-10-29 · Tag: bebas · Status: 🔁
Konteks: usulan awal membuat repo privat `pos-barang` dari template; pemilik memilih repo ini.
Keputusan: `notes/` repo ini menyimpan checkpoint proyek POS agar `/lanjut` bekerja. Perubahan lewat branch + PR (P4).
Alasan: perintah pemilik. Kekurangan: template tercampur data proyek; bila template ingin dipakai ulang, bersihkan `notes/` atau buat repo baru dari template.
Bukti: -

## K04 — Pola kerja mengikuti Rakfilm
Tanggal: 2026-10-29 · Tag: bebas · Status: ✅
Konteks: pemilik meminta cara kerja Guru Besar AI sebagai acuan.
Keputusan: perencanaan sebelum kode, risiko diuji lebih dulu, tiap syarat punya kriteria lulus, aturan kritis di kode, hasil uji berupa angka, catatan diperbarui bersama perubahan.
Alasan: sumber metodologi template ini. Acuan: `/Users/zaza/Projects/purwadhika-capstone-3` (`notes/prinsip-kerja.md`).
Bukti: -

## K05 — F1 disetujui, asumsi A1–A6 disetujui
Tanggal: 2026-10-29 · Tag: bebas · Status: 💬
Konteks: pemilik menjawab "oke stuju" atas artifact F1, tanpa koreksi.
Keputusan: ruang lingkup, FR-01..FR-10, NFR-01..NFR-06 dan A1–A6 berlaku. A6 (jenis toko) = umum, karena tidak ada kebutuhan khusus yang disebut.
Alasan: gerbang waterfall (K01).
Bukti: percakapan 2026-10-29.

## K06 — Desain F2: kunci tulis + pending-lalu-selesai, tanpa PIN
Tanggal: 2026-10-29 · Tag: bebas · Status: ✅
Konteks: database artifact tidak punya transaksi dan penulisan bersifat tulis-terakhir-menang; penyimpanan bersama dipastikan tersedia lewat daftar kapabilitas akun.
Keputusan: stok sebagai field; setiap tulis stok lewat kunci `kunci/kasir`, baca ulang stok, simpan transaksi `pending` dengan stok sebelum/sesudah, set stok absolut, tandai `selesai`; pemulihan saat dibuka. Tanpa PIN (artifact privat, D4). Rincian D1–D8 ada di artifact F2.
Alasan: mencegah stok ganda (R1) dan stok negatif (NFR-02) dengan alat yang ada; opsi buku besar mutasi ditolak (tidak menghilangkan balapan, banyak dokumen).
Bukti: belum terbukti berjalan; diuji pertama di F3 (T-08, T-09).

## K07 — Kunci kasir 4 detik, menunggu sampai kunci habis (menyimpang dari F2)
Tanggal: 2026-10-29 · Tag: bebas · Status: 🔧 (revisi K06)
Konteks: F2 menyebut kunci 10 detik dan satu kali coba ulang. Saat membangun terlihat bahwa kunci tidak punya "lepas", ia habis sendiri; 10 detik membuat tab kedua menunggu terlalu lama, dan satu kali coba ulang pasti gagal.
Keputusan: TTL kunci 4 detik; pemegang yang sama memperpanjang seketika; pemegang lain menunggu sampai `expiresAt` lalu mencoba lagi (maksimal 12 detik, 25–40 detik di uji). Pemulihan transaksi `pending` dijalankan juga di dalam setiap pembayaran.
Alasan: kasir tunggal tidak menunggu sama sekali; konflik antar-tab selesai dalam ±4 detik dan hasilnya tetap "stok cukup" atau "ditolak karena stok".
Bukti: menunggu hasil T-09a dan T-09b di artifact uji risiko.

## K08 — Koreksi klaim: ambang T-07b dan kecepatan pembayaran
Tanggal: 2026-10-29 · Tag: bebas · Status: 🔧 (koreksi atas klaim sendiri)
Konteks: T-07b gagal pada putaran 1 (3149 ms vs ambang 3000 ms), padahal stok benar dan tidak ada tunggu kunci. Ambang 3000 ms saya tentukan tanpa dasar; pembayaran memang ±3 detik (8 perjalanan db berurutan, R5 di F2).
Keputusan: (1) ambang T-07b = 4000 ms, yaitu masa berlaku kunci, karena tujuannya membuktikan pemegang kunci yang sama tidak menunggu kunci habis; (2) kurangi perjalanan: perpanjangan kunci dilewati bila belum setengah masa berlaku tetapi dicek sebelum tiap tulis stok, barang dibaca serentak. Penulisan stok tetap berurutan.
Alasan: akar masalah adalah jumlah perjalanan, bukan logika; urutan simpan dan keamanan pemulihan tidak berubah.
Bukti: putaran 1 di `hasil-uji.md`; putaran 2 menunggu.
