# Regression Test - BSN Fase 1

Tracking progres regression test dan bug yang ditemukan selama sesi pengetesan.
**PIC QA**: Dani | **Tanggal Mulai**: 2026-10-23

---

## 📊 Progress Summary

| No | Menu | Sub Menu | Status |
|----|------|----------|--------|
| 1 | Authentication | Logout | 🐞 Bug |
| 2 | Authentication | Login | 🐞 Bug |
| 3 | User Management | Role | 🐞 Bug |
| 4 | User Management | User | 🐞 Bug & 🟢 Done |
| 5 | Office Management | Office Type | 🐞 Bug |
| 6 | Authentication (External) | Register Nasabah | 🐞 Bug |
| 7 | Authentication (External) | Login | 🐞 Bug |
| 8 | Beranda (External) | Home Page | 🐞 Bug |
| 9 | Developer | List Developer | 🐞 Bug |
| 10 | Media & Information | FAQ | 🐞 Bug |
| 11 | Media & Information | Article | 🐞 Bug |
| 12 | Media & Information | Banner Setting | 🐞 Bug |
| 13 | User Management | User Block | 🐞 Bug |
| 14 | User Management | User External | 🐞 Bug |
| 15 | Stock Management | Aset Baru | 🐞 Bug |
| 16 | Aset Baru (External) | Filter Pencarian | 🐞 Bug |
| 17 | Aset Baru (External) | Card Aset | 🐞 Bug |
| 18 | Aset Baru (External) | Detail Aset | 🐞 Bug |
| 19 | Simulasi Pembiayaan (External) | Form Simulasi | 🐞 Bug |
| 20 | Daftar Developer (External) | Card Developer | 🐞 Bug |
| 21 | Stock Management | Approval Aset Baru | 🐞 Bug |
| 22 | Aset Baru (External) | Katalog | 🐞 Bug |
| 23 | Aset Baru (External) | Form Pengajuan Peminatan | 🐞 Bug |
| 24 | Stock Management | Leads Aset Baru | 🐞 Bug |
| 25 | Stock Management | Tiket Aset Baru | 🐞 Bug |

---

## 📌 Status Input Issue ke Huly

| No | Modul / Sub Menu | Total Bug | Status Huly | Rincian Issue |
|----|------------------|-----------|-------------|---------------|
| 1 | **Authentication** | 4 | ⏳ Pending (0/4) | Logout (2), Login (1), Lupa Kata Sandi (1) |
| 2 | **User Management** | 9 | ⏳ Pending (0/9) | Role (4), User (2), User Block (2), User External (1) |
| 3 | **Office Management** | 3 | ⏳ Pending (0/3) | Office Type (3) |
| 4 | **Developer** | 3 | ⏳ Pending (0/3) | List Developer (3) |
| 5 | **Media & Information** | 3 | ⏳ Pending (0/3) | FAQ (1), Article (1), Banner Setting (1) |
| 6 | **Authentication (External)** | 13 | ⏳ Pending (0/13) | Register Nasabah (4), Login (7), Lupa Kata Sandi (2) |
| 7 | **Beranda (External)** | 2 | ⏳ Pending (0/2) | Header (2) |
| 8 | **User Profile (External)** | 1 | ⏳ Pending (0/1) | Profile Tabs (1) |
| 9 | **Stock Management** | 14 | ✅ Reported (6/14) | Aset Baru (11), Approval Aset Baru (3) — 6 issue sudah diinput ke Huly: BSN_I-169 s.d. BSN_I-174 |
| 10 | **Aset Baru (External)** | 5 | ✅ Reported (2/5) | Filter Pencarian (1), Card Aset (1), Detail Aset (1), Katalog (1) — HULY-109, Form Pengajuan Peminatan (1) — HULY-110 |
| 11 | **Simulasi Pembiayaan (External)** | 1 | ⏳ Pending (0/1) | Form Simulasi (1) |
| 12 | **Daftar Developer (External)** | 1 | ⏳ Pending (0/1) | Card Developer (1) |
| 13 | **Leads & Tiket Aset Baru** | 6 | ✅ Reported (6/6) | Tiket Aset Baru (3) — BSN_I-182 s.d. BSN_I-184, Leads Aset Baru (3) — BSN_I-185 s.d. BSN_I-187 |
| **Total** | | **65** | **14 Reported / 51 Pending** | |

---

## 🏷️ Matriks Status Issue QA

| Status | Total | Rincian Issue |
|--------|:-----:|---------------|
| 🟢 **Done** | 1 | `Internal/User Management/User/01`: Dropdown Kantor pada Form Tambah User Kosong |
| 🔴 **Open** | 59 | 41 Issue Internal, 18 Issue External |
| 🟡 **Catatan / Klarifikasi** | 2 | • `External/Authentication/Register Nasabah/03`: Validasi Kata Sandi Breached Muncul di Akhir<br>• `External/Authentication/Login/05`: Label Banner Login External Tertulis Sistem Portal Internal |
| 🔄 **Re-Open** | 3 | • `External/Aset Baru/Card Aset/01`: Informasi Developer & Harga Coret Belum Sesuai<br>• `External/Aset Baru/Filter Pencarian/01`: Filter Jenis Properti Belum Berfungsi<br>• `External/Daftar Developer/Card Developer/01`: Logo, Segmen, dan Jumlah Aset Belum Sesuai |

---

