# Eksplorasi Read-Only — Stock Management / Aset Baru (Internal)

- Tanggal: Senin, 23 Nov 2026, ±14:48–14:50 WIB
- Environment: https://terasrumah-sandbox.zegen.app/internal (sandbox)
- Akun: danihaikal@gmail.com (role tampil: Superadmin) — login via password + TOTP authenticator, berhasil
- Mode: READ-ONLY penuh. Nol data dibuat/diubah/disubmit/di-approve/di-publish/dihapus. Mailpit tidak disentuh.

## 1. Halaman List — /internal/stock-management/aset-baru

Judul: "Daftar Aset Baru Terdaftar".

### Kartu ringkasan
- TOTAL ASET TERDAFTAR: 19 Unit, nilai Rp 13,8 Miliar
- PUBLISHED / TAYANG: 4 Unit Aktif
- STOK UNIT TERSEDIA: 540 Unit Total
- NONAKTIF / DRAF: 14 Unit Draf
- MENUNGGU VERIFIKASI: 11 Berkas

### Quick-filter chips
Semua Aset 19 · Published / Tayang 4 · Stok 0 · Draf Pengajuan 3 · Menunggu Verifikasi 11 · Butuh Revisi 1

### Search & filter
- Text search: "Cari nama aset, kode aset, atau lokasi"
- Dropdown: Kode Aset (19 kode: JKHS-10001 s.d. JKHS-10015, JPMS-10001, MKSS-10005, MKSS-10010, MKSS-10011), Status Publish (Published / Tayang, Belum Publish), Status Verifikasi (Draf Pengajuan, Menunggu Verifikasi, Butuh Revisi, Terverifikasi, Terverifikasi Aktif), Developer (≥11: Firman, PT. Agung Mas, PT Cendana Properti Nusantara, PT Harmoni Properti Nusantara, PT. Insan Mandiri, PT Membangun Jupiter, PT. Permata, PT PTAN, PT. SEJAHTERA, PT Sinar Matahari Bulan, PT Terasrumah Developer), Klaster (DISABLED sampai Developer dipilih)
- Tombol Reset
- Banner aturan: hanya aset Terverifikasi yang bisa dipublish; status lain terkunci otomatis

### Tombol atas
Unduh Rekap · Opsi ekspor (menunya hanya berisi "Lihat Status Ekspor" — tidak ada pilihan format yang dipilih, tidak ada yang diunduh) · Input Aset Baru

### Tabel (8 kolom)
Kode & Unit Aset · Developer & Proyek · Spesifikasi & Segmen · Jumlah Unit · Nilai Harga Agunan · Status Verifikasi · Status Publish · Aksi
- Baris berisi thumbnail, tipe, link kode, developer/proyek + lokasi, LT/LB, KT/KM, Subsidi/Non Subsidi, jumlah unit + bar stok 100% + Stok/Terjual, harga, badge verifikasi, toggle publish + label
- Sort tersedia di: Kode & Unit Aset, Developer & Proyek, Nilai Harga Agunan, Status Verifikasi. Header kolom bisa di-drag (reorder)
- Tidak ada pemilih jumlah data per halaman
- Aksi per baris: Detail (tab baru), tombol edit pensil (tidak diklik), menu titik tiga (pada baris Draf yang dicek isinya: "Salin Kode Aset", "Riwayat Status")
- Toggle publish: disabled untuk baris belum terverifikasi, aktif untuk yang published

### Status & pagination
- Verifikasi: Draf Pengajuan 3, Menunggu Verifikasi 11, Butuh Revisi 1, Terverifikasi Aktif 4 (total 19)
- Publish: Belum Publish, Aktif (Published)
- Pagination: "Menampilkan 1–10 dari 19", 10/halaman, 2 halaman, Sebelumnya/Selanjutnya
- Harga terlihat: terendah Rp 0 (JKHS-10015, status Draf), tertinggi Rp 5.000.000.000 (MKSS-10010)

