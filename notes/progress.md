# Progress

Diperbarui: 2026-10-29

## Sekarang
<!-- Jaga ≤ 15 baris. Ini satu-satunya bagian yang dibaca di awal sesi. -->
- Proyek: aplikasi Point of Sales barang, waterfall (F1 problem statement → F2 design → F3 implementation), semuanya di Claude artifact (K01, K02).
- F1 dan F2 disetujui pemilik 2026-10-29. Artifact F1: <https://claude.ai/artifact/3j1utfwuLaBWTVc5RTkKwx> · F2: <https://claude.ai/artifact/MtfJuFtJpabpKmk5jd8KUD>
- Fase aktif: F3 langkah 1 (uji risiko). Artifact uji: <https://claude.ai/artifact/Jxh868gVv2y41h6dkwTayv> (memuat inti `POS` = logika + simpan; baca dengan Artifact `action: read`, jangan menebak).
- Putaran 1: 10/11 lulus; T-07b gagal (durasi 3149 ms), diperbaiki di artifact versi 2 (K08). Langkah berikutnya: pemilik menjalankan ulang uji; baca hasil dari db `uji_hasil/terakhir` (ArtifactData `get`), catat di `notes/hasil-uji.md`.
- Bila semua lulus → langkah 2: kasir minimal memakai inti yang sama (T-04..T-07). Bila gagal → perbaiki desain kunci dulu.
- File yang relevan: `notes/rencana.md`, `notes/keputusan.md` (K01–K08).
- Gerbang: pemilik menyetujui hasil uji risiko sebelum UI dibangun.
- Blocker: pemilik menjalankan uji risiko.

## Pengingat
<!-- Hari penting, tenggat, hal yang harus dilakukan pemilik sendiri. Format: `(tgl)` -->

## Papan irisan
Status: `belum` · `berjalan` · `menunggu keputusan` · `selesai`

| ID | Irisan | Status | Bukti |
|----|--------|--------|-------|
| F1 | Problem statement (artifact) | selesai | Disetujui pemilik 2026-10-29 |
| F2 | Design (artifact) | selesai | Disetujui pemilik 2026-10-29 |
| F3 | Implementation (artifact) + hasil uji | berjalan | Langkah 1 (uji risiko): putaran 1 10/11, versi 2 menunggu uji ulang |
