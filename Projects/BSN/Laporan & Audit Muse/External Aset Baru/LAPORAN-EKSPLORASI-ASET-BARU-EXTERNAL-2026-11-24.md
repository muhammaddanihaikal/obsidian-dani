# Laporan Eksplorasi Aset Baru — Portal External

> Tanggal: Senin, 24 November 2026, ±14:24–14:42 WIB
> Akun: customer@terasrumah.dev (login via takeover oleh Muhammad + OTP Mailpit)
> Baseline Internal: tab Published berisi **4 aset** (MKSS-10010, JKHS-10007, JKHS-10003, MKSS-10005)
> Sifat: read-only. Satu-satunya pengecualian (peminatan dummy) TIDAK jadi disubmit — alasannya di bagian 6.

---

## Ringkasan Temuan HARD

1. **Aset Belum Publish ikut tampil di External (TERKONFIRMASI).** External menampilkan **6 aset**, Internal Published hanya **4**. Verifikasi Internal (24 Nov 14:43): JKHS-10001 statusnya "Menunggu Verifikasi / Belum Publish" dan JKHS-10004 "Butuh Revisi / Belum Publish" — keduanya **belum publish tapi tampil penuh di External** (bisa dibuka detailnya dan diajukan peminatan).
2. **Halaman detail menampilkan developer yang salah untuk semua aset.** Semua detail menulis "PT Sinar Mas Land Tbk", padahal developer aslinya beda-beda (di card daftar justru benar). Isi detail (spesifikasi, fasilitas, lokasi) juga template BSD City yang sama persis untuk semua aset — tidak sesuai asetnya.
3. **Daftar aset sempat gagal dimuat ±8 menit** (14:24–14:32): "Data aset belum dapat dimuat." di Aset Baru, Aset Lelang, dan daftar developer; pulih sendiri ±14:37. Filter lokasi DKI Jakarta yang saat itu 0 hasil ternyata **intermiten** (efek gangguan yang sama) — setelah pulih filter bekerja benar (2 hasil, terverifikasi 2×). Bukan bug stabil.
4. **Pagination katalog gabungan (/after-search/) tidak berfungsi** — tombol halaman 2 & "Selanjutnya" timeout, daftar tetap 1–6 dari 11.
5. **Simulasi salah hitung**: dari detail aset, harga tidak terbawa (tetap default Rp 600 Jt); hasil Hitung menampilkan DP Rp 10.000.000 (input Rp 120.000.000) dan plafon Rp 1.500.000.
6. **Submit peminatan ditolak 3×** dengan toast "Lengkapi data pemohon: status pernikahan" padahal field terisi "Menikah" (nilai prefill tidak terdaftar sampai diubah manual).
7. **Angka DP tidak konsisten** untuk lead yang sama: checkout Rp 50.000.000 (10%), halaman nasabah "DP Minimal Rp 25.000.000", detail lead Internal "DP 10%" = Rp 85.000.000 (17%).

> PEMINATAN AKHIRNYA DISUBMIT (keputusan Muhammad 14:51, data dummy): BERHASIL — toast "Berhasil Mengajukan Peminatan Aset Baru", lead **#ENT-01m8-8153** (JKHS-10007, 24 Nov 14:59 WIB). TERVERIFIKASI di Internal Leads Aset Baru: baris "[AUTO-QA] Test Peminatan / JKHS-10007 / 24/11/2026 14:59 / Tindak Lanjut", total leads 3 → 4, 12 berkas dummy terunggah semua. Alur External → Leads JALAN. Detail lengkap di LAPORAN-SINGKAT-ISSUE-HARD-2026-11-24.md.

Temuan pendukung lain ada di bagian 3–5.

---

## 1. Daftar Aset Baru (External)

Setelah pulih: "Menampilkan 1 - 6 dari total 6". Card **tidak** menampilkan harga coret dan **tidak** menampilkan stok sama sekali. Pagination 1 halaman.