## 2. Halaman Detail (1 sampel, view-only) — MKSS-10010 "Sutera Elok - Tipe A" (PUBLISH)

- Tab: Identitas Aset, Spesifikasi Unit, Dokumen Legalitas, Lokasi & Peta, Fasilitas, Akurasi Data
- Tombol: Unduh Ringkasan, Edit Aset (tidak diklik)
- Identitas: Kode Aset MKSS-10010; Status Published; Kode CIF Rekanan A1271; Kode Developer DEV-BSN-1271; Pengembang PT. Permata; Harga Rp 5.000.000.000; Min. Uang Muka (5%) Rp 250.000.000; Cabang Pengampu KCS Makassar
- Spesifikasi: Rumah, Klaster Cluster Elok A, Tipe A, LT 120 m², LB "-", 1 lantai, 2 KT / 1 KM, 1.300 VA / PDAM, Jalan Depan 50 Meter, Stok 20 Unit, Arah Selatan, SHGB, Non Subsidi
- Dokumen: SHGB — "Dokument baru.pdf" (Lihat Detail)
- Lokasi: -6.2775, 106.8444; DKI Jakarta, Kota Jakarta Selatan, Pasar Minggu, Cilandak Timur, Kode Pos 18323, Jl. Pasar Minggu No. 34; tombol Map / Satellite; Aksesibilitas: "Belum ada destinasi"
- Fasilitas: 19 terpasang
- Akurasi Data: rata-rata 98% (Informasi 100%, Harga 100%, Galeri 100%, Legalitas 100%, Lokasi 88,9%, Fasilitas 100%)
- Foto Unit 1 dari 4, Denah / Site Plan
- Seksi "Pengurangan Unit Terjual" terlihat — kontrol +/- dan tombol formulir pengesahan TIDAK disentuh
- Riwayat Aktivitas (3 entri, 13 Nov, superadmin): Aset Dibuat 10:28, Persetujuan Aset 10:34, Status Publish 10:34

## 3. Form Input Aset Baru (dibuka, keluar tanpa isi/simpan) — /create

Wizard 6 langkah: 01 Informasi, 02 Harga, 03 Galeri Foto, 04 Legalitas, 05 Lokasi, 06 Fasilitas.
- Langkah 2–6 DISABLED sampai Langkah 1 selesai — field-nya tidak bisa dilihat tanpa mengisi data (tidak dilakukan)
- Langkah 1 "Informasi": Nama Properti; Kategori Aset (Rumah, Tanah, Ruko, Apartemen, Gudang, Rumah + Ruko); Kode Aset (auto-generated); Tipe Aset; Kode CIF Rekanan (auto dari developer); Kode Developer; Pengembang Mitra (auto); Cabang Pengampu (dropdown); Status Subsidi (Subsidi / Non Subsidi); Klaster (disabled, "Pilih developer dulu"); Jumlah Stok; Alamat Lengkap; Deskripsi Aset (maks 500 karakter)
- Indikator: Langkah 1 dari 6, 17%, Akurasi Data 0%
- Tombol footer (semua disabled saat form kosong): Kembali ke daftar, Simpan Draf, Lanjutkan ke Harga, Simpan & Lanjutkan
- Keluar via breadcrumb "Aset Baru" — tidak ada field yang diisi, tidak ada yang disimpan

## 4. Peta menu Stock Management (sidebar)
Aset Baru · Aset Lelang · Katalog Marketing · Sold out Aset · Favourite Aset Baru · Favourite Aset Lelang · Investor · Approval Aset Baru · Approval Aset Lelang

