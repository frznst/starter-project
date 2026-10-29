# Hasil uji

Output model tidak deterministik: jalankan set uji beberapa kali (minimal 3) dan catat semuanya. Periksa perilaku (alat yang dipanggil, argumen, bahasa), bukan kata per kata. Verifikasi jawaban terhadap data sumber, jangan percaya jawaban yang sekadar fasih.

Format per putaran:

```text
## YYYY-MM-DD · irisan Sx · versi (commit/prompt)
Set uji: N kasus × M kali
Lolos: x/N
Gagal: kasus → gejala → penyebab → rujukan K##
```

---

## 2026-10-29 · F3 langkah 1 (uji risiko) · artifact versi 1
Set uji: 11 kasus × 1 kali (data uji `uji_`, satu tab; pembeli serentak disimulasikan dengan pemegang kunci berbeda)
Lolos: 10/11
Gagal: T-07b → stok benar (6) tetapi durasi 3149 ms, ambang 3000 ms terlewati → tiap pembayaran ±3 detik karena 8 perjalanan ke database berurutan (T-07: 2994 ms); ambang 3000 ms adalah tebakan saya, bukan syarat → K08
Angka penting: T-08a dan T-08b lulus (pemulihan tepat sekali, juga saat diulang); T-09a satu berhasil, satu ditolak "stok", stok 0, 9509 ms; T-09b 2 berhasil, 1 ditolak, stok 0.

## 2026-10-29 · F3 langkah 1 (uji risiko) · artifact versi 2
Perubahan: perpanjangan kunci dilewati bila belum setengah masa berlaku dan dicek sebelum tiap tulis stok; barang dibaca serentak; ambang T-07b = 4000 ms (masa berlaku kunci).
Hasil: menunggu pemilik menjalankan ulang.
