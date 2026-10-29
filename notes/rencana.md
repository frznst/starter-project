# Rencana

> Isi sebelum menulis kode. Rencana adalah kontrak: tiap irisan punya kriteria selesai yang bisa diuji.

## Tujuan
<!-- 1–3 kalimat: apa yang dibangun, untuk siapa, apa hasil akhirnya. -->

## Batasan & arahan
<!-- Tanggal, anggaran, stack wajib, arahan dari dosen/klien. -->

## Tag requirement
`mandatori` tidak boleh diganti · `bebas` pilihan kita, catat alasannya · `bonus` nilai tambah · `improvisasi` di luar permintaan

## Irisan
Irisan pertama = versi terkecil yang berjalan ujung ke ujung. Bukan "bangun semua data, lalu semua API, lalu UI".

| ID | Irisan | Tag | Kriteria selesai (bisa diuji) |
|----|--------|-----|-------------------------------|
| S1 | Kerangka berjalan ujung ke ujung (1 fitur, ter-deploy) | mandatori | |
| S2 | | | |

## Risiko teknis terbesar
<!-- Hal yang paling mungkin gagal. Diuji lebih dulu, sebelum S1 dilanjutkan. Sertakan cadangan. -->

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