## 5. Observasi / kandidat perhatian (pasif, belum diverifikasi sebagai bug)
1. Kartu "NONAKTIF / DRAF: 14 Unit Draf" tidak konsisten dengan chip "Draf Pengajuan 3" — angka 14 lebih cocok ke jumlah Belum Publish. Label kartu berpotensi menyesatkan.
2. Chip quick-filter "Stok 0" membingungkan di samping kartu "STOK UNIT TERSEDIA 540 Unit".
3. JKHS-10015 berharga Rp 0 (status Draf) — kualitas data / validasi harga nol layak dicek.
4. Detail MKSS-10010: lokasi Jakarta Selatan tetapi Cabang Pengampu KCS Makassar; Kode Pos 18323 untuk alamat Pasar Minggu/Cilandak Timur juga janggal — kemungkinan data dummy, tetap layak dicatat.
5. Luas Bangunan "-" (kosong) tetapi Akurasi Informasi 100% — rumus akurasi layak dipertanyakan.
6. Menu "Opsi ekspor" hanya berisi "Lihat Status Ekspor" — tidak ada aksi ekspor langsung dari menu itu (ada tombol Unduh Rekap terpisah).

## 6. Kandidat celah TC (untuk dicocokkan ke SIT Internal — belum diverifikasi ke file SIT)
Automation yang sudah ada (TC-INT-STOCK-01) baru menutup skenario Create wizard 6 langkah s.d. submit. Kandidat area yang belum tentu ter-cover:
- List: kombinasi filter bertingkat (Developer → Klaster aktif), Reset filter, quick-filter chips, sorting 4 kolom, reorder kolom, pagination halaman 2
- Publish gating: toggle disabled untuk status belum terverifikasi (sesuai banner aturan publikasi)
- Detail: 6 tab + akurasi data per seksi, riwayat aktivitas, unduh ringkasan
- Wizard gating: langkah 2–6 terkunci sebelum langkah 1 valid; tombol footer disabled saat form kosong; Simpan Draf vs Simpan & Lanjutkan
- Pengurangan Unit Terjual (formulir pengesahan) — area sensitif, hanya dengan data [AUTO-QA] dan izin eksplisit
- Catatan standar BSN: TC pagination memang tidak dibuat per standar tim — kandidat di atas harus disaring mengikuti standar SIT BSN (Expected 1 kalimat, negatif hanya Search & Filter)

## 7. Konfirmasi batas
Hanya navigasi, buka/tutup dropdown (Escape, tanpa memilih), pagination, 1x buka Detail, dan buka/keluar form create via breadcrumb. Tidak ada field diisi; tidak ada tombol simpan/submit/edit/publish/approve/delete/pengurang stok yang diklik. User Management, Role, dan Office Management tidak disentuh. Mailpit tidak dibuka.

---

# FASE 2 — Pendalaman (23 Nov 2026, ±14:51–14:58 WIB, sesi tidak expired)

Mode tetap READ-ONLY (interaksi view/filter/sort/pagination saja). Nol data berubah.

## 8. Hasil uji perilaku list
- Search "Sutera" → 2 hasil (MKSS-10010, MKSS-10005); "MKSS" → 3 hasil; kata kunci ngawur → 0 hasil, empty state "Tidak ada aset yang cocok dengan filter", tanpa baris pagination. Search berjalan setelah debounce singkat; setelah dibersihkan list kembali 19.
- Filter Status Verifikasi cocok semua dengan chips: Draf 3, Menunggu 11, Butuh Revisi 1, Terverifikasi Aktif 4. Opsi "Terverifikasi" (polos) ada di dropdown tapi hasilnya 0 aset.
- Filter Status Publish "Published / Tayang" → 4 (baris yang sama dengan Terverifikasi Aktif).
- Filter Developer "PT Harmoni Properti Nusantara" → 15 aset; dropdown Klaster jadi aktif dengan 4 opsi (Harmoni Garden Residence - Maple Garden, Harmoni Garden Residence - Pine Residence, Samanea Hill Park View - Emerald Hills, Samanea Hill Park View - Lavender Park). Klaster tidak diterapkan.
- Chips sinkron dengan dropdown Status Verifikasi (klik chip mengubah nilai dropdown).
- Pagination normal: halaman 2 "Menampilkan 11–19 dari 19", tombol Sebelumnya/Selanjutnya enable/disable sesuai posisi.

