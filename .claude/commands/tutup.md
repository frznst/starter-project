---
description: Tutup irisan aktif: uji, catat, commit
---
Tutup irisan aktif sesuai bagian "Menutup irisan" di CLAUDE.md.

1. Jalankan uji sesuai kriteria selesai irisan di notes/rencana.md. Potong output panjang dengan tail.
2. Jika ada yang gagal, laporkan apa adanya dan berhenti; jangan menandai selesai.
3. Jika lolos: tambahkan putaran di notes/hasil-uji.md, perbarui status dan bukti di notes/progress.md, tulis ulang bagian "Sekarang" untuk irisan berikutnya (maks 15 baris), dan catat keputusan baru di notes/keputusan.md bila ada.
4. Commit dengan pesan jelas, lalu tampilkan ringkasan perubahan. Push hanya bila pengguna sudah menyetujui alurnya (branch/PR).
5. Sarankan `/compact` atau sesi baru sebelum irisan berikutnya.

Catatan dari pengguna: $ARGUMENTS
