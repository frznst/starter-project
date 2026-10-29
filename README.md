# starter-project

Template repo untuk proyek baru dengan alur vibe coding terstruktur: **rencana → irisan tipis → catat → uji**.

Pola dasarnya diekstrak dari struktur kerja sebuah laporan capstone (jadwal per irisan, log keputusan bernomor, catatan progres dan hasil uji, definisi selesai yang bisa diuji). Aturan hemat token ditambahkan di `CLAUDE.md`.

## Struktur

```
├── CLAUDE.md                  # kontrak kerja untuk Claude (pendek, dimuat tiap sesi)
├── README.md
├── .env.example               # nama variabel saja, tanpa nilai
├── notes/
│   ├── rencana.md             # tujuan, irisan, kriteria selesai, kritik rencana
│   ├── progress.md            # "Sekarang" (≤15 baris) + papan irisan
│   ├── keputusan.md           # log K01, K02, … beserta alasan
│   └── hasil-uji.md           # putaran uji dan temuan
├── src/                       # logika; modul tidak menjalankan apa pun saat import
├── scripts/                   # pekerjaan sekali jalan (ingest, cek koneksi, eval)
├── tests/
└── .claude/commands/          # /rencana  /lanjut  /tutup
```

## Memakai template

```bash
gh repo create NAMA-PROYEK --private --clone --template frznst/starter-project
cd NAMA-PROYEK
claude
```

Lalu di Claude Code:

1. `/rencana` — isi `notes/rencana.md` dan kritik sebelum membangun
2. `/lanjut` — kerjakan irisan aktif
3. `/tutup` — uji, catat, commit; lalu `/compact` atau sesi baru

Hapus bagian "Template repo" ini dan tulis README proyek Anda sendiri setelah dibuat.