## 9. Temuan kandidat bug (observasi fase 2 — perlu verdict Muhammad)
1. **Chip "Stok" rusak/tidak mengukur stok**: klik chip Stok → 0 hasil, padahal kartu STOK UNIT TERSEDIA = 540 unit. Ternyata chip Stok menyetel filter Status Verifikasi = "Terverifikasi" (polos) yang memang 0 aset.
2. **Sorting Nilai Harga Agunan tidak berfungsi**: diklik berkali-kali (header + panah), urutan tidak berubah sama sekali.
3. **Sorting Kode & Unit Aset urutannya bukan alfabetis**: sekali klik mengacak ke urutan MKSS-10005, MKSS-10011, JKHS-10002, JKHS-10001, JKHS-10011, … — bukan A–Z maupun Z–A.
4. **Reset tidak menghapus sorting**: Reset membersihkan filter/search tapi urutan hasil sort tetap; hanya reload halaman yang mengembalikan urutan default.
5. **JPMS-10001: Status Subsidi tampil teks literal "true"** (bukan "Subsidi"/"Non Subsidi") di halaman detail.
6. **Inkonsistensi hitungan chips**: search mengubah angka chips mengikuti subset hasil, tapi filter dropdown tidak (chips tetap total global).
7. **Kartu "NONAKTIF / DRAF 14"** = Draf 3 + Menunggu Verifikasi 11 — label menyesatkan (sudah dicatat fase 1, terkonfirmasi hitungannya di fase 2).

## 10. Perbandingan detail per status (semua punya tombol & 6 tab yang sama)
- JKHS-10015 (Draf): Harga/DP/Daya/Jalan/Arah kosong, tanpa dokumen/koordinat/foto, Fasilitas 2, Akurasi 21% (Informasi 100%, Harga 0%, Galeri 0%, Legalitas 0%, Lokasi 0%, Fasilitas 25%). Riwayat 2 entri "Draft Aset" duplikat (20 Nov 10:06 & 10:07).
- JPMS-10001 (Menunggu): Harga Rp 450 jt, DP Rp 22,5 jt, KCS Jakarta Ps. Mggu, LT 100/LB 90, 34 unit, Akurasi 77% (Legalitas 0%, Lokasi 88,9%, Fasilitas 75%), tanpa dokumen legal. Riwayat 27 entri, ada 3 entri "Draft Aset" identik di timestamp yang sama.
- JKHS-10004 (Butuh Revisi): Kategori di detail = Apartemen (baris list: Tipe 45/90), Subsidi, 20 unit, Akurasi 77%, Fasilitas 21. Catatan revisi harfiah hanya "s" / Alasan "s". Riwayat 34 entri: pernah "Persetujuan Aset — Siap Tayang" (10 Nov) dan "Status Publish" (12 Nov 13:26), lalu dikembalikan untuk revisi (12 Nov 13:46).

## 11. Deep dive MKSS-10010 (Published)
6 tab ternyata scroll-anchor ke seksi dalam satu halaman panjang, bukan halaman terpisah. "Lihat Detail" dokumen SHGB membuka PDF 1 halaman berisi hanya kata "Contoh" (tab viewer ditutup, tidak diunduh). Aksesibilitas kosong. Sisanya sama dengan catatan fase 1.

## 12. Riwayat Status & Status Ekspor
- Menu "Riwayat Status" TIDAK membuka modal — membuka halaman detail aset di tab baru (riwayat ada di seksi "Riwayat Aktivitas Aset" di bawah detail).
- JKHS-10008 (dibuka via Riwayat Status): Akurasi 100% di semua kategori (satu-satunya), 2 dokumen (AJB, SKM/KUM), tapi destinasi aksesibilitasnya Stasiun/Tol Parung Panjang ±62 km dari lokasi aset di Cibinong.
- "Lihat Status Ekspor" membuka drawer "Download Export" berisi "Belum ada file ekspor." Tidak ada ekspor yang dimulai.

