# 📝 Testing Log - Modul 03 Notifikasi Web (Penyelarasan Menu UI Web)

Catatan pengujian web untuk penambahan fitur baru **Modul 03. Notifikasi** dan penyesuaian urutan penomoran modul sesuai susunan antarmuka portal **BTN SMART Web**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Web (Portal Admin / Web App)
* **Modul**: Modul 03. Notifikasi
* **Tanggal Update**: 9 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **TC SELESAI DISESUAIKAN (7 ESSENTIAL TC) - DOKUMEN & HASIL UJI SYNCED** ✅

---

## 🔍 Ringkasan Penyelarasan Urutan Menu & Header Navbar
Berdasarkan arahan Mas Dani dan analisis navigasi antarmuka portal BTN SMART Web:
1. Fitur **Notifikasi** terletak pada header bar (icon lonceng) yang diakses langsung setelah login & navigasi profil, serta terintegrasi dengan menu **Pengaturan Profile - Notifikasi**.
2. Modul Notifikasi dialokasikan sebagai **Modul 3** mandiri (TC `3.1` s/d `3.7`), tepat setelah **Modul 2 Profile**.
3. Seluruh modul setelahnya (Modul 3 s/d 76) digeser mundur (+1) secara berurutan menjadi **Modul 4 s/d 77**.
4. Judul Test Case pertama disepakati **tanpa kata "popover"**: *"Membuka notifikasi pada header"*.
5. Total Test Case Web resmi bertambah dari **898 TC** menjadi **905 TC** (total 77 modul).

---

## 📋 Daftar 9 Test Case Baru (Modul 03. Notifikasi)

| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Steps (Scenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **3.1** | Notifikasi | - | Membuka notifikasi pada header | Positive Case | High | Klik icon Lonceng (Notifikasi) pada header bar | Berhasil menampilkan daftar notifikasi terbaru. | Embedded (2 SS) |
| **3.2** | Notifikasi | - | Mencari notifikasi dengan kata kunci valid | Positive Case | Normal | Masukkan kata kunci valid pada kolom Cari notifikasi | Berhasil menampilkan data notifikasi yang dicari. | Embedded (1 SS) |
| **3.3** | Notifikasi | - | Mencari notifikasi dengan kata kunci tidak valid | Negative Case | Normal | Masukkan kata kunci tidak valid pada kolom Cari notifikasi | Berhasil menampilkan informasi data tidak ditemukan. | Standby (Empty) |
| **3.4** | Notifikasi | - | Melihat data notifikasi Belum Dibaca | Positive Case | Normal | Pada daftar notifikasi, klik tab Belum Dibaca | Berhasil menampilkan data notifikasi belum dibaca. | Embedded (1 SS) |
| **3.5** | Notifikasi | - | Melihat data notifikasi Diarsipkan | Positive Case | Normal | Pada halaman Pengaturan Profile - Notifikasi, klik tab Diarsipkan | Berhasil menampilkan data notifikasi diarsipkan. | Embedded (1 SS) |
| **3.6** | Notifikasi | - | Menandai semua notifikasi telah dibaca | Positive Case | High | Pada notifikasi, klik tombol Tandai semua dibaca | Berhasil menandai seluruh notifikasi telah dibaca. | Embedded (1 SS) |
| **3.7** | Notifikasi | - | Membuka halaman Notifikasi pada Pengaturan Profile | Positive Case | High | Klik tombol Lihat semua pada notifikasi header (atau masuk via menu Pengaturan Profile) | Berhasil menampilkan halaman penuh Notifikasi pada Pengaturan Profile. | Embedded (1 SS) |
| **3.8** | Notifikasi | - | Mengarsipkan notifikasi | Positive Case | High | Pada halaman Detail Notifikasi, klik tombol Arsipkan | Berhasil mengarsipkan notifikasi. | Embedded (2 SS: Modal & Hasil Kotak Merah) |
| **3.9** | Notifikasi | - | Membatalkan arsip notifikasi | Positive Case | High | Pada halaman Detail Notifikasi yang diarsipkan, klik tombol Kembalikan dari arsip | Berhasil membatalkan arsip notifikasi. | Embedded (2 SS: Modal & Hasil Kotak Merah) |

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   * Sheet `TC BTN SMART Web`:
     * Baris 65 s/d 73 memuat Modul 3 (TC 3.1 s/d 3.9).
     * Total Test Case Web resmi: **914 Test Case**.
2. **SIT Word (`SIT\SIT BTN SMART Web.docx`)**:
   * Table 1 (Info Table): `Jumlah Script : 914`.
   * Table 4 (Modul 3 Notifikasi): Memuat lengkap 9 TC (TC 3.1 s/d 3.9).
3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * Table 8 (TC 3.1) memuat 2 screenshot hasil crop bersih.
   * Table 9 (TC 3.2 s/d 3.9) memuat screenshot lengkap:
     * TC 3.2, 3.4, 3.5, 3.6, 3.7: Masing-masing 1 screenshot.
     * **TC 3.8**: Memuat 2 screenshot (1.png modal konfirmasi + 2.png halaman berkotak merah buatan Mas Dani).
     * **TC 3.9**: Memuat 2 screenshot (1.png modal konfirmasi + 2.png halaman berkotak merah buatan Mas Dani).
   * Modul 61 Kalender tetap dalam status Standby (tanpa gambar) sesuai arahan tim.
4. **Standardisasi Crop Screenshot (Clean Scrollbar Policy)**:
   * **TC 3.1, 3.2, 3.4, 3.6**: Dipotong track scrollbar abu-abu 15px di tepi kanan (`1920x863 -> 1905x863`) agar bebas dari garis scrollbar browser, dengan tampilan dashboard & popover tetap utuh.
   * **TC 3.5 & 3.7**: Full-page view Pengaturan Profile (`1920x1127`) tetap bersih as-is.
   * **TC 3.8 & 3.9**:
     * `1.png` (Modal detail/konfirmasi): Dipotong scrollbar 8px di tepi kanan (`1024x460 -> 1016x460`), menonjolkan tombol aksi Arsipkan dan Kembalikan dari arsip.
     * `2.png` (Full page hasil dengan kotak merah): Dipotong scrollbar 15px di tepi kanan (`1920x863 -> 1905x863`), kotak merah asli tetap utuh dan presisi.
5. **Struktur Folder Screenshot (`Hasil Uji\Screenshot\Web\03. Notifikasi\`)**:
   * Memuat lengkap 9 subfolder TC (`3.1` s/d `3.9`) dengan file gambar `.png` hasil crop dan panduan skenario `.txt`.
6. **Tri-Drive Verification & Zero-Backup Policy Compliance**:
   * **Drive Utama H (`muhammaddanihaikal.dev@gmail.com`)**: Menerapkan Zero-Backup Policy 100%. Seluruh folder cadangan (`Original Full` dan `Safety Backup`) telah dibersihkan total. Hanya menyisakan **tepat 77 folder modul resmi** (`01. Login` s/d `77. Export Center - Aktivitas Export`) yang bersih dan rapi.
   * **Backup Drive G (`dainnaxjakarta91@gmail.com`) & Local D**: Menampung seluruh folder cadangan mentah (`Original Full` / `Safety Backup`) sebanyak 55 folder secara utuh dan aman sebagai arsip histori pengujian.
   * File dokumen (`Test Case.xlsx`, `SIT BTN SMART Web.docx`, `Dokumen_Hasil_Uji_Web.docx`) tersinkron identik 100% byte-for-byte (MD5 hash verified) di ketiga lokasi.
6. **Git Version Control**:
   * Seluruh file dokumen, folder screenshot, script pembantu, dan log pengujian di-commit serta di-push ke branch `main`.