### 🐞 [BUG] | Field Nama / Nomor Unit Aset Belum Diganti Menjadi Stok Unit

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Field "Nama / Nomor Unit Aset" pada form tambah Aset Baru masih tampil di aplikasi, padahal di desain Figma sudah diganti menjadi field "Stok Unit" beserta helper text "Jumlah Stok Unit".
> * **Expected**: Field "Stok Unit" dengan helper text "Jumlah Stok Unit" tampil sesuai desain Figma
> * **Actual**: Field "Nama / Nomor Unit Aset" dengan placeholder "Contoh: Blok B3 No. 12" masih tampil
> * **Evidence Awal**:
>   * Figma Stok Unit: [https://files.catbox.moe/pie7mg.png](https://files.catbox.moe/pie7mg.png)
>   * App Nama Nomor Unit: [https://files.catbox.moe/yaqejq.png](https://files.catbox.moe/yaqejq.png)
<br>

### 🐞 [BUG] | Gagal Menambah Aset Baru Muncul Error

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Sistem memunculkan error "Oops something went wrong" saat user menekan tombol "Selesai dan Ajukan Aset", sehingga proses penambahan aset baru gagal disimpan.
> * **Expected**: Aset baru berhasil diajukan dan tersimpan ke sistem tanpa memunculkan pesan error
> * **Actual**: Muncul toast error "Oops something went wrong, Contact Developer for the issue" dengan Support ID: 88f79a1f1f4b8aa999a25427101dc922
> * **Evidence Awal**:
>   * Toast Error Ajukan Aset: [https://files.catbox.moe/ugr7f1.png](https://files.catbox.moe/ugr7f1.png)
<br>

### 🐞 [BUG] | Gagal Menyimpan Draf Aset Baru Muncul Error

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Sistem memunculkan error "Oops something went wrong" saat user menekan tombol "Simpan sebagai Draft", sehingga draf aset baru gagal disimpan.
> * **Expected**: Draf aset baru berhasil disimpan ke sistem tanpa memunculkan pesan error
> * **Actual**: Muncul toast error "Oops something went wrong, Contact Developer for the issue" dengan Support ID: 53ee322503b6b74edde680b93f606f95
> * **Evidence Awal**:
>   * Toast Error Simpan Draf: [https://files.catbox.moe/rbbzha.png](https://files.catbox.moe/rbbzha.png)
<br>

### 🐞 [BUG] | Urutan dan Waktu Riwayat Aktivitas Aset Tidak Sesuai

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Timeline pada Riwayat Aktivitas Aset tidak menampilkan urutan dan waktu yang sesuai, di mana aktivitas terbaru seperti "Menunggu Verifikasi" setelah edit aset justru tampil di bawah dan jamnya tidak ter-update.
> * **Expected**: Riwayat Aktivitas Aset terurut kronologis dari aktivitas terbaru di paling atas dengan tanggal dan jam yang akurat
> * **Actual**: Aktivitas baru "Menunggu Verifikasi" tampil di bawah status "Terverifikasi" lama dan jamnya tidak ter-update sesuai waktu edit (hanya status "Terverifikasi" yang urutan dan jamnya benar)
> * **Evidence Awal**:
>   * Urutan Riwayat Aktivitas Salah: [https://files.catbox.moe/6goyhu.png](https://files.catbox.moe/6goyhu.png)
<br>

### 🐞 [BUG] | Label Dokumen Legalitas pada Detail Aset Belum Sesuai Berkas yang Dipilih

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Pada section Dokumen Legalitas & Perizinan di detail aset, kartu berkas yang diunggah hanya menampilkan label statis "Dokumen", bukan nama jenis berkas legalitas yang dipilih saat penginputan (seperti "Akta Jual Beli (AJB)" atau "Akta Kuasa Menjual (SKM/KUM)").
> * **Expected**: Setiap kartu berkas menampilkan nama jenis dokumen legalitas yang sesuai dengan pilihan saat upload (misal: "Akta Jual Beli (AJB)" dan "Akta Kuasa Menjual (SKM/KUM)")
> * **Actual**: Seluruh kartu berkas hanya menampilkan label umum statis "Dokumen"
> * **Evidence Awal**:
>   * Form Pilihan Berkas Legalitas: [https://files.catbox.moe/onrymc.png](https://files.catbox.moe/onrymc.png)
>   * Detail Aset Label Dokumen: [https://files.catbox.moe/4e7ege.png](https://files.catbox.moe/4e7ege.png)
<br>

### 🐞 [BUG] | Field Spesifikasi Dimensi dan Ruang Utama Belum Memiliki Tanda Bintang

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Pada form tambah Aset Baru section Spesifikasi Dimensi & Ruang Utama, field Luas Tanah, Jumlah Lantai, Kamar Tidur, dan Kamar Mandi tidak menampilkan tanda bintang merah (*), padahal seluruh field tersebut bersifat wajib diisi (mandatory) dan memicu validasi error "Wajib diisi".
> * **Expected**: Seluruh label field mandatory (Luas Tanah, Jumlah Lantai, Kamar Tidur, dan Kamar Mandi) menampilkan tanda bintang merah (*) penanda wajib diisi
> * **Actual**: Label field Luas Tanah, Jumlah Lantai, Kamar Tidur, dan Kamar Mandi tidak memiliki tanda bintang merah (*), meskipun memunculkan pesan validasi "Wajib diisi"
> * **Evidence Awal**:
>   * Field Tanpa Bintang Mandatory: [https://files.catbox.moe/u6o9ia.png](https://files.catbox.moe/u6o9ia.png)
<br>

### 🐞 [BUG] | Fitur Search pada Field Tipe Aset dan Pilihan Klaster Bermasalah

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Terdapat kendala pada fitur pencarian form Aset Baru: search pada field Tipe Aset belum berfungsi (opsi tidak terfilter saat mengetik), dan belum tersedia fitur search pada field Pilihan Klaster.
> * **Expected**: Pencarian pada field Tipe Aset berfungsi memfilter opsi dropdown, dan field Pilihan Klaster menyediakan fitur search
> * **Actual**: Search pada field Tipe Aset belum berfungsi memfilter data, serta field Pilihan Klaster belum memiliki fitur search
> * **Evidence Awal**:
>   * Search Tipe Aset Tidak Berfungsi: [https://files.catbox.moe/wwbw8q.png](https://files.catbox.moe/wwbw8q.png)
>   * Pilihan Klaster Tanpa Search: [https://files.catbox.moe/zpu7zl.png](https://files.catbox.moe/zpu7zl.png)
<br>

### 🐞 [BUG] | Urutan Opsi Dropdown Tipe Aset Belum Sesuai Ketentuan

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Overview**: Urutan opsi pada dropdown Tipe Aset belum sesuai aturan prioritas 3 teratas (1. Rumah, 2. Apartemen, 3. Ruko). Saat ini urutan opsi pada sistem masih menampilkan Apartemen, Gedung Kantor, Gudang, Hotel, dst.
> * **Expected**: Tiga opsi teratas pada dropdown Tipe Aset berurutan: 1. Rumah, 2. Apartemen, 3. Ruko (diikuti tipe aset lainnya)
> * **Actual**: Urutan opsi dropdown Tipe Aset belum sesuai aturan prioritas (menampilkan Apartemen, Gedung Kantor, Gudang, dst.)
> * **Evidence Awal**:
>   * Urutan Dropdown Tipe Aset: [https://files.catbox.moe/8n0yoi.png](https://files.catbox.moe/8n0yoi.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

### 🐞 [BUG] | Total pada Card Stok Unit Tersedia Tidak Sesuai

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Huly**: BSN_I-169 (sudah diinput ke Huly)
> * **Overview**: Card "STOK UNIT TERSEDIA" di halaman Aset Baru menulis total 547 unit sebagai stok katalog. Padahal angka itu adalah jumlah unit dari semua aset, termasuk yang masih Draf dan belum tayang di katalog. Jadi angka di card lebih besar dari stok yang sebenarnya tersedia.
> * **Expected**: Card STOK UNIT TERSEDIA menampilkan total unit yang benar-benar tersedia di katalog (aset Terverifikasi / Published)
> * **Actual**: Card menampilkan 547 unit, yaitu total unit dari semua status aset termasuk Draf dan Menunggu Verifikasi
> * **Evidence Awal**:
>   * Card Stok 547: evidence_01_chip_stok.png (file lokal di folder issue `Internal/Stock Management/Aset Baru/09`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Sorting pada Tabel Aset Baru dan Approval Aset Baru Tidak Berfungsi

> * **Menu**: Stock Management → Aset Baru dan Approval Aset Baru
> * **Status**: Open
> * **Huly**: BSN_I-170 (sudah diinput ke Huly)
> * **Overview**: Tombol urutkan (sorting) di tabel Aset Baru dan tabel Approval Aset Baru tidak bekerja. Ada yang diklik tapi urutannya tidak berubah sama sekali, ada juga yang berubah tapi urutannya acak. Dari 12 kolom yang dicoba di kedua tabel, tidak ada satu pun yang mengurutkan dengan benar.
> * **Expected**: Setiap kolom berikon sort mengurutkan baris dengan benar, klik pertama menaik dan klik kedua menurun
> * **Actual**: Harga dan Developer mati total, Kode dan Status Verifikasi acak, dan seluruh kolom di Approval Aset Baru mati total
> * **Evidence Awal**:
>   * Header Sorting Harga: evidence_01_sorting_harga.png (file lokal di folder issue `Internal/Stock Management/Aset Baru/10`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Stok 0 Tetap Bisa Disimpan sebagai Draf pada Edit Aset Baru

> * **Menu**: Stock Management → Aset Baru
> * **Status**: Open
> * **Huly**: BSN_I-172 (sudah diinput ke Huly)
> * **Overview**: Saat mengedit aset, stok diisi 0 itu sebenarnya tidak boleh — tombol Selanjutnya saja yang menolaknya. Tapi tombol "Simpan sebagai Draft" tidak ikut memeriksa: modal konfirmasi tetap muncul dan draf dengan stok 0 tetap bisa disimpan.
> * **Expected**: Tombol Simpan sebagai Draft menjalankan validasi yang sama seperti tombol Selanjutnya dan menolak penyimpanan stok 0
> * **Actual**: Modal konfirmasi simpan draf tetap muncul meskipun stok 0, sehingga draf tidak valid dapat disimpan
> * **Evidence Awal**:
>   * Modal Konfirmasi Stok 0: evidence_01_simpan_draf_stok0.png (file lokal di folder issue `Internal/Stock Management/Aset Baru/11`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Value pada Kolom Spesifikasi Unit dan Jumlah Unit di Menu Approval Aset Baru Belum Tampil

> * **Menu**: Stock Management → Approval Aset Baru (Tab Pengajuan Masuk)
> * **Status**: Open
> * **Huly**: BSN_I-171 (sudah diinput ke Huly)
> * **Overview**: Di daftar Approval Aset Baru, kolom SPESIFIKASI UNIT dan JUMLAH UNIT isinya hanya tanda strip di semua baris. Padahal data aslinya ada, misalnya luas tanah/bangunan dan jumlah unit tampil normal di halaman Aset Baru dan di halaman detail.
> * **Expected**: Kolom SPESIFIKASI UNIT menampilkan LT/LB dan kolom JUMLAH UNIT menampilkan jumlah unit sesuai data aset
> * **Actual**: Kedua kolom tampil tanda strip di seluruh 16 baris antrean
> * **Evidence Awal**:
>   * Kolom Approval Strip: evidence_01_approval_kolom_kosong.png (file lokal di folder issue `Internal/Stock Management/Approval Aset Baru/01`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Filter pada Menu Approval Aset Baru Menampilkan Hasil Kosong

> * **Menu**: Stock Management → Approval Aset Baru (Tab Pengajuan Masuk)
> * **Status**: Open
> * **Huly**: BSN_I-173 (sudah diinput ke Huly)
> * **Overview**: Filter di menu Approval Aset Baru tidak bisa dipercaya, ada 3 kejadian: (1) Tab "Disetujui" menulis ada 4 pengajuan, tapi saat diklik daftarnya kosong, (2) Filter tipe "Rumah" hasilnya kosong, padahal semua 16 pengajuan tipenya Rumah, (3) Pencarian di tab Pengajuan ikut mengubah angka di tab Pengurangan Unit dari 2 menjadi 0, padahal tab itu tidak sedang diutak-atik.
> * **Expected**: Tab Disetujui menampilkan 4 pengajuan, filter Rumah menampilkan 16 pengajuan, dan pencarian di tab Pengajuan tidak mengubah angka tab Pengurangan Unit
> * **Actual**: Tab Disetujui dan filter Rumah menghasilkan 0 baris, pencarian "JPMS" mengubah angka tab Pengurangan Unit dari 2 menjadi 0, dan tombol Reset tidak membersihkan tab status yang aktif
> * **Evidence Awal**:
>   * Tab Disetujui Kosong: evidence_01_chip_disetujui.png (file lokal di folder issue `Internal/Stock Management/Approval Aset Baru/02`, drag & drop ke Huly)
>   * Filter Rumah Kosong: evidence_02_filter_tipe_aset.png (file lokal di folder issue yang sama, drag & drop ke Huly)
>   * Search Bocor Antar Tab: evidence_03_search_bocor_antar_tab.png (file lokal di folder issue yang sama, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | File Bukti pada Approval Pengurangan Unit Tidak Bisa Dibuka

> * **Menu**: Stock Management → Approval Aset Baru (Tab Pengurangan Unit)
> * **Status**: Open
> * **Huly**: BSN_I-174 (sudah diinput ke Huly)
> * **Overview**: Di tab Approval Pengurangan Unit, file bukti penjualan (SPR/kuitansi) hanya tampil sebagai nama file biasa yang tidak bisa diklik, dan tidak ada tombol untuk melihat detailnya. Jadi reviewer tidak bisa membuka bukti sama sekali, tapi tetap harus memilih Setujui atau Tolak.
> * **Expected**: Nama file bukti dapat diklik untuk dibuka/diunduh, atau tersedia tombol Detail untuk memeriksa bukti sebelum memutuskan
> * **Actual**: Nama file hanya teks mati dan tidak ada tombol Detail; satu-satunya aksi pada baris adalah Setujui dan Tolak
> * **Evidence Awal**:
>   * Bukti Pengurangan Teks Mati: evidence_01_bukti_pengurangan.png (file lokal di folder issue `Internal/Stock Management/Approval Aset Baru/03`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Tiket Tidak Terbentuk setelah Lead Ditindaklanjuti (BSN_I-182)

> * **Menu**: Stock Management → Tiket Aset Baru
> * **Status**: Open
> * **Overview**: Lead tes #ENT-01m8-8153 yang sudah ditindaklanjuti dan berstatus Terverifikasi tidak membentuk tiket di Tiket Aset Baru, baik di Board, Tabel, maupun pencarian.
> * **Expected**: Setelah lead Terverifikasi, tiket terbentuk otomatis di Tiket Aset Baru dan lead dapat diproses ke tahap berikutnya
> * **Actual**: Tidak ada tiket untuk lead tes di Board, Tabel, maupun pencarian Tiket Aset Baru
> * **Evidence Awal**:
>   * Tiket Tidak Terbentuk: evidence_01_tiket-tidak-terbentuk_redbox.png (file lokal di folder issue `Internal/Stock Management/Tiket Aset Baru/01`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Nomor Tiket Duplikat pada Dua Lead Berbeda (BSN_I-183)

> * **Menu**: Stock Management → Tiket Aset Baru
> * **Status**: Open
> * **Overview**: Lead tes #ENT-01m8-8153 dan lead Elina sama-sama menampilkan nomor tiket #TKT-2024-0891. Tahun pada nomor tiket adalah 2024, padahal lead dibuat tahun 2026.
> * **Expected**: Setiap lead / tiket memiliki nomor tiket unik yang berbeda, dengan tahun sesuai tahun pembuatan
> * **Actual**: Kedua lead menampilkan nomor tiket yang sama: #TKT-2024-0891
> * **Evidence Awal**:
>   * Nomor Tiket Duplikat: evidence_02_nomor-tiket-duplikat_redbox.png (file lokal di folder issue `Internal/Stock Management/Tiket Aset Baru/02`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Kolom Nomor Tiket Menampilkan ID Lead dan Card VOA Menampilkan Rp0 (BSN_I-184)

> * **Menu**: Stock Management → Tiket Aset Baru
> * **Status**: Open
> * **Overview**: Kolom Nomor Tiket pada tabel Tiket menampilkan ENT-01m7-2727, yaitu ID lead Elina, bukan nomor tiket. Card VOA Nilai Tiket Aset Baru menampilkan Rp0, padahal ada tiket Elina senilai Rp300.000.000 yang sedang tahap Proses.
> * **Expected**: Kolom Nomor Tiket menampilkan nomor tiket (format #TKT-...) dan card VOA menampilkan total nilai tiket aktif (Rp300.000.000)
> * **Actual**: Kolom Nomor Tiket menampilkan ID lead ENT-01m7-2727 dan card VOA menampilkan Rp0
> * **Evidence Awal**:
>   * Nomor Tiket ID Lead: evidence_08_nomor-tiket-id-lead-voa-nol_redbox.png (file lokal di folder issue `Internal/Stock Management/Tiket Aset Baru/03`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Simulasi DP dan Angsuran pada Drawer Leads Tidak Sesuai Harga Aset (BSN_I-185)

> * **Menu**: Stock Management → Leads Aset Baru
> * **Status**: Open
> * **Overview**: Nilai simulasi DP dan angsuran pada drawer Leads sama untuk harga aset yang berbeda: lead tes (aset Rp500.000.000) dan lead Elina (aset Rp300.000.000) sama-sama tampil DP Rp85.000.000 dan angsuran Rp6.380.000/bln. Nilai yang benar untuk lead tes: DP 10% x Rp500.000.000 = Rp50.000.000; sebagai pembanding, detail tiket Elina menampilkan angka yang benar (DP Rp30.000.000).
> * **Expected**: DP tampil 10% dari harga aset masing-masing lead (lead tes Rp50.000.000, Elina Rp30.000.000) dan angsuran dihitung dari plafon serta tenor lead tersebut
> * **Actual**: Kedua lead menampilkan DP Rp85.000.000 dan angsuran Rp6.380.000/bln yang sama persis
> * **Evidence Awal**:
>   * Simulasi DP Sama: evidence_03_simulasi-dp-dummy_redbox.png (file lokal di folder issue `Internal/Stock Management/Leads Aset Baru/01`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Card Perlu Tindak Lanjut Tidak Berubah setelah Tindak Lanjut Disimpan (BSN_I-186)

> * **Menu**: Stock Management → Leads Aset Baru
> * **Status**: Open
> * **Overview**: Setelah tindak lanjut lead tes disimpan, tab berubah benar menjadi Tindak Lanjut 2 / Terverifikasi 2, tapi card Perlu Tindak Lanjut tetap menampilkan 4 dengan keterangan "2 SLA Kritis" (harusnya 2). Card juga tidak berubah saat filter dipakai: tetap 4 walaupun hasil filter 0 lead.
> * **Expected**: Card Perlu Tindak Lanjut ikut berubah mengikuti data terbaru (menjadi 2, sama seperti tab Tindak Lanjut)
> * **Actual**: Card tetap menampilkan 4 ("2 SLA Kritis") setelah tindak lanjut disimpan, dan tetap 4 saat hasil filter 0 lead
> * **Evidence Awal**:
>   * Card Tidak Berubah: evidence_04_kartu-tindak-lanjut-tidak-update_redbox.png (file lokal di folder issue `Internal/Stock Management/Leads Aset Baru/02`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Sorting pada Tabel Leads Hanya Berfungsi di 2 Kolom (BSN_I-187)

> * **Menu**: Stock Management → Leads Aset Baru
> * **Status**: Open
> * **Overview**: Sorting pada tabel Leads hanya tersedia di 2 kolom: ID Pesanan dan Kode Asset. Kolom Peminat, Waktu Peminatan, dan Status Lead tidak memiliki kontrol sorting.
> * **Expected**: Kolom Peminat, Waktu Peminatan, dan Status Lead memiliki kontrol sorting seperti kolom ID Pesanan dan Kode Asset
> * **Actual**: Sorting hanya ada di kolom ID Pesanan dan Kode Asset; tiga kolom lain tidak memiliki kontrol sorting
> * **Evidence Awal**:
>   * Sorting Terbatas: evidence_06_sorting-terbatas_redbox.png (file lokal di folder issue `Internal/Stock Management/Leads Aset Baru/03`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

---

## 🐞 Bug Report / Isu Temuan

### 🐞 [BUG] | Gagal Logout Akun dan Muncul Halaman Error

> * **Menu**: Authentication → Logout
> * **Status**: Open
> * **Deskripsi**: Saat user menekan button Keluar pada dropdown profil di pojok kanan atas, proses logout gagal diproses.
> * **Expected**: Sistem berhasil membersihkan session login user dan mengarahkan kembali ke halaman Login.
> * **Actual**: Sistem mengarahkan user ke halaman error dengan pesan "Permintaan Tidak Dapat Diproses" dan user gagal logout.
> * **Evidence Awal**:
>   * Button Keluar: [https://files.catbox.moe/ujkwhl.png](https://files.catbox.moe/ujkwhl.png)
>   * Halaman Error: [https://files.catbox.moe/mbunqm.png](https://files.catbox.moe/mbunqm.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Masuk dengan Akun Lain Tidak Berfungsi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman Konfirmasi Identitas dan menekan button Masuk dengan akun lain, tidak ada respons apa pun dari sistem.
> * **Expected**: Sistem mengarahkan user kembali ke form login awal untuk memasukkan email atau akun yang berbeda.
> * **Actual**: Button Masuk dengan akun lain tidak berfungsi saat ditekan dan user tetap tertahan di halaman Konfirmasi Identitas.
> * **Evidence Awal**:
>   * Button Masuk Akun Lain: [https://files.catbox.moe/n4w7iw.png](https://files.catbox.moe/n4w7iw.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Menambah Role Baru Muncul Error 415

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi form modal Tambah Role dan menekan button Tambah, proses simpan gagal diproses oleh sistem.
> * **Expected**: Data role baru berhasil ditambahkan dan langsung terdaftar pada list Daftar Role.
> * **Actual**: Muncul toast error "Gagal menambah role" dengan keterangan "code=415, message=Unsupported Media Type" dan data role baru tidak tersimpan.
> * **Evidence Awal**:
>   * Toast Error Tambah Role: [https://files.catbox.moe/y85oza.png](https://files.catbox.moe/y85oza.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Menghapus Role Muncul Toast Error

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user menekan icon hapus pada salah satu data role dan mengonfirmasi dengan button Ya, Hapus, proses penghapusan gagal diproses sistem.
> * **Expected**: Data role berhasil dihapus dan otomatis terhapus dari list Daftar Role.
> * **Actual**: Muncul toast error "Gagal menghapus role" dengan pesan "Oops something went wrong, Contact Developer for the issue" dan data role tetap ada di list.
> * **Evidence Awal**:
>   * Modal Konfirmasi Hapus: [https://files.catbox.moe/a2dlfq.png](https://files.catbox.moe/a2dlfq.png)
>   * Toast Error Hapus: [https://files.catbox.moe/ypdpob.png](https://files.catbox.moe/ypdpob.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Menyimpan Aksi Role Muncul Error 415

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user memilih checkbox pada bagian Aksi Umum Role dan menekan button Simpan Aksi, proses penyimpanan gagal diproses sistem.
> * **Expected**: Pengaturan aksi umum role berhasil disimpan dan sistem memunculkan toast konfirmasi sukses.
> * **Actual**: Muncul toast error "Gagal menyimpan aksi role" dengan pesan "code=415, message=Unsupported Media Type" dan data aksi tidak tersimpan.
> * **Evidence Awal**:
>   * Toast Error Simpan Aksi Role: [https://files.catbox.moe/x29f8c.png](https://files.catbox.moe/x29f8c.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Mengubah Role Muncul Error 415

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user mengedit data role pada modal Ubah Role dan menekan button Simpan, proses pembaruan data gagal diproses sistem.
> * **Expected**: Perubahan data role berhasil diperbarui dan tersimpan pada list Daftar Role.
> * **Actual**: Muncul toast error "Gagal mengubah role" dengan pesan "code=415, message=Unsupported Media Type" dan data role tidak ter-update.
> * **Evidence Awal**:
>   * Toast Error Ubah Role: [https://files.catbox.moe/c6n1h7.png](https://files.catbox.moe/c6n1h7.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Dropdown Kantor pada Form Tambah User Kosong

> * **Menu**: User Management → User
> * **Status**: Done
> * **Deskripsi**: Saat user mengisi form tambah user dan membuka dropdown Kantor, opsi daftar kantor tidak muncul dan hanya menampilkan status "No data".
> * **Expected**: Dropdown Kantor menampilkan seluruh daftar kantor cabang yang aktif dan dapat dipilih oleh user.
> * **Actual**: Dropdown Kantor kosong dan hanya menampilkan "No data", sehingga proses submit data user tidak dapat diselesaikan.
> * **Evidence Awal**:
>   * Dropdown Kantor No Data: [https://files.catbox.moe/u2z6fh.png](https://files.catbox.moe/u2z6fh.png)
> * **Bukti Retest (Done)**:
>   * Dropdown Kantor: [https://files.catbox.moe/s2qycg.png](https://files.catbox.moe/s2qycg.png)
> * **Catatan Retest**:
>   * Dropdown Kantor sudah berhasil menampilkan daftar kantor cabang aktif.

<br>

### 🐞 [BUG] | Button Hapus Tetap Aktif pada Parent Root Kantor

> * **Menu**: Office Management → Office Type
> * **Status**: Open
> * **Deskripsi**: Pada tabel daftar tipe kantor, baris data dengan parent Root (Kantor Pusat) masih memiliki button hapus yang aktif pada kolom Action.
> * **Expected**: Data tipe kantor yang menjadi parent "Root" tidak dapat dihapus (button hapus dinonaktifkan/disabled atau disembunyikan).
> * **Actual**: Button hapus pada baris data parent "Root" tetap tampil aktif dan dapat ditekan oleh user.
> * **Evidence Awal**:
>   * Button Hapus Parent Root: [https://files.catbox.moe/210map.png](https://files.catbox.moe/210map.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Halaman Utama Gagal Redirect ke Login Internal

> * **Menu**: Authentication → Logout
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman auto-logout dan menekan button Halaman Utama, sistem gagal mengarahkan kembali ke form login portal internal.
> * **Expected**: Button Halaman Utama mengarahkan user kembali ke halaman Login Portal Internal BSN.
> * **Actual**: Sistem mengarahkan user ke path URL yang salah dan berujung pada halaman 404 situs publik.
> * **Evidence Awal**:
>   * Button Halaman Utama: [https://files.catbox.moe/p3u8zt.png](https://files.catbox.moe/p3u8zt.png)
>   * Hasil Redirect Error: [https://files.catbox.moe/bgx4u8.png](https://files.catbox.moe/bgx4u8.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Dropdown Parent Tipe Kantor Kosong

> * **Menu**: Office Management → Office Type
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi form tambah tipe kantor dan membuka dropdown Parent, daftar pilihan parent tidak muncul dan hanya menampilkan status "No data".
> * **Expected**: Dropdown Parent menampilkan daftar opsi tipe kantor (misal: Root, Kantor Pusat, dll.) yang dapat dipilih sebagai induk hierarki.
> * **Actual**: Dropdown Parent kosong dan hanya menampilkan "No data", sehingga proses penambahan tipe kantor baru terhambat.
> * **Evidence Awal**:
>   * Dropdown Parent No Data: [https://files.catbox.moe/iw6luy.png](https://files.catbox.moe/iw6luy.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Filter Pencarian Tipe Kantor Belum Berfungsi

> * **Menu**: Office Management → Office Type
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi parameter pencarian pada bar filter dan menekan button Cari, sistem tidak melakukan penyaringan data pada tabel.
> * **Expected**: Tabel menampilkan daftar tipe kantor yang sesuai dengan kriteria filter yang dimasukkan oleh user.
> * **Actual**: Fitur filter belum berfungsi dan tabel tidak merespons perubahan data pencarian setelah button Cari ditekan.
> * **Evidence Awal**:
>   * Filter Tipe Kantor: [https://files.catbox.moe/cuno1j.png](https://files.catbox.moe/cuno1j.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Validasi Konfirmasi Kata Sandi Tidak Hilang meskipun Password Sesuai

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi field Konfirmasi Kata Sandi dengan nilai yang identik dan telah memenuhi seluruh kriteria keamanan, teks peringatan validasi di bawah field tidak hilang.
> * **Expected**: Peringatan validasi otomatis hilang saat input Konfirmasi Kata Sandi sudah cocok dengan Kata Sandi.
> * **Actual**: Pesan "Kata sandi harus terdiri dari huruf besar, huruf kecil, angka, dan karakter khusus." tetap muncul dan tidak berubah meskipun password sudah sesuai.
> * **Evidence Awal**:
>   * Peringatan Validasi Konfirmasi: [https://files.catbox.moe/5dlimo.png](https://files.catbox.moe/5dlimo.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Submit Pendaftaran Tidak Menampilkan Notifikasi dan Gagal Redirect ke Login

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Open
> * **Deskripsi**: Saat user menyetujui Syarat & Ketentuan di langkah terakhir dan menekan button Daftar Sekarang, tidak ada notifikasi sukses dan user diarahkan kembali ke halaman pendaftaran.
> * **Expected**: Sistem memunculkan notifikasi/informasi pendaftaran berhasil dan langsung mengarahkan user ke halaman Login.
> * **Actual**: Tidak ada notifikasi sukses yang muncul dan sistem malah me-redirect user kembali ke form pendaftaran awal.
> * **Evidence Awal**:
>   * Button Daftar Sekarang: [https://files.catbox.moe/b00i5x.png](https://files.catbox.moe/b00i5x.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Masuk dengan Akun Lain Tidak Berfungsi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman Konfirmasi Identitas dan menekan button Masuk dengan akun lain, tidak ada respons apa pun dari sistem.
> * **Expected**: Sistem mengarahkan user kembali ke halaman/form login awal untuk memasukkan email atau akun lain.
> * **Actual**: Button Masuk dengan akun lain tidak berfungsi saat ditekan dan user tetap tertahan di halaman Konfirmasi Identitas.
> * **Evidence Awal**:
>   * Button Masuk Akun Lain: [https://files.catbox.moe/6nlq0m.png](https://files.catbox.moe/6nlq0m.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Klik "Daftar gratis sekarang" Malah Memunculkan Toast Konfirmasi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di form login dan menekan link button Daftar gratis sekarang, sistem tidak mengarahkan ke form registrasi akun baru.
> * **Expected**: Sistem mengarahkan user ke halaman pendaftaran akun baru (Register).
> * **Actual**: Muncul toast info "Harap konfirmasi tindakan ini dengan memverifikasi bahwa ini benar-benar Kamu" dan user tetap tertahan di halaman login.
> * **Evidence Awal**:
>   * Toast Daftar Gratis Sekarang: [https://files.catbox.moe/av606w.png](https://files.catbox.moe/av606w.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Klik Lupa Kata Sandi Malah Diarahkan ke Halaman Sesi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di form login dan menekan link button Lupa kata sandi?, sistem tidak mengarahkan ke form pemulihan/reset kata sandi akun.
> * **Expected**: Sistem mengarahkan user ke halaman reset kata sandi dengan field input email untuk verifikasi pemulihan akun.
> * **Actual**: Sistem malah mengarahkan user ke halaman sesi auth dengan keterangan "Anda belum masuk ke akun manapun" dan button "Masuk Sekarang".
> * **Evidence Awal**:
>   * Form Login: [https://files.catbox.moe/214j9d.png](https://files.catbox.moe/214j9d.png)
>   * Halaman Sesi: [https://files.catbox.moe/c2vb8i.png](https://files.catbox.moe/c2vb8i.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Nama Nasabah pada Header Navbar Belum Muncul

> * **Menu**: Beranda → Header
> * **Status**: Open
> * **Deskripsi**: Saat user nasabah telah berhasil login dan mengakses halaman Beranda, komponen profil akun pada pojok kanan atas header navbar belum memuat identitas nasabah.
> * **Expected**: Header navbar menampilkan inisial avatar serta nama lengkap nasabah yang sedang login.
> * **Actual**: Header navbar belum memuat nama nasabah dan hanya menampilkan karakter strip (-) pada badge lingkaran hijau serta teks label (- v).
> * **Evidence Awal**:
>   * Badge Profil Navbar: [https://files.catbox.moe/8bm9tu.png](https://files.catbox.moe/8bm9tu.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Seluruh Tab pada Halaman Profil Nasabah Gagal Memuat Data

> * **Menu**: User Profile → Profile Tabs
> * **Status**: Open
> * **Deskripsi**: Saat user nasabah mengakses halaman profil akun dan berpindah antar tab (Profil, Akun, Daftar Pesanan, Favorit, Notifikasi), seluruh tab gagal memuat konten data.
> * **Expected**: Seluruh tab menu pada halaman profil nasabah dapat diakses dengan lancar dan menampilkan informasi data nasabah dengan normal.
> * **Actual**: Seluruh tab menu gagal memuat data dan menampilkan ilustrasi error "Oops! Terjadi kesalahan saat memuat data".
> * **Evidence Awal**:
>   * Dropdown Navbar Profil: [https://files.catbox.moe/vove9t.png](https://files.catbox.moe/vove9t.png)
>   * Halaman Error Memuat Data: [https://files.catbox.moe/h5am05.png](https://files.catbox.moe/h5am05.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Setelah Logout Navbar Profil Tidak Berubah Menjadi Button Masuk

> * **Menu**: Beranda → Header
> * **Status**: Open
> * **Deskripsi**: Saat user nasabah telah melakukan logout dan kembali ke Beranda, komponen header navbar di pojok kanan atas tidak kembali ke status belum login.
> * **Expected**: Header navbar menampilkan button Masuk setelah proses logout selesai.
> * **Actual**: Header navbar tetap menampilkan badge profil ([-] - v) dan tidak berubah menjadi button Masuk.
> * **Evidence Awal**:
>   * Navbar Setelah Logout: [https://files.catbox.moe/09p09q.png](https://files.catbox.moe/09p09q.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Validasi Kata Sandi Breached Muncul di Langkah Terakhir dan Melempar User ke Awal

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Catatan / Clarification
> * **Deskripsi**: Saat mendaftar akun nasabah, indikator kata sandi di Langkah 1 valid dan berwarna hijau ("Kuat"). Namun saat menekan button Daftar Sekarang di Langkah 3, sistem menolak pendaftaran dengan pesan pelanggaran data dan melempar user kembali ke Langkah 1.
> * **Expected**: Validasi kata sandi (termasuk deteksi data breach) dievaluasi langsung di Langkah 1 sebelum user melanjutkan ke langkah berikutnya, atau indikator kekuatan kata sandi menampilkan peringatan sejak awal.
> * **Actual**: User berhasil menyelesaikan form hingga Langkah 3, namun gagal submit dengan toast error "Kata sandi ditemukan dalam pelanggaran data dan tidak boleh digunakan lagi" dan otomatis diarahkan kembali ke Langkah 1.
> * **Catatan Tim**: Menunggu klarifikasi tim terkait security policy HaveIBeenPwned (HIBP) / breached password di auth backend dan kesesuaian alur UX di Langkah 1 vs Langkah 3.
> * **Evidence Awal**:
>   * Submit Langkah 3: [https://files.catbox.moe/0eqyh8.png](https://files.catbox.moe/0eqyh8.png)
>   * Error Langkah 1: [https://files.catbox.moe/37o3lw.png](https://files.catbox.moe/37o3lw.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Daftar dengan Google Stuck Memproses dan Tidak Berfungsi

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman pendaftaran akun nasabah langkah 1 dan menekan button Daftar dengan Google, sistem tidak merespons pengalihan ke akun Google.
> * **Expected**: Sistem mengarahkan user ke halaman login/pemilihan akun Google (Google OAuth Sign-In).
> * **Actual**: Button hanya berubah menampilkan status spinner "Memproses" secara terus-menerus (stuck loading) dan tidak terjadi redirect.
> * **Evidence Awal**:
>   * Button Google: [https://files.catbox.moe/96bd6e.png](https://files.catbox.moe/96bd6e.png)
>   * Status Memproses: [https://files.catbox.moe/uzp8ik.png](https://files.catbox.moe/uzp8ik.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Tidak Ada Button Navigasi Kembali ke Login pada Halaman Verifikasi OTP

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman verifikasi OTP ("Masukkan Kode Verifikasi"), tidak tersedia button atau navigasi untuk membatalkan proses dan kembali ke form login awal.
> * **Expected**: Halaman verifikasi OTP menyediakan button atau link navigasi Kembali ke Login (atau tombol kembali) agar user dapat mengganti akun jika terjadi salah input email.
> * **Actual**: Halaman hanya menyediakan button Lanjutkan dan Kirim ulang kode tanpa ada opsi navigasi kembali ke login.
> * **Evidence Awal**:
>   * Halaman Verifikasi OTP: [https://files.catbox.moe/ibxwqj.png](https://files.catbox.moe/ibxwqj.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Label Banner Login External Masih Tertulis Sistem Portal Internal

> * **Menu**: Authentication → Login
> * **Status**: Catatan / Clarification
> * **Deskripsi**: Saat user mengakses halaman login external (nasabah), teks sub-judul pada banner sebelah kiri masih menampilkan label "Sistem Portal Internal".
> * **Expected**: Banner sebelah kiri menampilkan label yang sesuai dengan portal publik/external nasabah (misalnya "Sistem Portal Nasabah" atau "Portal Lelang BSN").
> * **Actual**: Banner sebelah kiri masih tertulis "Sistem Portal Internal", yang tidak sesuai dengan konteks portal external nasabah.
> * **Catatan Tim**: Menunggu klarifikasi tim apakah teks banner kiri pada portal nasabah/external memang seharusnya 'Sistem Portal Nasabah / External' atau teks 'Sistem Portal Internal' adalah copywriting sementara/salah template.
> * **Evidence Awal**:
>   * Form Login: [https://files.catbox.moe/gmq0kc.png](https://files.catbox.moe/gmq0kc.png)
>   * Konfirmasi Identitas: [https://files.catbox.moe/5hfldp.png](https://files.catbox.moe/5hfldp.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Field Email dan Kata Sandi Tidak Memiliki Indikator Bintang Mandatory

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di form login, label pada field Email dan Kata Sandi tidak dilengkapi dengan simbol asterisk/tanda bintang (*) penanda field wajib diisi.
> * **Expected**: Label field menampilkan simbol asterisk merah (Email * & Kata Sandi *) sebagai penanda bahwa kedua field tersebut mandatory/wajib diisi.
> * **Actual**: Label hanya menampilkan teks Email dan Kata Sandi polos tanpa indikator bintang mandatory.
> * **Evidence Awal**:
>   * Form Login: [https://files.catbox.moe/pkauex.png](https://files.catbox.moe/pkauex.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Field Kata Sandi Baru dan Konfirmasi Tidak Memiliki Indikator Bintang Mandatory

> * **Menu**: Authentication → Lupa Kata Sandi
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman pemulihan akun ("Masukkan Kata Sandi Baru"), label pada field Kata Sandi dan Konfirmasi Kata Sandi tidak dilengkapi simbol asterisk/tanda bintang (*) penanda field wajib diisi.
> * **Expected**: Label field menampilkan simbol asterisk merah (Kata Sandi * & Konfirmasi Kata Sandi *) sebagai penanda bahwa kedua field tersebut mandatory/wajib diisi.
> * **Actual**: Label hanya menampilkan teks Kata Sandi dan Konfirmasi Kata Sandi polos tanpa indikator bintang mandatory.
> * **Evidence Awal**:
>   * Form Reset Password: [https://files.catbox.moe/rwoifa.png](https://files.catbox.moe/rwoifa.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Masuk Sekarang Terpental ke Halaman Sesi dan Gagal Membuka Login

> * **Menu**: Authentication → Lupa Kata Sandi
> * **Status**: Open
> * **Deskripsi**: Setelah user selesai mereset kata sandi dan diarahkan ke halaman sesi auth, penekanan button Masuk Sekarang mengalami mental (redirect loop) kembali ke /auth sehingga user tidak bisa mengakses form login.
> * **Expected**: Sistem mengarahkan user ke form login dan user dapat memasukkan kata sandi baru untuk masuk ke akun.
> * **Actual**: Saat menekan button Masuk Sekarang, sistem sempat membuka form login namun langsung terpental kembali ke halaman sesi /auth ("Anda belum masuk ke akun manapun").
> * **Evidence Awal**:
>   * Halaman Sesi Auth: [https://files.catbox.moe/acnx02.png](https://files.catbox.moe/acnx02.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Identitas Akun User Tidak Muncul pada Halaman Konfirmasi Identitas

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user melanjutkan alur login ke tahap Konfirmasi Identitas, teks penjelas akun tidak menampilkan alamat email atau nama akun user.
> * **Expected**: Halaman Konfirmasi Identitas menampilkan identitas user yang sedang login (misalnya: "Anda masuk sebagai user@email.com").
> * **Actual**: Keterangan "Anda masuk sebagai" kosong tanpa menampilkan email atau data user yang sedang diverifikasi.
> * **Evidence Awal**:
>   * Halaman Konfirmasi Identitas: [https://files.catbox.moe/34yhsf.png](https://files.catbox.moe/34yhsf.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Email Reset Password Gagal Terkirim ke Mailpit

> * **Menu**: Authentication → Lupa Kata Sandi
> * **Status**: Open
> * **Deskripsi**: Saat user mengajukan pemulihan kata sandi akun internal dan sistem memunculkan toast bahwa email telah dikirim, pesan berisi tautan pemulihan tidak pernah masuk/diterima di Mailpit.
> * **Expected**: Sistem berhasil mengirimkan email berisi tautan/kode pemulihan kata sandi ke server Mailpit.
> * **Actual**: Toast info menyatakan email telah dikirim, namun inbox Mailpit tidak menerima email pemulihan apa pun.
> * **Evidence Awal**:
>   * Toast Pemulihan Akun: [https://files.catbox.moe/6rd9fo.png](https://files.catbox.moe/6rd9fo.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Tambah Proyek Aset Belum Berfungsi

> * **Menu**: Developer → List Developer → Detail Developer
> * **Status**: Open
> * **Deskripsi**: Saat user membuka detail salah satu developer dan menekan button + Tambah Proyek / Aset Baru pada section *Daftar Proyek & Portofolio Aset Developer*, form input tidak terbuka dan sistem menampilkan toast bahwa fitur belum tersedia karena masih menunggu kesiapan API.
> * **Expected**: Sistem menampilkan formulir/modal input untuk menambahkan data proyek, klaster, atau unit aset baru developer.
> * **Actual**: Button tidak membuka form input dan memunculkan toast info "Fitur ini belum tersedia, menunggu API".
> * **Evidence Awal**:
>   * Detail Developer: [https://files.catbox.moe/79re76.png](https://files.catbox.moe/79re76.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Menambah FAQ Muncul Error answer dan question cannot be blank

> * **Menu**: Media & Information → FAQ
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi field Pertanyaan dan Jawaban lalu menekan button Submit, sistem gagal menyimpan dan memunculkan pesan validasi bahwa kedua field kosong.
> * **Expected**: FAQ baru berhasil disimpan, muncul notifikasi sukses, dan sistem mengarahkan kembali ke tabel list FAQ.
> * **Actual**: Muncul toast error "answer: cannot be blank; question: cannot be blank." padahal kedua field wajib sudah terisi.
> * **Evidence Awal**:
>   * Form Tambah FAQ: [https://files.catbox.moe/e1tq91.png](https://files.catbox.moe/e1tq91.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Menyimpan Berita Baru Muncul Error Unggah Gambar

> * **Menu**: Media & Information → Article
> * **Status**: Open
> * **Deskripsi**: Saat user melengkapi seluruh data artikel termasuk gambar utama lalu menekan button Simpan Berita, sistem gagal menyimpan artikel dan memunculkan error toast upload gambar.
> * **Expected**: Artikel baru berhasil tersimpan, muncul notifikasi sukses, dan sistem mengarahkan kembali ke halaman daftar artikel.
> * **Actual**: Sistem gagal menyimpan dan menampilkan toast error "Gagal mengunggah gambar" dengan rincian "Network Error" meskipun indikator kelengkapan gambar utama sudah hijau.
> * **Evidence Awal**:
>   * Toast Error Simpan Berita: [https://files.catbox.moe/yxcalm.png](https://files.catbox.moe/yxcalm.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Menyimpan Banner Baru Muncul Error Unggah Gambar

> * **Menu**: Media & Information → Banner Setting
> * **Status**: Open
> * **Deskripsi**: Saat user mengunggah gambar banner dan mengisi judul lalu menekan button Simpan Banner, sistem gagal menyimpan banner dan memunculkan error toast upload gambar.
> * **Expected**: Banner baru berhasil disimpan, muncul notifikasi sukses, dan sistem mengarahkan kembali ke halaman pengaturan banner.
> * **Actual**: Sistem gagal menyimpan dan menampilkan toast error "Gagal mengunggah gambar" dengan rincian "Network Error" meskipun indikator kelengkapan gambar banner sudah hijau.
> * **Evidence Awal**:
>   * Toast Error Simpan Banner: [https://files.catbox.moe/oiy2ia.png](https://files.catbox.moe/oiy2ia.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | User yang Diblokir Tidak Muncul pada Menu User Block

> * **Menu**: User Management → User Block
> * **Status**: Open
> * **Deskripsi**: Saat user menonaktifkan atau memblokir akun user pada menu User, daftar user tersebut tidak masuk dan tidak ditampilkan pada tabel User Block.
> * **Expected**: User yang berstatus Tidak Aktif atau diblokir otomatis tercatat dan tampil pada daftar tabel di menu User Block.
> * **Actual**: Tabel pada menu User Block tetap kosong dengan keterangan "Belum ada user yang diblokir" meskipun terdapat user berstatus Tidak Aktif pada menu User.
> * **Evidence Awal**:
>   * Status User Tidak Aktif: [https://files.catbox.moe/9pufg4.png](https://files.catbox.moe/9pufg4.png)
>   * Tabel User Block Kosong: [https://files.catbox.moe/nddkir.png](https://files.catbox.moe/nddkir.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Memblokir User tanpa Alasan Muncul Error Oops Something Went Wrong

> * **Menu**: User Management → User Block
> * **Status**: Open
> * **Deskripsi**: Saat user mencoba memblokir akun user dengan mengosongkan field Alasan, proses blokir gagal diproses dan sistem memunculkan toast error server.
> * **Expected**: Sistem menampilkan pesan validasi form yang jelas jika field Alasan bersifat mandatory, atau proses pemblokiran berhasil tersimpan jika field Alasan bersifat opsional.
> * **Actual**: Sistem gagal memproses pemblokiran dan memunculkan toast error "Oops something went wrong, Contact Developer for the issue" saat modal konfirmasi ditekan.
> * **Evidence Awal**:
>   * Toast Error Blokir User: [https://files.catbox.moe/l671x1.png](https://files.catbox.moe/l671x1.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Gagal Menambah User dengan Email yang Sudah Terdaftar

> * **Menu**: User Management → User
> * **Status**: Open
> * **Deskripsi**: Saat user menambahkan user baru menggunakan alamat email yang sudah terdaftar di sistem, proses submit gagal dan memunculkan error crash server.
> * **Expected**: Sistem menampilkan pesan validasi atau toast peringatan yang informatif seperti "Email sudah terdaftar" agar user dapat mengganti alamat email.
> * **Actual**: Sistem gagal memvalidasi duplikasi email dan langsung melempar error server "Oops something went wrong, Contact Developer for the issue".
> * **Evidence Awal**:
>   * Toast Error Email Terdaftar: [https://files.catbox.moe/hhkfv0.png](https://files.catbox.moe/hhkfv0.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | User External yang Terdaftar Tidak Muncul pada Menu User External

> * **Menu**: User Management → User External
> * **Status**: Open
> * **Deskripsi**: Saat user baru berhasil melakukan registrasi melalui portal External, akun tersebut tidak masuk dan tidak ditampilkan pada menu User External portal Internal.
> * **Expected**: User yang telah terdaftar dari portal External otomatis tercatat pada statistik member dan muncul pada tabel List Update User External.
> * **Actual**: Total user pada statistik tetap 0 dan tabel User External kosong dengan keterangan "Belum ada user external" meskipun registrasi user external telah dilakukan.
> * **Evidence Awal**:
>   * Tabel User External Kosong: [https://files.catbox.moe/ofj739.png](https://files.catbox.moe/ofj739.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Filter Jenis Properti Belum Berfungsi

> * **Menu**: Aset Baru (External) → Filter Pencarian
> * **Status**: Re-Open
> * **Overview**: Pada panel Filter Pencarian di halaman Aset Baru (External), filter berdasarkan Jenis Properti belum berfungsi untuk menyaring daftar aset, sedangkan filter lainnya sudah berfungsi.
> * **Expected**: Memilih opsi pada filter Jenis Properti dapat menyaring daftar aset sesuai jenis properti yang dipilih
> * **Actual**: Filter Jenis Properti belum berfungsi saat digunakan untuk menyaring daftar aset
> * **Evidence Awal**:
>   * Filter Jenis Properti: [https://files.catbox.moe/gfmuer.png](https://files.catbox.moe/gfmuer.png)
> * **Bukti Retest (Re-Open)**:
>   * Disimpan lokal (`retest_reopen_01_opsi_lain_hilang.jpg`, `retest_reopen_02_opsi_belum_semua.jpg`) & copas langsung di Huly
> * **Catatan Retest**:
>   * Filter sudah menyaring data, namun setelah memilih 1 opsi properti (misal "Apartemen") opsi lainnya hilang. Usulan: tampilkan semua jenis properti dengan 5 teratas terlebih dahulu + tombol "Lihat Semua" / "Lebih Sedikit".
<br>

### 🐞 [BUG] | Informasi Developer, Proyek, Klaster, Tipe, Harga Coret, dan Label Harga pada Card Aset Belum Sesuai

> * **Menu**: Aset Baru (External) → Card Aset
> * **Status**: Re-Open
> * **Overview**: Pada halaman Aset Baru (External), tampilan card aset belum sesuai: nama developer, proyek, klaster, dan tipe unit belum muncul (masih tampil "Developer Rekanan BSN" dan angka seperti "12"); harga coret & badge "Hemat Rp ..." belum tampil; serta label harga masih tertulis "Harga Awal" (seharusnya "Harga Aset").
> * **Expected**: Card aset menampilkan nama developer & proyek, klaster & tipe unit, harga coret beserta badge "Hemat Rp ...", dan label "Harga Aset"
> * **Actual**: Card aset hanya menampilkan "Developer Rekanan BSN" dengan judul angka ("12"), harga coret & keterangan hemat belum tampil, serta label harga masih tertulis "Harga Awal"
> * **Evidence Awal**:
>   * App Card Aset: [https://files.catbox.moe/9keqxm.png](https://files.catbox.moe/9keqxm.png)
>   * Figma Card Aset: [https://files.catbox.moe/ycciri.png](https://files.catbox.moe/ycciri.png)
> * **Bukti Retest (Re-Open)**:
>   * Disimpan lokal (`retest_reopen_01_card_kotak.jpg`, `retest_reopen_02_card_memanjang.jpg`, `retest_reopen_03_card_memanjang_detail_ui.png`) & copas langsung di Huly
> * **Catatan Retest**:
>   * Informasi developer & urutan judul ("Nama Developer • Nama Proyek" dan "Klaster - Tipe") sudah sesuai. Namun pada Card Memanjang (List) masih ada 8 temuan UI: (1) keterangan "Diperbarui: ..." seharusnya tidak ada, (2) "Kamar" seharusnya "K. Tidur", (3) "Toilet" seharusnya "K. Mandi", (4) "Rp300 Juta" kurang spasi, (5) icon Favorit masih bookmark (harusnya love), (6) tombol "Beli Sekarang ->" harusnya "Ajukan Peminatan ->", (7) belum ada tombol "Simulasi", (8) belum ada perhitungan "Angsuran est.".
<br>

### 🐞 [BUG] | Tampilan Header, Spesifikasi, dan Map pada Detail Aset Baru Belum Sesuai

> * **Menu**: Aset Baru (External) → Detail Aset
> * **Status**: Open
> * **Overview**: Pada halaman Detail Aset Baru (External), terdapat ketidaksesuaian dengan desain Figma: Header (judul seharusnya cukup "Klaster - Tipe" tanpa nama proyek, dan baris bawahnya sejajar 1 baris: icon pin + Nama Proyek, Lokasi • Kode Listing), Spesifikasi & Dimensi Fisik Aset (Luas Tanah & Luas Bangunan masih "-"), serta Aksesibilitas & Lokasi Strategis (peta belum tampil dan masih muncul "Koordinat lokasi tidak tersedia").
> * **Expected**: Judul tampil "Klaster - Tipe", baris bawah sejajar 1 baris (icon pin + Nama Proyek, Lokasi • Kode Listing), nilai Luas Tanah & Luas Bangunan tampil sesuai data aset, dan peta lokasi tampil
> * **Actual**: Nama proyek masih ikut di judul, baris lokasi tanpa icon pin/nama proyek dengan Kode Listing turun baris, nilai Luas Tanah & Luas Bangunan masih "-", dan peta belum tampil
> * **Evidence Awal**:
>   * App Header Detail Aset: [https://files.catbox.moe/tii786.png](https://files.catbox.moe/tii786.png)
>   * App Map Tidak Tampil: [https://files.catbox.moe/0k8ekb.png](https://files.catbox.moe/0k8ekb.png)
>   * Figma Header Detail Aset: [https://files.catbox.moe/8kaim1.png](https://files.catbox.moe/8kaim1.png)
>   * Figma Map Detail Aset: [https://files.catbox.moe/pvgl13.png](https://files.catbox.moe/pvgl13.png)
>   * App Luas Tanah & Bangunan Kosong: [https://files.catbox.moe/p2v3h1.png](https://files.catbox.moe/p2v3h1.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Gagal Menghitung Simulasi KPR Syariah Muncul Error

> * **Menu**: Simulasi Pembiayaan (External) → Form Simulasi
> * **Status**: Open
> * **Overview**: Saat mencoba menghitung simulasi KPR Syariah, hasil perhitungan tidak muncul dan sistem justru menampilkan toast error.
> * **Expected**: Hasil simulasi angsuran KPR Syariah berhasil dihitung dan ditampilkan
> * **Actual**: Muncul toast error "Terjadi kesalahan saat menghitung KPR Syariah" dan hasil perhitungan tidak tampil
> * **Evidence Awal**:
>   * Toast Error Simulasi KPR: [https://files.catbox.moe/2yqjv2.png](https://files.catbox.moe/2yqjv2.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Logo, Segmen, dan Jumlah Aset pada Card Developer Belum Sesuai

> * **Menu**: Daftar Developer (External) → Card Developer
> * **Status**: Re-Open
> * **Overview**: Pada card developer di halaman Daftar Developer, masih ada beberapa tampilan yang belum sesuai: (1) logo developer belum tampil (masih inisial "HPN"), (2) label kategori masih tertulis "Developer" (seharusnya "Subsidi" atau "Non Subsidi"), (3) Jumlah Aset Properti masih tampil 0.
> * **Expected**: Card menampilkan logo developer, label segmen ("Subsidi" / "Non Subsidi"), dan jumlah aset properti sesuai data
> * **Actual**: Logo masih inisial ("HPN"), label masih tertulis "Developer", dan jumlah aset properti masih 0
> * **Evidence Awal**:
>   * Card Daftar Developer: [https://files.catbox.moe/1la023.png](https://files.catbox.moe/1la023.png)
> * **Bukti Retest (Re-Open)**:
>   * Disimpan lokal (`retest_reopen_01_card_developer.png`) & copas langsung di Huly
> * **Catatan Retest**:
>   * Logo belum muncul, segmen baru menampilkan "Non Subsidi" semua (belum sesuai pilihan masing-masing developer: Subsidi / Non Subsidi / keduanya), dan Jumlah Aset Properti masih 0.
<br>

### 🐞 [BUG] | Pilihan Segmen Properti Utama Terintegrasi Belum Bisa Memilih Dua Opsi

> * **Menu**: Developer (Internal) → List Developer
> * **Status**: Open
> * **Overview**: Pada field Segmen Properti Utama Terintegrasi, seharusnya user bisa memilih 2 opsi sekaligus ("Subsidi" dan "Non Subsidi"), tetapi saat ini belum bisa.
> * **Expected**: User bisa memilih 2 opsi sekaligus ("Subsidi" dan "Non Subsidi")
> * **Actual**: Saat ini belum bisa memilih 2 opsi sekaligus (hanya bisa memilih satu opsi)
> * **Evidence Awal**:
>   * Pilihan Segmen Properti: [https://files.catbox.moe/f77cwa.png](https://files.catbox.moe/f77cwa.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Data Statistik, Kolom Tabel, dan Filter pada List Developer Belum Sesuai

> * **Menu**: Developer (Internal) → List Developer
> * **Status**: Open
> * **Overview**: Pada halaman List Developer, masih ditemukan beberapa ketidaksesuaian data dan opsi filter: (1) Kartu TOTAL ASET PROYEK masih tampil "0 Aset Proyek", (2) Filter Semua Segmen belum punya opsi "Subsidi & Non Subsidi", (3) Filter Semua Kantor Wilayah hanya menampilkan "KCS Makassar", (4) Kolom Segmen pada tabel masih "Segmen belum diisi", dan (5) Data Unit masih tampil "0 Unit".
> * **Expected**: Total aset proyek, data segmen, dan jumlah unit tampil sesuai data sebenarnya; filter segmen menyediakan opsi "Subsidi & Non Subsidi"; dan filter kantor wilayah menampilkan seluruh kantor terdaftar
> * **Actual**: Total aset proyek tampil 0, data segmen tertulis belum diisi, jumlah unit tampil 0, filter segmen belum ada opsi gabungan, dan filter kantor wilayah hanya menampilkan "KCS Makassar"
> * **Evidence Awal**:
>   * Total Aset Proyek, Segmen, & Unit Kosong: [https://files.catbox.moe/7ui0n0.png](https://files.catbox.moe/7ui0n0.png)
>   * Filter Segmen Kurang Opsi Gabungan: [https://files.catbox.moe/qe3yw1.png](https://files.catbox.moe/qe3yw1.png)
>   * Filter Kantor Hanya Makassar: [https://files.catbox.moe/6rls01.png](https://files.catbox.moe/6rls01.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

### 🐞 [BUG] | Aset yang Belum Publish Tampil di Katalog External

> * **Menu**: Aset Baru (External) → Katalog
> * **Status**: Open
> * **Huly**: HULY-109 (sudah diinput ke Huly, proyek BSN LELANG (EXTERNAL))
> * **Overview**: Katalog Aset Baru di portal External menampilkan 6 aset. Padahal aset yang sudah publish di Internal hanya 4. Dua aset yang belum publish (JKHS-10001 dan JKHS-10004) ikut tampil, detailnya bisa dibuka, dan bisa diajukan peminatan.
> * **Expected**: Katalog External hanya menampilkan 4 aset yang sudah Published di Internal. Aset yang belum publish tidak tampil dan tidak bisa diakses dari External.
> * **Actual**: Katalog External menampilkan 6 aset. JKHS-10001 dan JKHS-10004 yang belum publish ikut tampil, detailnya bisa dibuka, dan peminatan bisa diajukan.
> * **Evidence Awal**:
>   * Katalog 6 Aset: evidence_01_total-6-aset_redbox.png (file lokal di folder issue `External/Aset Baru/Katalog/01`, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
<br>

### 🐞 [BUG] | Form Pengajuan Peminatan Belum Sesuai Desain Figma

> * **Menu**: Aset Baru (External) → Form Pengajuan Peminatan
> * **Status**: Open
> * **Huly**: HULY-110 (sudah diinput ke Huly, proyek BSN LELANG (EXTERNAL))
> * **Overview**: Form pengajuan peminatan aset baru di portal External saat ini tampil dalam satu halaman panjang, semua bagian form ditumpuk di satu halaman. Tampilan ini belum sesuai desain Figma terbaru yang membagi form menjadi beberapa step.
> * **Expected**: Form pengajuan peminatan tampil bertahap sesuai desain Figma: satu step dalam satu halaman, mulai dari Step 1 Data Properti & Akad sampai Step 4 Dokumen Pendukung.
> * **Actual**: Form tampil dalam satu halaman panjang dan belum dibagi per step seperti desain Figma.
> * **Evidence Awal**:
>   * Form Saat Ini: evidence_21_form-saat-ini.png (file lokal di folder issue `External/Aset Baru/Form Pengajuan Peminatan/01`, drag & drop ke Huly)
>   * Desain Figma: evidence_20_figma-form-baru.png (file lokal di folder issue yang sama, drag & drop ke Huly)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
