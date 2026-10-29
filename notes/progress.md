# Progress

Diperbarui: 2026-10-29

## Sekarang
<!-- Jaga ≤ 15 baris. Ini satu-satunya bagian yang dibaca di awal sesi. -->
- Proyek: aplikasi Point of Sales barang, waterfall (F1 problem statement → F2 design → F3 implementation), semuanya di Claude artifact (K01, K02).
- F1 dan F2 disetujui pemilik 2026-10-29. Artifact F1: <https://claude.ai/artifact/3j1utfwuLaBWTVc5RTkKwx> · F2: <https://claude.ai/artifact/MtfJuFtJpabpKmk5jd8KUD>
- Fase aktif: F3 langkah 1 (uji risiko). Artifact uji: <https://claude.ai/artifact/Jxh868gVv2y41h6dkwTayv> (memuat inti `POS` = logika + simpan; baca dengan Artifact `action: read`, jangan menebak).
- Langkah 1 (uji risiko) selesai: 11/11 lulus (K08). Langkah 2 (kasir minimal) terbit: <https://claude.ai/artifact/B17113Fxjdo1UcHyvcpeFe> (inti `POS` sama dengan artifact uji; 9 barang contoh di koleksi `barang`, nama bertanda "(contoh)").
- Bila semua lulus → langkah 2: kasir minimal memakai inti yang sama (T-04..T-07). Bila gagal → perbaiki desain kunci dulu.
- File yang relevan: `notes/rencana.md`, `notes/keputusan.md` (K01–K09).
- Pemilik uji coba go-live dulu dengan data contoh (K09). Langkah berikutnya: pemilik melaporkan hasil coba kasir (T-04..T-07 di UI nyata); lalu langkah 3 (layar Barang + tambah stok: T-01..T-03), ekspor CSV, riwayat, ringkasan, uji akhir.
- Blocker: pemilik menjalankan uji risiko.

## Pengingat
<!-- Hari penting, tenggat, hal yang harus dilakukan pemilik sendiri. Format: `(tgl)` -->

## Papan irisan
Status: `belum` · `berjalan` · `menunggu keputusan` · `selesai`

| ID | Irisan | Status | Bukti |
|----|--------|--------|-------|
| F1 | Problem statement (artifact) | selesai | Disetujui pemilik 2026-10-29 |
| F2 | Design (artifact) | selesai | Disetujui pemilik 2026-10-29 |
| F3 | Implementation (artifact) + hasil uji | berjalan | Langkah 1 uji risiko 11/11 lulus; langkah 2 kasir minimal terbit, menunggu dicoba pemilik |
