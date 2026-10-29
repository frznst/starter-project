# Rencana

> Isi sebelum menulis kode. Rencana adalah kontrak: tiap irisan punya kriteria selesai yang bisa diuji.

## Tujuan
Aplikasi Point of Sales barang untuk toko kecil (satu toko, satu kasir): mencatat penjualan tunai, mengurangi stok otomatis, dan menampilkan rekap harian. Hasil akhir: aplikasi yang bisa dipakai di Claude artifact, dengan hasil uji tercatat. Rincian syarat FR-01..FR-10 dan NFR-01..NFR-06 ada di artifact F1 (lihat `progress.md`).

## Batasan & arahan
- Metode waterfall: tiap fase selesai dan disetujui pemilik sebelum fase berikutnya (K01).
- Semua fase dikerjakan sebagai Claude artifact; catatan di repo ini (K02, K03).
- Biaya berjalan nol (NFR-06). Tidak ada tenggat tertulis.

## Tag requirement
`mandatori` tidak boleh diganti · `bebas` pilihan kita, catat alasannya · `bonus` nilai tambah · `improvisasi` di luar permintaan

## Irisan
Irisan pertama = versi terkecil yang berjalan ujung ke ujung. Bukan "bangun semua data, lalu semua API, lalu UI".

| ID | Irisan | Tag | Kriteria selesai (bisa diuji) |
|----|--------|-----|-------------------------------|
| F1 | Problem statement (artifact) | bebas | Tiap syarat punya ID dan bisa dijawab lulus/tidak; asumsi A1–A6 dijawab pemilik; pemilik menyatakan OK |
| F2 | Design (artifact): alur kasir, model data, aturan bisnis, sketsa layar, rencana uji | bebas | Tiap FR/NFR F1 terpetakan ke elemen desain dan ke satu uji; keputusan penyimpanan dan atomisitas stok tertulis; pemilik menyatakan OK |
| F3 | Implementation (artifact): kasir minimal dulu, lalu fitur lain | bebas | Semua uji rencana F2 lulus dengan angka tercatat di `hasil-uji.md`; stok tidak pernah negatif; total dan kembalian benar pada semua skenario |

## Risiko teknis terbesar
R1: stok dan uang tidak konsisten karena artifact tanpa server (dua transaksi berdekatan bisa menjual stok yang sama). Cara mencegah dirancang di F2, diuji paling awal di F3. Cadangan: penyimpanan browser satu perangkat bila penyimpanan bersama tidak memadai. Risiko lain (R2–R4) ada di artifact F1.

## Kritik rencana (jalankan sebelum membangun)
Tiap pertanyaan dijawab ya/tidak; yang "tidak" diperbaiki di rencana, dicatat di `keputusan.md`.
- [ ] Jadwal per irisan, bukan per lapisan?
- [ ] Ada komponen/tool yang tugasnya tumpang-tindih?
- [ ] Input bebas yang harus cocok persis sudah dibatasi (enum)?
- [ ] Ada logika yang akan tertulis dua kali?
- [ ] Dependensi berisiko sudah diuji sebelum dibangun di atasnya?
- [ ] Tiap irisan punya definisi selesai yang bisa diuji, bukan "sudah bagus"?
- [ ] Ada pekerjaan tambahan tanpa jaminan hasil beda? (buang)
- [ ] Aturan kritis ditegakkan di kode, bukan hanya di prompt?