## 13. Scan anomali 19 baris (ringkas)
- JKHS-10015: satu-satunya harga Rp 0; akurasi terendah 21%.
- JPMS-10001: Subsidi "true"; Daya 43 VA; Kode Pos 353636 (6 digit); Kode CIF "-", Kode Developer DEV-INIT-001; riwayat duplikat.
- JKHS-10006: 0 Unit, 0% stok, 0 KT • 2 KM (Draf).
- JKHS-10002: 0 Unit tapi status Menunggu Verifikasi; 6 KT • 6 KM; nama tampil "B3"; lokasi Muaro Jambi.
- MKSS-10005: 0 Unit, 0% stok, tapi Terverifikasi Aktif DAN Published; label tipe kapital semua "TIPE 35/70".
- JKHS-10003: label "Tipe 50/100" tapi LT 72 / LB 36; lokasi Kepulauan Seribu; published termurah Rp 300 jt.
- JKHS-10004: kategori Apartemen vs tipe 45/90; catatan revisi "s".
- 8 baris Harmoni nyaris identik (JKHS-10007 s.d. 10014): properti/spesifikasi/harga sama (Rp 500 jt, 50 unit, Cibinong), beda hanya kode & status verifikasi.
- Semua baris: Terjual = 0 di mana-mana.

---

# FASE 3 — Uji Create + Edit + Read (atas izin eksplisit Muhammad: "cukup create edit read aja", 23 Nov 2026 ±15:03–15:25 WIB)

## Record yang dibuat (LEFTOVER — tidak bisa dihapus, tidak ada fungsi delete)
- **Kode Aset: MKSS-10013** — "Sutera Elok - Cluster Elok A - Tipe A", detail/01M83QYKFYK5692GJ6QBTYMPB6
- Status: **Draf Pengajuan / Belum Publish** (disimpan via "Simpan sebagai Draft" + modal konfirmasi, create & edit). TIDAK pernah di-submit ke verifikasi, TIDAK di-publish.
- Penanda [AUTO-QA] ada di **Deskripsi** (bukan nama — lihat temuan 1): "[AUTO-QA] Eksplor Aset 20261123-1503. Data uji AUTO-QA oleh Muse, 23 Nov 2026. Bukan data real. (revisi AUTO-QA)"
- Dampak ke list: total 19 → 20 aset, nilai Rp 13,8 M → Rp 14,1 M, stok 540 → 547, chip Draf 3 → 4.

## Nilai Create (terverifikasi di detail)
Developer PT. Permata (CIF A1271, DEV-BSN-1271), Proyek Sutera Elok, Klaster Cluster Elok A, Tipe Unit Tipe A, Kategori Rumah, Non Subsidi, LT 120 m², LB -, 1 lantai, 2 KT/1 KM, Harga Rp 350.000.000, DP default 5% → Min. Uang Muka terhitung otomatis Rp 17.500.000, stok awal 5, alamat Jl. AUTO-QA Test No. 1, Jakarta Selatan/Pasar Minggu/Cilandak Timur, KP 12560, koordinat -6.347891, 106.568402 (Pin Manual), Cabang Pengampu KCS Makassar (otomatis), dokumen SHGB (PDF dummy), foto 4 (Fasad wajib + 2 Lainnya + 1 Denah), fasilitas 6, Akurasi 98% (Lokasi 88,9%, sisanya 100%). Riwayat: "Draft Aset, 23 Nov 15:21, M dani Haikal".

## Edit (hanya record ini)
Form edit = wizard 6 langkah yang sama, prefilled. Terkunci saat edit: Developer, Proyek, Klaster, Tipe Unit; field Kode Aset disabled (placeholder JKHS-XXXX, kode tampil di heading). Diubah: **Stok 5 → 7** dan Deskripsi ditambah " (revisi AUTO-QA)", simpan sebagai draf lagi. Read ulang terverifikasi: detail tampil 7 Unit, riwayat 2 entri (15:21 create, 15:23 edit), status tetap DRAFT.

