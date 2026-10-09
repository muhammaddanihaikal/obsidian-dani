# 📝 Testing Log - Modul 03 Notifikasi Web (Penyelarasan Menu UI Web)

Catatan pengujian web untuk penambahan fitur baru **Modul 03. Notifikasi** dan penyesuaian urutan penomoran modul sesuai susunan antarmuka portal **BTN SMART Web**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Web (Portal Admin / Web App)
* **Modul**: Modul 03. Notifikasi
* **Tanggal Update**: 9 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **100% COMPLETE & SYNCED (10 ESSENTIAL TC / 18 SCREENSHOTS) - TRI-DRIVE & GIT VERIFIED** ✅

---

## 🔍 Ringkasan Penyelarasan Urutan Menu & Header Navbar
Berdasarkan arahan Mas Dani dan analisis navigasi antarmuka portal BTN SMART Web:
1. Fitur **Notifikasi** terletak pada header bar (icon lonceng) yang diakses langsung setelah login & navigasi profil, serta terintegrasi dengan menu **Pengaturan Profile - Notifikasi**.
2. Modul Notifikasi dialokasikan sebagai **Modul 3** mandiri (TC `3.1` s/d `3.10`), tepat setelah **Modul 2 Profile**.
3. Judul Test Case pertama disepakati **tanpa kata "popover"**: *"Membuka notifikasi pada header"*.
4. Penambahan Test Case baru: **3.10 Melihat detail notifikasi** (akses drawer/halaman detail pesan notifikasi dari daftar notifikasi).
5. Seluruh tangkapan layar (18 screenshot asli) telah dipindahkan dari folder luar, disimpan versi uncropped di folder backup `(Original Full)` di Local D dan Google Drive G, serta di-crop standar (menghilangkan sidebar & navbar pada halaman profil, menghilangkan sidebar & menjaga popover navbar pada aksi header) dan di-embed ke Dokumen Hasil Uji Master.

---

## 📋 Daftar 10 Test Case Lengkap (Modul 03. Notifikasi)

| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Steps (Scenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **3.1** | Notifikasi | - | Membuka notifikasi pada header | Positive Case | High | Klik icon Lonceng (Notifikasi) pada header bar | Berhasil menampilkan daftar notifikasi terbaru. | Embedded (2 SS: Icon & Popover) |
| **3.2** | Notifikasi | - | Mencari notifikasi dengan kata kunci valid | Positive Case | Normal | Masukkan kata kunci valid pada kolom Cari notifikasi | Berhasil menampilkan data notifikasi yang dicari. | Embedded (1 SS: Input "file ekspor") |
| **3.3** | Notifikasi | - | Mencari notifikasi dengan kata kunci tidak valid | Negative Case | Normal | Masukkan kata kunci tidak valid pada kolom Cari notifikasi | Berhasil menampilkan informasi data tidak ditemukan. | Embedded (1 SS: Input "tidak ada") |
| **3.4** | Notifikasi | - | Melihat data notifikasi Belum Dibaca | Positive Case | Normal | Pada daftar notifikasi, klik tab Belum Dibaca | Berhasil menampilkan data notifikasi belum dibaca. | Embedded (1 SS: Tab Belum Dibaca) |
| **3.5** | Notifikasi | - | Melihat data notifikasi Diarsipkan | Positive Case | Normal | Pada halaman Pengaturan Profile - Notifikasi, klik tab Diarsipkan | Berhasil menampilkan data notifikasi diarsipkan. | Embedded (1 SS: Tab Diarsipkan) |
| **3.6** | Notifikasi | - | Menandai semua notifikasi telah dibaca | Positive Case | High | Pada notifikasi, klik tombol Tandai semua dibaca | Berhasil menandai seluruh notifikasi telah dibaca. | Embedded (2 SS: Tombol & Counter 0) |
| **3.7** | Notifikasi | - | Membuka halaman Notifikasi pada Pengaturan Profile | Positive Case | High | Klik tombol Lihat semua pada notifikasi header (atau masuk via menu Pengaturan Profile) | Berhasil menampilkan halaman penuh Notifikasi pada Pengaturan Profile. | Embedded (2 SS: Tombol & Full Page) |
| **3.8** | Notifikasi | - | Mengarsipkan notifikasi | Positive Case | High | Pada halaman Detail Notifikasi, klik tombol Arsipkan | Berhasil mengarsipkan notifikasi. | Embedded (3 SS: Klik Item, Tombol Arsip, Hasil Tab Diarsipkan) |
| **3.9** | Notifikasi | - | Membatalkan arsip notifikasi | Positive Case | High | Pada halaman Detail Notifikasi yang diarsipkan, klik tombol Kembalikan dari arsip | Berhasil membatalkan arsip notifikasi. | Embedded (3 SS: Klik Item Arsip, Tombol Unarsip, Hasil Kembali) |
| **3.10** | Notifikasi | - | Melihat detail notifikasi | Positive Case | High | Pada daftar notifikasi, klik salah satu notifikasi yang ingin dilihat | Berhasil menampilkan halaman Detail Notifikasi. | Embedded (2 SS: Klik Item Popover & Halaman Detail Notif) |

---

## ✂️ Standardisasi Pemotongan Screenshot (Clean Web Crop)
Sesuai arahan Mas Dani (*"crop nya pake versi yg biasa aja bro hilangin sidebar navbar aja bro"*):
1. **Aksi Popover & Header (TC 3.1, 3.2, 3.3, 3.4, 3.6, 3.7.1, 3.10.1)**:
   - Sidebar kiri dihapus (`x = 300px`).
   - Navbar atas **TETAP ADA** (`y = 0`) agar badge icon lonceng, red box, dan card popover dropdown tidak terpotong.
   - Scrollbar browser kanan dipotong 15px (`x = 1905px`).
2. **Halaman Menu Profile (TC 3.5, 3.7.2, 3.8, 3.9, 3.10.2)**:
   - **Full Body Crop**: Sidebar kiri dihapus (`x = 300px`) dan Navbar atas dihapus (`y = 64px`).
   - Menghasilkan tampilan frame *"Pengaturan Profile"* yang ter-zoom maksimal, bersih, proporsional, dan seluruh red bounding box tetap utuh 100%.

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   * Sheet `TC BTN SMART Web`: Baris 65 s/d 74 memuat lengkap 10 TC (TC 3.1 s/d 3.10).
   * Total baris web bertambah menjadi **921 baris** (915 script TC resmi).
2. **SIT Word (`SIT\SIT BTN SMART Web.docx`)**:
   * Table 1 (Info Table): `Jumlah Script : 920`.
   * Table 4 (Modul 3 Notifikasi): Memuat lengkap 10 TC (TC 3.1 s/d 3.10).
3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * Table 8 memuat TC 3.1 (2 SS).
   * Table 9 memuat TC 3.2 s/d 3.10 (total 16 SS).
   * Seluruh 18 screenshot terpasang rapi (`width = 5.90 in`, center alignment, space before/after `5.8 pt`).
   * XML duplicate ID dibersihkan, Table of Contents (TOC) di-refresh via Word COM automation.
4. **Struktur Folder Screenshot (`Hasil Uji\Screenshot\Web\03. Notifikasi\`)**:
   * Memuat lengkap 10 subfolder TC (`3.1` s/d `3.10`) dengan file gambar `.png` hasil crop dan panduan skenario `.txt`.
   * Seluruh file loose `.png` di luar folder telah dibersihkan dan dipindahkan ke dalam subfolder yang sesuai.
5. **Folder Backup uncropped `(Original Full)`**:
   * Folder cadangan uncropped mentah (`18 file PNG`) tersimpan aman di Local D dan Google Drive G.
   * **Zero-Backup Drive H**: Drive H bersih tanpa folder `(Original Full)` dan tanpa file loose, hanya memuat 10 subfolder aktif resmi.
6. **Tri-Drive Verification (MD5 Hash Identik)**:
   * Local D (`D:\Project\BTN Smart\Refactor`)
   * Google Drive H (`H:\My Drive\Zegen\BTN Smart\Refactor`)
   * Google Drive G (`G:\My Drive\Zegen\BTN Smart\Refactor`)
   * Seluruh 3 file dokumen (`.docx`, `.xlsx`) dan 18 gambar `.png` terverifikasi 100% IDENTIK byte-for-byte (MD5 hash verified).