| Kode | Nama di card | Developer (card) | Harga | Foto |
|---|---|---|---|---|
| JKHS-10003 | Pine Residence - Tipe 50/100 | PT Harmoni Properti Nusantara | Rp 300 Juta | 5 |
| MKSS-10010 | Cluster Elok A - Tipe A | PT. Permata (Sutera Elok) | Rp 5 Miliar | 4 |
| JKHS-10007 | Maple Garden - Tipe 36/72 | PT Harmoni Properti Nusantara | Rp 500 Juta | 5 |
| JKHS-10004 | Maple Garden - Tipe 45/90 | PT Harmoni Properti Nusantara | Rp 450 Juta | 5 |
| JKHS-10001 | Maple Garden - Tipe 36/72 | PT Harmoni Properti Nusantara | Rp 790 Juta | 5 |
| MKSS-10005 | Atalantik - Tipe 35/70 | PT Membangun Jupiter Bhumi (Earth Sutera) | Rp 450 Juta | 6 |

- Keempat aset baseline ada semua, developer di card **sesuai** baseline, harga **sesuai** baseline.
- MKSS-10005 (stok Internal 0) tetap tampil; stok tidak ditampilkan di mana pun di External, jadi stok 0 tidak bisa diverifikasi dari portal ini.

## 2. Search & Filter

- Search "Harmoni" → 4 hasil (JKHS-10003, 10007, 10004, 10001) — benar.
- Search "zzzqqq" → 0 hasil, empty state "Belum ada aset baru yang sesuai" — benar.
- Filter harga "< 500 Jt" → 4 hasil, tapi aset Rp 500 Juta **ikut masuk** (label "<" tapi perilaku "≤"). Selisih kecil.
- Filter KT 4 → 2 hasil, benar. Filter KM 2+ → 4 hasil, benar. Filter developer PT Harmoni → 4 hasil, benar. Filter tipe "Apartemen" → 2 hasil.
- **Filter lokasi "DKI JAKARTA" → 0 hasil (BUG)** — memilihnya saja tidak berefek; setelah "Cari Aset" (?province=31) hasilnya 0 dari 0.
- Radio Akad Syariah nonaktif: "Pilihan akad belum tersedia untuk penyaringan aset."
- Sorting berfungsi benar: Harga Tertinggi/Terendah urutannya konsisten terbalik. Pilihan: Rekomendasi Terpopuler, Harga Terendah, Harga Tertinggi, Terlama.
- Input harga Minimum/Maksimum manual terlihat tapi tidak diuji nilainya.

## 3. Halaman Detail (keempat aset dibuka)

Pola URL: `/detail-asset-jual/<slug>/`. Galeri foto berfungsi (preview + geser + thumbnail terverifikasi).

**Yang salah di SEMUA detail:**

- Developer tertulis **PT Sinar Mas Land Tbk** — bertentangan dengan card & data Internal.
- Blok spesifikasi identik untuk semua aset: "Tipe 120 / 140", LT "–", LB "–", KT "4 + 1", KM "3 + 1", Carport 2, Daya 3.500 VA, hadap Selatan, Row 8 m, keterangan "blueprint arsitektur Sinar Mas Land".
- Fasilitas identik: tema "The Mozia & BSD City". Lokasi identik: "AEON Mall & ICE BSD 5 Menit / Tol Serpong-Balaraja 6 Menit / Stasiun Cisauk Intermoda 8 Menit" — tidak sesuai aset Bogor/Jakarta.
- Harga coret selalu = harga × 1,25 (Rp 500 Jt → coret Rp 625 Jt, "Hemat Rp 125 Juta"; Rp 5 M → coret Rp 6,25 M; dst). Berkaitan dengan issue tracker External "Card Aset 01 — Informasi Developer & Harga Coret Belum Sesuai" (status Re-Open).
- **Tidak ada bagian legalitas** dan **tidak ada sisa stok** di halaman detail.
- Peta: "Koordinat lokasi tidak tersedia" di semua detail (tombol Buka Google Maps ada, tidak diklik).
- Judul tab browser semua aset: "Harga mulai Rp0"; harga di badan halaman termuat belakangan (dari Rp 0 ke harga benar).
- "Unit serupa" sama di semua detail: MKSS-10005, JKHS-10001, JKHS-10004 + Aset Lelang Bandung BDGS-10001 (Rp 70 Miliar).