## Temuan fase 3 (kandidat issue)
1. **Tidak ada field Nama Properti bebas** — nama aset diturunkan dari master data (Developer → Proyek → Klaster → Tipe Unit). Konsekuensi: penanda [AUTO-QA] tidak bisa jadi nama; **Deskripsi tidak tampil di halaman detail dan tidak terindeks search** (search "[AUTO-QA]" = 0 hasil; ketemu hanya via kode MKSS-10013 atau buka form Edit). Pelacakan data uji jadi sulit.
2. **Wizard menyimpan state hanya di memori** — satu panggilan upload gagal membuat isi Langkah 1–2 hilang total dan harus diulang dari awal.
3. **Langkah 3 wajib minimum 4 foto DAN 1 kategori "Denah / Site Plan"** — tombol Selanjutnya diblokir dengan toast sampai syarat itu terpenuhi.
4. **Langkah 4: checkbox SHM ikut tercentang sendiri** saat PDF diunggah ke SHGB (counter sempat "2 dari 10"), harus di-untick manual.
5. **Koordinat GPS wajib diisi tapi placeholder terlihat seperti nilai terisi** ("-6.347891, 106.568402" hanyalah placeholder); "Deteksi Titik Otomatis" gagal di browser tanpa izin lokasi.
6. **Simpan draf lambat** — unggah 4 PNG 70-byte > 1 menit; tanpa toast sukses (keberhasilan hanya terlihat dari redirect + verifikasi detail).
7. Validasi Langkah 1 lengkap per-field ("…wajib dipilih/diisi") + toast "Lengkapi data yang wajib diisi terlebih dahulu" — perilaku validasi normal.
8. Semua 10 jenis dokumen legalitas (AJB, SKM/KUM, PH, Girik, IMB/PBG, PBB, PK, SHGB, SHM, SPH) bersifat opsional di wizard.

---

# FASE 4 — Penuntasan (perintah Muhammad via WhatsApp, 23 Nov 2026 ±16:08–16:15 WIB)

Hanya record sendiri MKSS-10013 yang diubah; data existing tetap read-only. Tidak ada yang di-submit ke verifikasi, tidak ada yang di-publish, tidak ada Setujui/Tolak yang diklik.

## 14. Hasil per item
1. **Salin Kode Aset** — berfungsi: toast hijau "Kode JKHS-10008 disalin", list tidak berubah.
2. **Catatan Butuh Revisi (JKHS-10004)** — TIDAK ada banner/seksi khusus revisi di detail. Catatan hanya muncul sebagai entri pertama "Riwayat Aktivitas Aset" ("Revisi Aset, 12 Nov 13:46 — Catatan: s / Alasan: s") + badge REVISI. Riwayat penuh: 34 entri.
3. **Edge case wizard (draft sendiri, semua direstore & terverifikasi: stok 7, DP 5%, deskripsi utuh)**:
   - Stok 0 → DIBLOKIR "Selanjutnya": toast + inline "Isi angka bulat minimal 1".
   - DP 0% diterima (Min. DP Rp 0); DP 30% diterima (Rp 105.000.000); ketik 35% → **di-clamp diam-diam ke 30%** tanpa pesan (sempat tampil nilai antara 3%/Rp 10,5 jt saat mengetik).
   - Deskripsi dikosongkan → DIBLOKIR: "Deskripsi aset wajib diisi".
