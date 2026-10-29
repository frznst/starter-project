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
