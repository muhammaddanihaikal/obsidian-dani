# Laporan Eksplorasi & Testing — Halaman Simulasi KPR (Simulasi Pembiayaan)

- URL: https://terasrumah-sandbox.zegen.app/simulasi-kpr/
- Portal: External (publik, tanpa login)
- Tanggal: 25 Nov 2026, ±17:43–17:49 WIB
- Metode: eksplorasi manual menyeluruh via browser (desktop 1919px), termasuk cek hitungan ulang dengan rumus anuitas standar
- Evidence: folder `evidence/` di samping file ini (asli + versi kotak merah)

## Kesimpulan Utama

**Simulator ini pada dasarnya rusak: hasil hitungannya adalah contoh tetap (dummy) yang tidak mengikuti input sama sekali.** Apa pun kombinasi harga, DP, tenor, dan produk yang dimasukkan, hasil yang keluar selalu sama persis:

| Komponen Hasil | Nilai yang Selalu Keluar |
|---|---|
| Angsuran Per Bulan | Rp 1.107.111 |
| Lama Pembiayaan | 180 Bulan |
| Uang Muka (DP) | Rp 10.000.000 |
| Jumlah Pembiayaan Maksimal | Rp 1.500.000 |
| Biaya Bank (Produk Sub) | Rp 5.950.000 |
| Biaya Notaris (Produk Sub) | Rp 9.425.000 |
| Pembayaran Pertama | Rp 26.482.111 |

Tabel Detail Angsuran pun selalu dihitung dari pokok tetap **Rp 140.000.000** (terbukti dari baris bulan 1: Sisa Rp 139.476.222 + Pokok Rp 523.778 = Rp 140.000.000 pas; margin bulan 1 Rp 583.333 = 140.000.000 × 5% / 12). Untuk pokok Rp 140.000.000 itu sendiri tabelnya benar secara matematis — hanya saja pokok itu tidak berasal dari input pengguna mana pun.

## Cara Kerja Halaman

- Form (kiri): dropdown **Pilih Produk Pembiayaan** (Produk Sub, Produk Sub 2, MRB KPR BTN APARTEMEN EFF, MMQ PEMBELIAN COUNTER + SINGLE UJROH, PROMO COUNTER; Produk Sub terpilih otomatis), catatan margin produk, **Harga Properti** (default 600.000.000, format pemisah ribuan otomatis), **Uang Muka/DP** hanya tombol persen 5%/10%/20%/30% (default 20%), **Jangka Waktu (Tenor)** dropdown 5–30 Tahun, **Pilihan Akad Syariah** (Murabahah (MMQ), Musyarakah Mutanaqisah, Murabahah Bil Wakalah), tombol **Hitung**. Tidak ada tombol Reset, tidak ada slider, tidak ada input margin, tidak ada input DP nominal.
- Hasil (kanan): tab **Rincian Pembiayaan** (margin, lama, jumlah maksimal, DP, rincian Biaya Bank & Biaya Notaris, kartu Angsuran Per Bulan + Pembayaran Pertama, catatan disclaimer) dan tab **Detail Angsuran** (tabel per bulan: Sisa, Pokok, Margin, Angsuran, % margin).
- Tidak ada tombol pengajuan/CTA, unduhan, atau grafik di halaman ini.

## Hasil Cek Hitungan (rumus anuitas A = P·r(1+r)^n / ((1+r)^n − 1))

Skema halaman: margin berjenjang — fase 1 bulan 1–24, fase 2 dihitung ulang dari sisa pokok untuk sisa bulan. Angka manual dibulatkan ke ribuan terdekat.

| Kombinasi | Input | Hasil Halaman | Hitungan Manual (berjenjang) | Putusan |
|---|---|---|---|---|
| 1 | 600 jt, DP 20%, plafon 480 jt, 15 th, 5%→13% | Angsuran 1.107.111; DP tampil 10.000.000; Maks 1.500.000 | Fase 1 ±3.795.800; fase 2 ±5.789.000 | TIDAK COCOK (halaman hanya 29,2% dari seharusnya; rasio pas 140/480) |
| 2 | 1.000 jt, DP 10%, plafon 900 jt, 10 th, 5%→13% | Identik dengan Kombinasi 1 (termasuk Lama 180 Bulan, padahal tenor 120) | Fase 1 ±9.547.000; fase 2 ±12.673.000 | TIDAK COCOK (11,6% dari seharusnya) |
| 3 | 300 jt, DP 30%, plafon 210 jt, 5 th, 5%→13% | Identik lagi (Lama tetap 180 Bulan, padahal tenor 60) | Fase 1 ±3.963.000; fase 2 ±4.455.000 | TIDAK COCOK (27,9% dari seharusnya) |
| 4 | MRB KPR BTN APARTEMEN EFF, 600 jt, DP 20%, 15 th | Margin tampil 3,5%/2,5%, tapi Angsuran tetap 1.107.111, Maksimal Rp 70.000, tabel tetap 5%/13% 180 bulan | — | TIDAK COCOK (label produk berubah, angka tidak) |