Per aset: MKSS-10010 4 foto Rp 5 M; JKHS-10007 5 foto Rp 500 Jt (RM: Faris Ramadhan, KCP BSD, tombol WA wa.me/6280000000000); JKHS-10003 5 foto Rp 300 Jt (alamat tampil "rusun flamboyan jakarta barat" — di Internal: Kepulauan Seribu Selatan); MKSS-10005 6 foto Rp 450 Jt.

Tombol di detail: Bagikan aset, Simpan ke favorit, Ajukan Peminatan Unit, Hubungi RM via WhatsApp, Bandingkan Aset, Hitung Simulasi Lengkap.

## 4. Fitur Lain

- **Bandingkan**: berfungsi — 2 aset masuk slot perbandingan (/bandingkan/). Tapi kolom Kamar Tidur, Kamar Mandi, Status Hunian, Kategori Penjualan semuanya "–". Teks "Butuh Minimal 2 Properti" tampil juga saat properti < 2.
- **Favorit**: berfungsi (simpan → "Tersimpan", bisa dibatalkan lagi; keadaan dikembalikan seperti semula). Favorit akun saat ini: JKHS-10003, JKHS-10004, MKSS-10005.
- **Bagikan**: menu WhatsApp/Facebook/X/Telegram/LinkedIn/Salin Link — tidak ada yang dikirim.
- **Simulasi dari detail**: hanya membawa jenis & subsidi (?jenis=Apartemen&subsidi=0). **Harga Properti tetap default Rp 600.000.000** (bukan harga aset), DP Rp 0, dropdown produk macet di "Memuat produk...", hasil "Kamu belum memiliki perhitungan." Tombol Hitung tidak diklik.
- **Pagination katalog gabungan** (/after-search/, total 11 aset): tombol "2" dan "Selanjutnya" timeout 3×, daftar tetap 1–6 — **rusak**.
- Beranda: rekomendasi sempat "Belum ada aset yang sesuai dengan filter ini", hitungan kategori tampil "—Unit". Daftar Developer (/developer-list/) gagal: "Gagal memuat data developer.", 0 developer (saat gangguan).

## 5. Gangguan Muat di Awal (±14:24–14:32)

- /aset-baru/ berulang kali "Data aset belum dapat dimuat." + tombol "Coba lagi"; sidebar "Gagal memuat developer. Coba lagi"; footer "Menampilkan 0 - 0 dari total 0".
- Search saat gangguan ikut berakhir error (bukan hasil/empty state). Satu search "Earth Sutera" macet di "Memuat aset…" > 2 menit.
- Aset Lelang kena sama. Pulih sendiri ±14:37 (daftar 6 aset termuat normal).

## 6. Peminatan — awalnya ditahan, akhirnya DISUBMIT atas keputusan Muhammad (lihat catatan di Ringkasan)

"Ajukan Peminatan Unit" membuka **Formulir Pengajuan Peminatan Aset Baru** penuh (halaman /checkout/, 4 tahap, 5 bagian) — bukan form minat sederhana, dan **tidak ada field catatan/pesan**. Isinya:

- Terisi otomatis: unit Rp 500.000.000, "Tipe36/90" (di card/detail: 36/72), "2KT +1KM" (di card: 2 KT, 2 KM) — **data prefill tidak konsisten**, legalitas "SHM Ready", Selling Officer Ahmad Fauzi, DP 10% Rp 50.000.000, Tenor 15 Thn (est. Rp 4,02 Jt/bln), Plafon 90% Rp 450.000.000, nama "Terasrumah Customer", email akun, WA 088976972688.
- Wajib diisi: NIK KTP 16 digit, tempat & tanggal lahir, alamat lengkap sesuai KTP (RT/RW, kelurahan, kecamatan, kota, provinsi, kode pos), no. telepon/WA, nama instansi, jenis pekerjaan, penghasilan THP bulanan.
- Wajib upload **11 berkas** (0/11): Formulir Pengajuan KPR, Sertifikat SHM/HGB Induk, Izin PBG/IMB, e-KTP, NPWP, Pas Foto 3x4, Kartu Keluarga, SK Domisili (opsional), SK Kerja, Slip Gaji 3 Bulan, Rekening Koran 3 & 6 Bulan.
- Kelengkapan form saat dibuka: 25%.

