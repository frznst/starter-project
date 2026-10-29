# Prinsip kerja

Diadaptasi dari `notes/prinsip-kerja.md` di repo capstone `reinerrekado/purwadhika-capstone-3` (dibagikan untuk dipakai ulang di repo lain), dengan tambahan aturan hemat token. Dibaca saat mulai proyek atau saat ragu; tidak perlu dibaca tiap sesi (ringkasannya ada di `CLAUDE.md`).

## 1. Prinsip

> **Simple. Structural. Logical. Efficient & effective.** Di atas keempatnya: **impressive.**

| Prinsip | Artinya dalam praktik |
|---|---|
| **Simple** | Pilih opsi paling ringan yang berhasil. Kalau tidak bisa dijelaskan dalam satu kalimat, terlalu rumit. |
| **Structural** | Batas file dan fungsi jelas. UI hanya UI, logika di modul sendiri, satu sumber untuk tiap data. |
| **Logical** | Setiap keputusan punya alasan yang bisa dikatakan keras-keras. Alasan dicatat, bukan diingat. |
| **Efficient & effective** | Hemat uang, token, dan waktu; ukur sebelum memutuskan (hitung biaya dulu; uji 20 item sebelum menjalankan 1.000). |
| **Impressive** | Usaha ekstra ditaruh di tempat yang **terlihat**, bukan di infrastruktur tambahan. |

Aturan yang selalu berlaku:

- **Harus bisa dijelaskan.** Pemilik repo harus mampu menjelaskan setiap langkah dan kode penting. Kode yang tidak bisa dijelaskan adalah beban, seberapa pun bagusnya.
- **Diskusi dulu kalau diminta.** Jelaskan pilihan dan kekurangannya, beri rekomendasi, lalu tunggu. Jangan bertindak.
- **Ikuti bahasa visual dan pola yang sudah ada.** Jangan "memperbaiki" jauh dari desain yang sudah dipilih. Hindari tampilan generik buatan AI.

## 2. Metode kerja (urutannya)

1. **Pahami syarat dulu.** Tulis syarat wajib, batas waktu, dan hal yang tidak boleh diganti. Cek setiap pilihan terhadap daftar itu.
2. **Irisan tipis dari ujung ke ujung.** Versi paling sederhana yang berjalan dan sudah ter-deploy dibuat lebih dulu, baru dilengkapi.
3. **Verifikasi dengan data nyata.** Jangan percaya jawaban yang terdengar meyakinkan. Cek ke sumber, uji beberapa kali, simpan angkanya.
4. **Tegakkan di kode, bukan di prompt.** Kalau model sering mengabaikan sebuah aturan, pindahkan aturan itu ke kode atau skema, lalu uji.
5. **Satu perubahan, satu bukti.** Setiap perbaikan diuji dan hasilnya (angka, bukan perasaan) ditulis. Jalankan ulang uji otomatis setelah perubahan berisiko.
6. **Audit berkala.** Setelah fitur selesai, cari celah: kegagalan layanan, batas biaya, kebocoran rahasia, klaim dokumen yang usang.
7. **Akui kesalahan sendiri.** Klaim yang ternyata salah dikoreksi di catatan beserta alasannya, bukan diperbaiki diam-diam.

## 3. Catatan wajib (`notes/`), diperbarui di commit yang sama dengan perubahannya

| File | Isi | Kapan diperbarui |
|---|---|---|
| `progress.md` | "Sekarang" (≤15 baris) + papan irisan + pengingat | Setiap langkah selesai |
| `keputusan.md` | Entri K01, K02, … dengan status | Setiap kali berbeda dari arahan atau contoh |
| `penjelasan-kode.md` | Per file: tugas, fungsi penting, tanya-jawab dengan angka nyata | Setiap file/langkah selesai |
| `hasil-uji.md` | Putaran uji dan temuan | Setiap putaran uji |
| `rencana.md` | Tujuan, irisan, kriteria selesai, kritik rencana | Saat rencana berubah |

Dua jenis penyimpangan di `keputusan.md`: **melawan arahan** (perlu alasan kuat dan konfirmasi) dan **beda dari contoh** (wajar, cukup dijelaskan).

## 4. Keamanan dan uang

- Jangan pernah mencetak atau menempel nilai key. Cek nilai env lewat panjangnya saja.
- Key hanya di `.env` (di-ignore git) dan di rahasia platform deploy. `.env.example` hanya nama variabel.
- Sebelum repo dibuka ke publik: audit seluruh riwayat git dengan nilai key asli.
- Pasang batas pemakaian (per sesi dan per jam) dan batas biaya di key sebelum app dibuka ke publik.
- Hal yang sulit dibalik (menghapus, force-push, mengubah akses, mengirim ke layanan luar) **ditanyakan dulu**. Tidak ada yang dihapus tanpa kata "hapus" dari pemilik.
- Bila push ke `main` me-redeploy app publik, uji perubahan berisiko secara lokal dulu.

## 5. Hemat token (tambahan; tidak ada di sumber)

Sumbernya mengumpulkan ±190 KB catatan; membacanya utuh tiap sesi boros. Karena itu:

- Awal sesi hanya baca "Sekarang" di `progress.md`.
- `keputusan.md`: `grep K<nomor>`; jangan dibaca utuh.
- `penjelasan-kode.md`: baca daftar isi, lalu hanya bagian file yang sedang dikerjakan (`grep -n "^## "` lalu baca rentang barisnya).
- Bila sebuah catatan melewati ±400 baris, pindahkan bagian lama yang sudah beku ke `notes/arsip/` dan biarkan indeks di file utama.
