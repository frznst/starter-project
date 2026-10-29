---
description: Tutup irisan aktif: uji, catat, commit
---
Tutup irisan aktif sesuai bagian "Menutup irisan" di CLAUDE.md.

1. Jalankan uji sesuai kriteria selesai irisan di notes/rencana.md. Potong output panjang dengan tail.
2. Jika ada yang gagal, laporkan apa adanya dan berhenti; jangan menandai selesai.
3. Jika lolos: tambahkan putaran di notes/hasil-uji.md, perbarui status dan bukti di notes/progress.md, tulis ulang bagian "Sekarang" untuk irisan berikutnya (maks 15 baris), dan catat keputusan baru di notes/keputusan.md bila ada.
4. Commit dengan pesan jelas dalam bahasa Indonesia di branch, push branch, dan buka PR yang memuat apa yang berubah, kenapa, dan bagaimana diuji. Jangan commit atau push ke `main`; merge menunggu persetujuan pemilik (P4).
5. Sarankan `/compact` atau sesi baru sebelum irisan berikutnya.

Catatan dari pengguna: $ARGUMENTS