Data dummy `[AUTO-QA]` tidak bisa dipakai di form ini, dan Muse tidak mengarang NIK/dokumen pribadi. **Tidak ada yang diisi/disubmit.** Daftar Peminatan akun: "Tidak ada pesanan ditemukan", 0 unit.

Pilihan untuk Muhammad: (a) skip uji peminatan, atau (b) sediakan satu set data + berkas tes resmi dari tim untuk dipakai.

## 7. Locator Kunci (External)

- Menu "Aset Baru" → /aset-baru/; search textbox placeholder "Cari nama proyek, developer, atau lokasi..." + tombol "Cari Aset"; combobox lokasi "Semua Lokasi".
- Filter: tombol harga "< 500 Jt" / "500 Jt – 1 M" / "1 M – 2.5 M" / "> 2.5 M"; checkbox tipe (mis. "Apartemen 2") & developer; tab KT 1/2/3/4/5+; tab KM Semua/1/2+/3+; tombol "Reset Filter"; sort "Rekomendasi Terpopuler" (opsi Harga Terendah/Tertinggi/Terlama); toggle "Tampilan grid"/"Tampilan daftar".
- Card = elemen `<article>`, judul = link ke /detail-asset-jual/…/; tombol card: "Ajukan Pembiayaan" (ke detail), "Simulasi" (→ /simulasi-kpr/), bagikan, "Simpan ke favorit"/"Hapus dari favorit".
- Detail: tombol "Ajukan Peminatan Unit", "Bandingkan Aset", "Bagikan aset", galeri "Buka preview foto".
- Form peminatan: /checkout/?id_asset=…&tipe=baru; field "Nama Lengkap Sesuai KTP", "NIK KTP (16 Digit)", "Nomor WhatsApp", "Email Pemohon"; tombol "Batal" / "Kirim Pengajuan Lead".

## 8. Verifikasi Internal + Peta Leads Aset Baru (24 Nov 14:43, read-only)

- JKHS-10001: Menunggu Verifikasi, **Belum Publish** (switch publish nonaktif), Ciledug, Kota Tangerang, Rp 790.000.000, 12 unit.
- JKHS-10004: Butuh Revisi, **Belum Publish** (switch publish nonaktif), Cipondoh, Kota Tangerang, Rp 450.000.000, 20 unit.
- Kesimpulan: temuan HARD no. 1 terkonfirmasi — filter publish di External bocor.

**Leads Aset Baru** (di bawah Customer Management):
- URL: /internal/manajemen-peminat/leads/aset-baru
- Card: Total Leads Terdaftar 3 (bulan ini +3) | Perlu Tindak Lanjut 3 (2 SLA kritis) | Selesai/Terkonversi 0 | Batal/Ditolak 0
- Tab status: Semua 3, Tindak Lanjut 2, Processing 0, Terverifikasi 1, Selesai 0, Batal 0
- Kolom tabel: No, ID Pesanan, Peminat, Kode Asset, Waktu Peminatan, Status Lead, Aksi (+ checkbox)
- Locator: search placeholder "Cari ID Pesanan...", dropdown "Pola Penjualan: Semua", tanggal awal/akhir, tombol "Cari" & "Reset filter", tombol atas "Segarkan" & "Download Data"
- Lead yang ada = 3 (data tim, tidak dibuka detailnya). Karena peminatan tes tidak disubmit, belum ada lead baru dari eksplorasi ini.

## 9. Sisa Data

- Tidak ada data baru yang dibuat. Favorit JKHS-10007 sempat disimpan lalu dibatalkan lagi (kembali seperti semula). Peminatan: 0.