Plafon (Harga − DP) di panel kiri selalu benar (480 jt / 900 jt / 210 jt), tetapi tidak pernah dipakai di panel hasil.

## Daftar Issue

### KRITIS — Hasil Simulasi Dummy / Tidak Mengikuti Input

1. **Hasil simulasi tidak berubah apa pun inputnya** — Angsuran Rp 1.107.111, Lama 180 Bulan, DP Rp 10.000.000, Maksimal Rp 1.500.000, Biaya Bank Rp 5.950.000, Biaya Notaris Rp 9.425.000 identik untuk Kombinasi 1, 2, 3, juga untuk Harga 0 dan Harga 999.999.999.999. Repro: reload halaman, masukkan kombinasi apa pun, klik Hitung. → `evidence_01`
2. **Klik Hitung kedua dalam sesi yang sama tidak menghitung ulang** — setelah hasil Kombinasi 1 tampil, input diganti (1.000 jt / DP 10% / 10 Tahun) lalu Hitung lagi: semua nilai hasil tetap yang lama. Repro: Hitung sekali, ubah input, Hitung lagi.
3. **Lama Pembiayaan selalu 180 Bulan** — padahal tenor yang dipilih 10 Tahun (120 Bulan) atau 5 Tahun (60 Bulan). Repro: pilih tenor 5 Tahun, Hitung, baca Rincian. → `evidence_01`
4. **Uang Muka (DP) di hasil selalu Rp 10.000.000** — padahal panel kiri halaman yang sama menampilkan dengan benar Rp 120.000.000 (Kombinasi 1), Rp 100.000.000 (Kombinasi 2), Rp 90.000.000 (Kombinasi 3), Rp 0 (Harga 0). Halaman bertentangan dengan dirinya sendiri. → `evidence_01`, `evidence_04`
5. **Jumlah Pembiayaan Maksimal tidak masuk akal dan tidak pernah sama dengan Harga − DP** — Rp 1.500.000 untuk Produk Sub (plafon seharusnya Rp 480.000.000) dan Rp 70.000 untuk produk MRB dengan input harga yang sama. → `evidence_01`, `evidence_02`
6. **Tabel Detail Angsuran berbasis pokok tetap Rp 140.000.000** — tidak mengikuti plafon input (480 jt / 900 jt / 210 jt). Repro: Hitung, buka Detail Angsuran, baca baris bulan 1.
7. **Detail Angsuran selalu 180 baris dengan margin 5% (bulan 1–24) lalu 13% (bulan 25–180)** — termasuk untuk tenor 5 Tahun, dan untuk produk MRB yang rincian biayanya sendiri menulis margin 3,5% (bulan 1–5) dan 2,5% (bulan 6–10). → `evidence_03`

### Biaya

8. **Biaya produk MRB adalah angka dummy urut** — Biaya Bank: Appraisal Rp 10, Administrasi Rp 11, Proses Rp 12, Provisi Rp 0, Asuransi Rp 13 (Total Rp 46). Biaya Notaris: Rp 14, 15, 16, 17, 18, 19 (Total Rp 99). Data contoh mentah tampil ke pengguna. → `evidence_02`
9. **Biaya Produk Sub tidak pernah berubah mengikuti harga** — Proses Rp 2.975.000, Asuransi Rp 2.975.000, Bea Balik Nama Rp 1.487.500, Akta SKMHT Rp 2.975.000, Akta APHT Rp 2.975.000, Perjanjian HT Rp 500.000, Cek Sertifikat Rp 1.487.500 (total 5.950.000 / 9.425.000) identik untuk harga 300 jt, 600 jt, 1.000 jt, 0, dan 999.999.999.999. Nilai-nilai itu konsisten dengan basis ±Rp 595.000.000 (2.975.000 = 0,5%-nya) yang tidak dijelaskan. → `evidence_01`, `evidence_05`

### Validasi

10. **Tidak ada validasi Harga Properti kosong** — field dikosongkan berubah menjadi 0 (DP tampil Rp 0) dan Hitung tetap mengeluarkan hasil contoh yang sama, tanpa pesan error/peringatan. → `evidence_04`
11. **Tidak ada validasi Harga Rp 0** — memasukkan 0 lalu Hitung tetap mengeluarkan hasil yang sama tanpa error. → `evidence_04`
12. **Harga sangat besar diterima tanpa batas/peringatan, dan tampilan DP rusak** — Harga Rp 999.999.999.999 dengan DP 20% menampilkan "Rp 199.999.999.999,8" (koma desimal, 1 angka di belakang koma, teks membungkus dua baris) alih-alih nominal Rupiah bulat; hasil simulasinya pun tetap yang sama. → `evidence_05`

### Konten & Label

