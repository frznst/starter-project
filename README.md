# starter-project

Template repo untuk proyek baru dengan alur vibe coding terstruktur: **rencana → irisan tipis → catat → uji**.

Pola dasarnya diadaptasi dari `notes/prinsip-kerja.md` di repo capstone `reinerrekado/purwadhika-capstone-3` (jadwal per irisan, log keputusan bernomor, catatan progres/penjelasan kode/hasil uji, definisi selesai yang bisa diuji). Aturan hemat token dan perintah `/rencana` `/lanjut` `/tutup` ditambahkan di sini.

## Struktur

```text
├── CLAUDE.md                  # kontrak kerja untuk Claude (pendek, dimuat tiap sesi)
├── README.md
├── .env.example               # nama variabel saja, tanpa nilai
├── notes/
│   ├── rencana.md             # tujuan, irisan, kriteria selesai, kritik rencana
│   ├── progress.md            # "Sekarang" (≤15 baris) + papan irisan
│   ├── keputusan.md           # log K01, K02, … beserta alasan dan status
│   ├── penjelasan-kode.md     # per file: tugas, fungsi penting, tanya-jawab
│   ├── hasil-uji.md           # putaran uji dan temuan
│   ├── prinsip-kerja.md       # prinsip dan metode Guru Besar AI (rujukan, tidak dibaca tiap sesi)
│   └── prinsip-saya.md        # prinsip pemilik repo (P1, P2, …), ditambah lewat /prinsip
├── src/                       # logika; modul tidak menjalankan apa pun saat import
├── scripts/                   # pekerjaan sekali jalan (ingest, cek koneksi, eval)
├── tests/
└── .claude/commands/          # /rencana  /lanjut  /tutup  /prinsip
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
