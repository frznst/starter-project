# CLAUDE.md — Standar kerja

Alur: **rencana → irisan tipis → catat → uji**. File ini sengaja pendek karena dimuat di setiap sesi.
Baca file lain hanya saat dibutuhkan.

## Mulai sesi (urut)
1. Baca bagian **Sekarang** di `notes/progress.md`. Itu sumber kebenaran status.
2. Kerjakan **hanya irisan aktif**. Jangan memindai seluruh repo; buka file yang disebut di irisan.
3. Butuh alasan di balik sebuah pilihan? `grep K<nomor> notes/keputusan.md`, jangan baca seluruh file.

## Prinsip (urutan prioritas bila bertentangan)
simple → structural → logical → efficient & effective. "Impressive" hanya setelah keempatnya terpenuhi.

## Aturan rekayasa
- **Irisan, bukan lapisan.** Versi paling sederhana yang jalan dari ujung ke ujung (dan ter-deploy bila ada deploy) dibuat dulu, lalu dilengkapi. Masalah integrasi harus ketahuan di irisan pertama.
- **Satu logika, satu tempat.** Pembersihan data, validasi, dan aturan bisnis ditulis sekali dan dipakai ulang.
- **Aturan kritis ditegakkan di kode atau skema, bukan di prompt.** Model sering mengabaikan aturan yang hanya ada di prompt. Prompt untuk perutean dan gaya.
- **Batasi input bebas.** Pakai enum/Literal untuk nilai yang harus cocok persis.
- **UI tipis.** Logika di modul terpisah; modul yang di-import tidak menjalankan apa pun saat import.
- **Uji risiko terbesar dulu**, sebelum membangun di atasnya (koneksi, API pihak ketiga, deploy).
- **Definisi selesai harus bisa diuji.** Tulis kriterianya di `notes/rencana.md` sebelum mengerjakan.
- **Penyimpangan dicatat.** Setiap pilihan yang berbeda dari arahan atau contoh masuk `notes/keputusan.md` dengan alasan.
- **Secret.** `.env` tidak pernah di-commit; `.env.example` hanya nama variabel. Audit riwayat git sebelum repo dibuat publik.

## Aturan hemat token
- Jangan membaca ulang file yang sudah ada di konteks. Untuk file besar, baca potongan (offset/limit) atau `grep` dulu.
- Pencarian luas (banyak file/direktori) didelegasikan ke subagent Explore; hanya kesimpulannya yang masuk konteks.
- Output panjang (log, test) dipotong: `| tail -n 30`. Jangan menempel output penuh ke chat.
- `notes/progress.md` bagian **Sekarang** dijaga ≤ 15 baris. Riwayat lama dipindah ke `notes/keputusan.md`, bukan ditumpuk.
- Satu irisan per sesi bila memungkinkan. Di batas irisan: `/tutup`, lalu `/compact` atau sesi baru, lanjut dengan `/lanjut`.
- Jangan menulis ulang file untuk perubahan kecil; pakai Edit.

## Menutup irisan (`/tutup`)
1. Jalankan uji sesuai kriteria selesai; catat hasil di `notes/hasil-uji.md`.
2. Perbarui `notes/progress.md`: status irisan, bukti, dan **Sekarang** untuk irisan berikutnya.
3. Catat keputusan baru (K##) bila ada.
4. Commit kecil dengan pesan jelas; push. Jangan commit ke `main` langsung untuk perubahan besar: pakai branch + PR.

## Minta izin dulu
Menghapus data/branch, `push --force`, mengubah repo jadi publik, menambah dependensi besar, mengubah skema data.

## Peta repo
`notes/` rencana, progres, keputusan, hasil uji · `src/` logika · `scripts/` pekerjaan sekali jalan · `tests/` uji · `.claude/commands/` perintah `/lanjut` `/tutup` `/rencana`
