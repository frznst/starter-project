# Prinsip saya

Prinsip pemilik repo. Berlaku **di samping** `notes/prinsip-kerja.md` (prinsip Guru Besar AI), tidak menggantikannya. Prinsip Guru Besar AI tidak diubah. Bila dua prinsip bentrok langsung, Claude bertanya, tidak memilih sendiri.

Disusun dari wawancara pada 2026-10-29. Ringkasan satu baris tiap prinsip ada di `CLAUDE.md` karena itu yang dibaca tiap sesi.

## Prinsip

| # | Prinsip | Artinya dalam praktik |
|---|---|---|
| P1 | **Usulkan, lalu tunggu OK** | Sebelum mengubah file, Claude menjelaskan rencana: apa yang diubah, di file mana, kenapa, dan perkiraan biaya bila ada. Perubahan baru dikerjakan setelah pemilik menyetujui. Membaca, mencari, dan menjalankan uji tanpa efek samping tidak perlu menunggu OK. |
| P2 | **Hemat biaya dulu** | Bila dua opsi sama-sama cukup, pilih yang lebih murah (token, API, hosting, waktu). Opsi berbayar disebut bersama perkiraan biayanya saat diusulkan. |
| P3 | **Penjelasan sedang, dengan alasan** | Setiap penjelasan memuat apa yang dikerjakan dan kenapa memilih cara itu, dalam beberapa kalimat. Tidak bertele-tele, tidak hanya "sudah selesai". |
| P4 | **Branch + PR, bukan main** | Perubahan masuk lewat branch dan pull request. Tidak ada commit atau push langsung ke `main`. Deskripsi PR memuat apa yang berubah, kenapa, dan bagaimana diuji. Penggabungan (merge) dilakukan setelah pemilik setuju. |
| P5 | **Jangan ubah yang tidak diminta** | Kerjakan sebatas permintaan. Hal lain yang ditemukan (kode berantakan, ide perbaikan, nama yang kurang bagus) dicatat atau diusulkan, tidak dikerjakan diam-diam. |
| P6 | **Defensif untuk yang diminta, tanpa tambahan** | Fitur yang diminta dibuat lengkap: validasi input, penanganan error yang realistis, kasus tepi. Tetapi tidak menambah fitur, abstraksi, atau opsi konfigurasi yang belum diminta. |
| P7 | **Bahasa Indonesia untuk teks, Inggris untuk nama** | Komentar kode, pesan commit, deskripsi PR, dan dokumen memakai bahasa Indonesia. Nama variabel, fungsi, dan file memakai bahasa Inggris. |
| P8 | **Pola pikir produk** | Tujuan utamanya produk/usaha, jadi sebelum rilis pikirkan pengguna nyata: keamanan data dan secret, biaya per pengguna, batas pemakaian, dan apa yang terjadi saat layanan luar gagal. Memperluas bagian "Keamanan dan uang" di `prinsip-kerja.md`. |

## Catatan tafsir

- P6 menyelaraskan dua jawaban pemilik: "defensif & lengkap" dan kesal pada "kode berlebihan". Tafsirannya: lengkap menurut apa yang diminta, bukan menurut apa yang mungkin dibutuhkan kelak.
- Pengecualian "tanpa OK" di P1 adalah asumsi Claude, bukan jawaban pemilik. Ubah bila tidak cocok.

## Menambah prinsip

Jalankan `/prinsip`. Claude mewawancarai Anda, lalu menambahkan P9, P10, dan seterusnya ke file ini beserta satu baris ringkasan di `CLAUDE.md`. Prinsip lama tidak dihapus; yang diganti ditandai "digantikan oleh P##".
