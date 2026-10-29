# Pas: mockup UI dan brand (usulan)

Salinan sumber Design canvas <https://claude.ai/artifact/C9QgKkDknQb6kA3PTvkMyW>. Alasan dan batasannya ada di K10 (`notes/keputusan.md`). Ini usulan, bukan kode app: kasir Firza tetap di artifact-nya sendiri.

| File | Isi |
|------|-----|
| `canvas.json` | Indeks canvas: posisi dan ukuran tiap artboard, dua halaman (Layar app, Brand & logo). |
| `Main.dc.html` | Layar Kasir: kartu barang, nota berjalan, uang cepat, kembalian, cap LUNAS. Bisa diklik. |
| `Barang.dc.html` | Daftar barang sebagai kartu, form barang baru dengan validasi, tambah stok dengan − / +. |
| `Riwayat.dc.html` | Nota per tanggal sebagai kartu yang bisa dibuka, tombol Ekspor CSV. |
| `Ringkasan.dc.html` | Penjualan hari ini, jumlah nota, penjualan per jam, barang paling laku, stok yang perlu diisi. |
| `Logo.dc.html` | Logo versi terang dan gelap, ukuran kecil, larangan pemakaian, asal-usul nama. |
| `Brand.dc.html` | Brand guideline: prinsip, warna, huruf, kartu dan hover, tombol, cara bicara, bentuk. |

Format `.dc.html` hanya dirender di dalam Design canvas (memakai `support.js` milik canvas), jadi file ini tidak bisa dibuka langsung di browser. Untuk melihatnya, buka link canvas di atas.

Aturan inti, ringkas:

- Warna mencolok hanya biru `#2340FF`, satu tombol utama per layar. Selebihnya tinta `#141414`, kertas `#F4F4F1`, putih, abu `#5A5A55`, garis `#DCDCD6`.
- Kartu saat hover: naik 3 px, garis jadi tinta, bayangan keras 3×4 px tanpa blur, 140 ms.
- Huruf: Hanken Grotesk untuk sementara; target HK Grotesk Wide setelah lisensinya dicek.