4. **Pengurangan Unit Terjual (MKSS-10013)** — form pengesahan terpetakan penuh: tabel blok kavling (wajib), No. Registrasi SPR (wajib), Tanggal Closing/Akad (wajib, date picker), radio Saluran Penjualan (4 opsi: KPR Bank Lain, Cash Keras, Cash Bertahap In-House, Agen Eksternal), upload bukti (PDF/JPG/PNG maks 10 MB). Data dummy diajukan (Blok AUTO-QA-01, SPR-AUTOQA/XI/2026-001, 23/11/2026, Cash Keras, PDF dummy). Hasil: **PENDING verifikasi** — muncul garis merah "1 unit masih menunggu verifikasi pengurangan." di detail; angka stok BELUM berubah (Total 7, proyeksi sisa 6, list tetap 7 Stok/0 Terjual); **tidak ada entri Riwayat baru**. Pengajuan ini sekarang ikut mengantre di tab "Approval Pengurangan Unit" (total antrean tab itu: 2 — 1 punya kita, 1 sudah ada sebelumnya).
5. **"Selesai dan Ajukan Aset"** — TIDAK diklik (analisis saja). Di mode Edit, tombol submit langkah 6 bernama **"Simpan dan Ajukan Perubahan"**; label "Selesai dan Ajukan Aset" hanya ada di wizard Create. Tidak ada indikator akurasi/prasyarat yang tampil di langkah 6 selain asterisk fasilitas. Mengkliknya = menyimpan + mengajukan ke verifikasi (masuk antrean Approval tim) — keputusan terpisah untuk Muhammad.
6. **Approval Aset Baru (view-only)** — /internal/stock-management/approval/aset-baru: 2 tab mode (Approval Input Aset 16, Approval Pengurangan Unit 2), kartu: Total Pengajuan 16 (Rp 12,485 M), Menunggu 11, Disetujui 4, Butuh Revisi/Ditolak 1. Filter lengkap (search, Developer, Klaster dependen, Tipe Aset, Harga Min/Maks, rentang tanggal, Kode Aset, Reset + Terapkan Filter). Tabel 8 kolom; baris Menunggu punya aksi Detail + Setujui + Tolak; baris Terverifikasi hanya Detail. Draft kita MKSS-10013 TIDAK ada di antrean (16 = 20 aset − 4 draf), konsisten tidak pernah diajukan.

## 15. Temuan baru fase 4 (kandidat issue tambahan)
13. **"Simpan sebagai Draft" tanpa pre-validasi** — modal konfirmasi tetap muncul saat Stok 0 (invalid); kalau dikonfirmasi, draf invalid bisa tersimpan (diuji sampai modal saja, dibatalkan).
14. **DP di atas 30% di-clamp diam-diam** tanpa pesan kesalahan.
15. **Field tanggal pengurangan menolak tanggal yang diketik** (flag invalid) — hanya mau lewat date picker.
16. **Pengajuan pengurangan tidak tercatat di Riwayat Aktivitas** — jejak satu-satunya garis pending di seksi Pengurangan detail.
17. **List Approval: kolom Spesifikasi & Jumlah Unit semua "-"** ("Rumah LT - / LB -", "- Tersedia: -") untuk semua baris, padahal di list Aset Baru nilainya ada — kurator menilai tanpa data kunci.
18. **Nama file foto hilang di mode Edit** — foto tampil sebagai "origin.png / Tersimpan", nama asli tidak dipertahankan.
19. Catatan revisi tidak punya seksi/banner khusus di detail (minor, UX) — terkubur di Riwayat.

## 16. PETA COVERAGE FINAL — Stock Management / Aset Baru
**Sudah ter-cover:**
- List: search (positif + empty state), semua filter + kombinasi Developer→Klaster, quick chips, sorting (4 kolom), reorder kolom (observasi), pagination, reset
- Aksi baris: Detail, Salin Kode Aset (toast), Riwayat Status (membuka detail), menu titik tiga
- Detail: 6 tab/seksi pada 4 status berbeda (Published, Draf, Menunggu, Butuh Revisi), akurasi data, riwayat aktivitas penuh, dokumen viewer, peta
- Create: wizard 6 langkah penuh, validasi per-field, simpan draf + modal konfirmasi, hitung DP otomatis
- Edit: wizard prefilled, field terkunci, simpan draf
- Edge case: stok 0, DP 0%/30%/di atas maks, field wajib dikosongkan
- Pengurangan Unit Terjual: form pengesahan lengkap + pengajuan (status pending terverifikasi)
- Approval Aset Baru: peta halaman, filter, kolom, aksi yang terlihat (view-only)
- Ekspor: drawer status ekspor (view-only)

