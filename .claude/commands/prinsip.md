---
description: Wawancara pemilik untuk menambah prinsip pribadi di notes/prinsip-saya.md
---
Tambahkan atau ubah prinsip pemilik. Jangan mengubah `notes/prinsip-kerja.md` (prinsip Guru Besar AI).

1. Baca daftar prinsip yang sudah ada dengan `grep -n "^| P" notes/prinsip-saya.md`, supaya pertanyaan tidak mengulang.
2. Wawancarai pemilik dengan AskUserQuestion, maksimal 4 pertanyaan per putaran, pilihan konkret plus ruang jawaban sendiri. Gali satu tema per putaran, misalnya cara kerja, kualitas kode, biaya, keamanan, komunikasi.
3. Bila dua jawaban tampak bertentangan, sebutkan dan usulkan tafsir yang menyelaraskan. Jangan memilih diam-diam.
4. Tulis prinsip baru sebagai baris tabel (P9, P10, …) di `notes/prinsip-saya.md`: nama, dan artinya dalam praktik. Prinsip yang diganti tidak dihapus, tandai "digantikan oleh P##".
5. Tambahkan satu baris ringkasan di bagian "Prinsip pemilik" pada `CLAUDE.md`.
6. Perubahan masuk lewat branch + PR sesuai P4. Tunjukkan rencana ke pemilik dulu sesuai P1.

Tema atau catatan dari pemilik: $ARGUMENTS
