# Log keputusan

Satu entri per keputusan, nomor naik terus (K01, K02, …), tidak pernah dihapus. Cari dengan `grep K07 notes/keputusan.md`.
Wajib dicatat: setiap penyimpangan dari arahan/contoh, pilihan di antara beberapa opsi, dan bug yang mengubah desain.

Dua jenis penyimpangan: **melawan arahan** (butuh alasan kuat dan konfirmasi pemilik) dan **beda dari contoh** (wajar, cukup dijelaskan).
Status: ✅ sesuai arahan · 🔁 beda dari contoh · 🔧 revisi atas keputusan sebelumnya (sebut K lama) · 💬 menunggu/sudah dikonfirmasi

Format:

```text
## K00 — Judul singkat
Tanggal: YYYY-MM-DD · Tag: mandatori|bebas|bonus|improvisasi · Status: ✅|🔁|🔧|💬
Konteks: apa masalahnya (1–2 kalimat)
Keputusan: apa yang dipilih
Alasan: kenapa; opsi lain yang ditolak
Bukti: hasil uji / angka / commit
```

---