**Belum ter-cover + alasan:**
- Submit pengajuan aset ("Selesai dan Ajukan Aset" / "Simpan dan Ajukan Perubahan") — mengubah status masuk antrean verifikasi tim; menunggu keputusan Muhammad
- Approve/Tolak di Approval Input Aset & Approval Pengurangan Unit — state-changing pada antrean (termasuk menyetujui pengurangan kita sendiri); menunggu keputusan Muhammad
- Efek stok setelah pengurangan disetujui — bergantung pada approval di atas
- Toggle publish/unpublish — state-changing pada data existing
- Unduh Rekap / Unduh Ringkasan / unduh file ekspor — aksi unduhan tidak dieksekusi selama eksplorasi
- Delete — tidak ada fungsinya di UI

## 17. Keadaan akhir record uji
MKSS-10013 tetap Draf Pengajuan / Belum Publish, stok total 7, DP 5% (Rp 17.500.000), harga Rp 350.000.000, deskripsi utuh, riwayat 3 entri Draft, + 1 pengurangan 1 unit berstatus MENUNGGU VERIFIKASI di antrean Approval Pengurangan Unit. Total list: 20 aset, Rp 14,1 M, stok 547, Published 4, Menunggu 11, Butuh Revisi 1 — data existing lain tidak berubah.

---

# ADDENDUM — Verdict Muhammad atas kandidat issue (23 Nov 2026 sore)
- Issue "Chip Stok": **diubah arahnya atas verdict Muhammad** — perilaku tabel/filter dianggap sudah benar; yang dijadikan issue adalah **TOTAL pada kartu "STOK UNIT TERSEDIA"** (547/540) yang menghitung unit dari seluruh status aset padahal berlabel "Stok Unit Katalog". Draft bug report 01 sudah ditulis ulang mengikuti verdict ini (folder bug-report-drafts/01 - Kartu Stok Unit Tersedia Tidak Konsisten).
- 5 draft bug report prioritas dibuat di ~/workspace/bsn/bug-report-drafts/ (report.md + report.txt + komentar_huly.txt kosong + screenshot asli & versi kotak merah dari snapshot sesi browser). Belum dinaikkan ke Huly/Catbox — menunggu ACC Muhammad.
- Bug SHM: tidak ter-reproduksi di alur Edit; atas izin khusus Muhammad ("cuma untuk kali ini untuk nangkep ss-nya") dilakukan satu kali repro lewat alur Create khusus untuk menangkap screenshot buktinya.
- Hasil repro SHM (23 Nov ±16:36–16:39 WIB, izin khusus satu kali): alur Create penuh, urutan centang SHGB dulu lalu unggah PDF — SHM **TIDAK** tercentang, counter tetap "1 dari 10". Wizard dibuang tanpa disimpan (total aset tetap 20). Total uji ulang gagal repro: 2x (Edit & Create). Varian belum teruji: unggah saat checkbox SHGB belum dicentang. Draft 05 ditandai "jangan dinaikkan sebelum varian itu diuji".
- Audit sorting menyeluruh (23 Nov 17:00–17:06 WIB, atas permintaan Muhammad, read-only, metode catat urutan baris sebelum/sesudah 2x klik + baca ulang): **0 dari 12 kolom sortable berfungsi benar.** Aset Baru: Harga MATI, Developer & Proyek MATI (temuan baru), Kode ACAK (klik 2 bukan kebalikan klik 1), Status Verifikasi ACAK + tidak toggle (klik 2 = klik 1, temuan baru). Approval Aset Baru: SEMUA kolom mati, termasuk Harga Pengajuan (satu-satunya yang berikon sort) dan Tanggal Diajukan. Mengonfirmasi temuan Muhammad sendiri di menu Approval.