13. **Label akad tertukar** — kartu hijau dan dropdown menulis "Murabahah (MMQ)", padahal di halaman Panduan KPR (/panduan/kpr/) Murabahah dan Musyarakah Mutanaqisah (MMQ) adalah dua akad berbeda; halaman Panduan juga mencantumkan akad Istishna yang tidak ditawarkan simulator sama sekali.
14. **Nama produk seperti data tes** — opsi pertama/default dropdown produk bernama "Produk Sub" dan "Produk Sub 2" tampil ke nasabah. → `evidence_01`
15. **Dropdown produk nonaktif "Memuat produk..." selama ±1–2 detik saat halaman dibuka** — form tidak bisa dipakai sampai daftar produk tiba. → `evidence_06`

### Catatan (keterbatasan/minor, bukan bug fungsi)

16. Tidak ada tombol Reset, slider, input margin, maupun input DP nominal (DP hanya 4 tombol persen; tenor hanya dropdown 5–30 tahun) — pengguna tidak bisa menyetel nilai secara leluasa.
17. Hasil tidak punya ringkasan total pokok, total margin, atau total keseluruhan bayar, dan tidak ada grafik — hanya tabel bulanan (yang pokoknya pun salah).
18. Angsuran bulan terakhir (180) Rp 1.688.014, lebih kecil Rp 69 dari bulan 25–179 (Rp 1.688.083) tanpa penjelasan — kemungkinan penyesuaian pembulatan akhir, perlu konfirmasi apakah disengaja.

## Temuan Tambahan di Luar Halaman Ini (saat memeriksa link header/footer)

19. Halaman **Bandingkan** (/bandingkan/) hanya menampilkan spinner loading dengan area utama kosong, tanpa konten/error.
20. Halaman **Artikel** (/article/) hanya menampilkan 6 kartu skeleton/placeholder, tanpa artikel.
21. Halaman **FAQ** (/faq/) menampilkan kartu-kartu kosong, tanpa daftar tanya-jawab.
22. Katalog sandbox kosong: Jadwal Lelang "0–0 dari 0", Aset Lelang "total 0 Aset … Memuat aset…", Aset Baru "total 0 Aset … Memuat aset…" (bukan 404; kemungkinan memang data sandbox).
23. **Nomor call center tidak konsisten antarhalaman** — footer: "1500-286" dan "150-286"; Syarat & Ketentuan: "BTN Call 150286 atau 1500286"; FAQ: "(021) 5299-1200".
24. Link footer **List Developer** mengarahkan pengguna yang belum login langsung ke halaman login, tanpa pesan penjelasan.

## Yang Sudah Benar / Berfungsi

- Halaman publik, terbuka tanpa login; tidak ada error tampilan/overflow di desktop 1919px.
- Pilihan produk memperbarui catatan margin dan badge di form dengan benar (Produk Sub 5%/13%; MRB 3,5%/2,5%).
- Tombol persen DP menghitung nominal DP di panel kiri dengan benar (20% × 600 jt = 120 jt, dst.).
- Pilihan akad langsung memperbarui kartu hijau (mis. ke "Akad: Musyarakah Mutanaqisah").
- Tombol Hitung menampilkan skeleton lalu hasil; perpindahan tab Rincian/Detail Angsuran berfungsi.
- Subtotal biaya menjumlah dengan benar, dan aritmetika Pembayaran Pertama konsisten dengan komponen yang ditampilkan (1.107.111 + 10.000.000 + 5.950.000 + 9.425.000 = 26.482.111) — komponennya yang salah, bukan penjumlahannya.
- Format pemisah ribuan Rupiah benar pada nominal normal; teks disclaimer estimasi tersedia; tidak ada lorem ipsum di halaman simulator.
- Seluruh link header/footer yang diuji mengarah ke halaman yang benar (tidak ada 404): Beranda, Jadwal Lelang, Aset Lelang, Aset Baru, Tentang Kami, FAQ, Simulasi Pembiayaan, Panduan KPR, Syarat & Ketentuan, Kebijakan Privasi, situs bankbsn.co.id, dan menu dropdown Panduan (Lelang/Cessie/Jual Bersama/SKM/Penjualan Sukarela/Panduan KPR).

## Yang Belum Bisa Dicek

- Error konsol browser (tidak ada akses DevTools pada sesi ini; tidak ada error yang terlihat di UI).
- Tampilan mobile/responsif (pengujian hanya desktop).
- Hasil hitung lengkap produk Produk Sub 2, MMQ PEMBELIAN COUNTER + SINGLE UJROH, dan PROMO COUNTER (baru Produk Sub & MRB yang dihitung; pola dummy-nya sudah terkonfirmasi di dua produk).
- Link ikon media sosial footer, link tel: call center, ikon Notifikasi & Favorit (kemungkinan butuh login; tidak diklik agar tidak memicu alur sign-in), dan link unduh PDF Buku Panduan Lelang.
- Penyebab teknis di sisi backend/API untuk hasil yang statis (tidak ada inspeksi jaringan pada sesi ini).
- Perbandingan dengan situs produksi (ini sandbox).
