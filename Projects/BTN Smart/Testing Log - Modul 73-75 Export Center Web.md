# 📝 Testing Log - Modul 73, 74, 75 Export Center Web (Penyelarasan UI Baru)

Catatan pengujian web untuk penyesuaian UI baru **Export Center** menggantikan modul lama **Exported Data Management** pada portal **BTN SMART Web**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Web (Portal Admin / Web App)
* **Modul**:
  * Modul 73: Export Center - Riwayat Export (8 TC)
  * Modul 74: Export Center - Persetujuan Export (9 TC)
  * Modul 75: Export Center - Aktivitas Export (8 TC)
* **Tanggal Update**: 9 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **SELESAI DISESUAIKAN (25 ESSENTIAL TC) - DOKUMEN & HASIL UJI SYNCED** ✅

---

## 🔍 Ringkasan Fitur & Perubahan (Export Center UI Baru)
Modul **Export Center** adalah pembaruan menyeluruh dari modul lama (*Exported Data Management*) yang menyelaraskan alur inisiasi, persetujuan, dan pemantauan data export di BTN SMART Web:

1. **Modul 73: Riwayat Export (Inisiator / Sales)**
   * Menampilkan riwayat permohonan ekspor data milik pengguna yang sedang login.
   * Tab status: **Semua**, **Menunggu Persetujuan**, **Berhasil**, **Ditolak**, dan **Kadaluwarsa**.
   * Fitur pencarian kata kunci valid dan handling data tidak ditemukan (invalid).
   * Filter drawer berdasarkan rentang tanggal, jenis modul, dan format berkas.
   * Detail drawer informasi pengajuan dan tombol unduh file yang sudah disetujui.

2. **Modul 74: Persetujuan Export (Approver / Supervisor / Monitoring)**
   * Menampilkan daftar antrean permohonan ekspor data dari tim sales/inisiator.
   * Tab status persetujuan: **Semua**, **Menunggu Persetujuan**, **Disetujui**, dan **Ditolak**.
   * Aksi persetujuan (**Approve**) dan penolakan (**Reject**) langsung dari baris tabel.
   * Drawer detail permohonan sebelum pengambilan keputusan.

3. **Modul 75: Aktivitas Export (Auditing / Management Overview)**
   * Pemantauan riwayat menyeluruh seluruh aktivitas ekspor di sistem.
   * Tab filter status, pencarian data, filter drawer, reset filter, detail drawer, dan pengunduhan berkas.

---

## 📋 Daftar 25 Test Case Baru (Essential TC)

### Modul 73: Export Center - Riwayat Export
| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Steps (Scenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **73.1** | Export Center | Riwayat Export | Membuka halaman Riwayat Export | Positive Case | High | Masuk ke menu Export Center - Klik submenu Riwayat Export | Berhasil menampilkan halaman Riwayat Export. | Embedded (1 SS) |
| **73.2** | Export Center | Riwayat Export | Mencari data riwayat export dengan kata kunci valid | Positive Case | Normal | Masukkan kata kunci valid pada Search Bar | Berhasil menampilkan data riwayat export yang dicari. | Embedded (1 SS) |
| **73.3** | Export Center | Riwayat Export | Mencari data riwayat export dengan kata kunci tidak valid | Negative Case | Normal | Masukkan kata kunci tidak valid pada Search Bar | Berhasil menampilkan informasi data tidak ditemukan. | Standby (Empty) |
| **73.4** | Export Center | Riwayat Export | Melihat data riwayat export berdasarkan status | Positive Case | Normal | Pada halaman Riwayat Export, klik tab status (Semua / Menunggu Persetujuan / Berhasil / Ditolak / Kadaluwarsa) | Berhasil menampilkan data riwayat export berdasarkan status yang dipilih. | Embedded (1 SS) |
| **73.5** | Export Center | Riwayat Export | Melakukan filter data riwayat export | Positive Case | Normal | Klik tombol Filter - Tentukan parameter filter - Klik Terapkan | Berhasil memfilter data riwayat export sesuai parameter. | Embedded (1 SS) |
| **73.6** | Export Center | Riwayat Export | Mereset filter data riwayat export | Positive Case | Normal | Klik tombol Filter - Klik tombol Reset Filter | Berhasil mereset filter dan menampilkan seluruh data riwayat export. | Embedded (1 SS) |
| **73.7** | Export Center | Riwayat Export | Melihat detail riwayat export | Positive Case | High | Pada tabel data riwayat export, klik icon Detail | Berhasil menampilkan drawer detail riwayat export. | Embedded (1 SS) |
| **73.8** | Export Center | Riwayat Export | Mengunduh file data export yang tersedia | Positive Case | High | Pada baris data yang berstatus Berhasil, klik icon Download | Berhasil mengunduh file data export. | Embedded (1 SS) |

### Modul 74: Export Center - Persetujuan Export
| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Steps (Scenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **74.1** | Export Center | Persetujuan Export | Membuka halaman Persetujuan Export | Positive Case | High | Masuk ke menu Export Center - Klik submenu Persetujuan Export | Berhasil menampilkan halaman Persetujuan Export. | Embedded (1 SS) |
| **74.2** | Export Center | Persetujuan Export | Mencari data persetujuan export dengan kata kunci valid | Positive Case | Normal | Masukkan kata kunci valid pada Search Bar | Berhasil menampilkan data persetujuan export yang dicari. | Embedded (1 SS) |
| **74.3** | Export Center | Persetujuan Export | Mencari data persetujuan export dengan kata kunci tidak valid | Negative Case | Normal | Masukkan kata kunci tidak valid pada Search Bar | Berhasil menampilkan informasi data tidak ditemukan. | Standby (Empty) |
| **74.4** | Export Center | Persetujuan Export | Melihat data persetujuan export berdasarkan status | Positive Case | Normal | Pada halaman Persetujuan Export, klik tab status (Semua / Menunggu Persetujuan / Disetujui / Ditolak) | Berhasil menampilkan data persetujuan export berdasarkan status yang dipilih. | Embedded (1 SS) |
| **74.5** | Export Center | Persetujuan Export | Melakukan filter data persetujuan export | Positive Case | Normal | Klik tombol Filter - Tentukan parameter filter - Klik Terapkan | Berhasil memfilter data persetujuan export sesuai parameter. | Embedded (1 SS) |
| **74.6** | Export Center | Persetujuan Export | Mereset filter data persetujuan export | Positive Case | Normal | Klik tombol Filter - Klik tombol Reset Filter | Berhasil mereset filter dan menampilkan seluruh data persetujuan export. | Embedded (1 SS) |
| **74.7** | Export Center | Persetujuan Export | Melakukan approval data pengajuan export | Positive Case | High | Pada baris pengajuan, klik icon Checklist (Approve) - Konfirmasi persetujuan | Berhasil menyetujui pengajuan export data. | Embedded (1 SS) |
| **74.8** | Export Center | Persetujuan Export | Melakukan reject data pengajuan export | Positive Case | High | Pada baris pengajuan, klik icon Silang (Reject) - Konfirmasi penolakan | Berhasil menolak pengajuan export data. | Embedded (1 SS) |
| **74.9** | Export Center | Persetujuan Export | Melihat detail pengajuan export | Positive Case | High | Pada tabel data persetujuan export, klik icon Detail | Berhasil menampilkan drawer detail pengajuan export. | Embedded (1 SS) |

### Modul 75: Export Center - Aktivitas Export
| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Steps (Scenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **75.1** | Export Center | Aktivitas Export | Membuka halaman Aktivitas Export | Positive Case | High | Masuk ke menu Export Center - Klik submenu Aktivitas Export | Berhasil menampilkan halaman Aktivitas Export. | Embedded (1 SS) |
| **75.2** | Export Center | Aktivitas Export | Mencari data aktivitas export dengan kata kunci valid | Positive Case | Normal | Masukkan kata kunci valid pada Search Bar | Berhasil menampilkan data aktivitas export yang dicari. | Embedded (1 SS) |
| **75.3** | Export Center | Aktivitas Export | Mencari data aktivitas export dengan kata kunci tidak valid | Negative Case | Normal | Masukkan kata kunci tidak valid pada Search Bar | Berhasil menampilkan informasi data tidak ditemukan. | Standby (Empty) |
| **75.4** | Export Center | Aktivitas Export | Melihat data aktivitas export berdasarkan status | Positive Case | Normal | Pada halaman Aktivitas Export, klik tab status (Semua / Menunggu Persetujuan / Berhasil / Ditolak / Kadaluwarsa) | Berhasil menampilkan data aktivitas export berdasarkan status yang dipilih. | Embedded (1 SS) |
| **75.5** | Export Center | Aktivitas Export | Melakukan filter data aktivitas export | Positive Case | Normal | Klik tombol Filter - Tentukan parameter filter - Klik Terapkan | Berhasil memfilter data aktivitas export sesuai parameter. | Embedded (1 SS) |
| **75.6** | Export Center | Aktivitas Export | Mereset filter data aktivitas export | Positive Case | Normal | Klik tombol Filter - Klik tombol Reset Filter | Berhasil mereset filter dan menampilkan seluruh data aktivitas export. | Embedded (1 SS) |
| **75.7** | Export Center | Aktivitas Export | Melihat detail aktivitas export | Positive Case | High | Pada tabel data aktivitas export, klik icon Detail | Berhasil menampilkan drawer detail aktivitas export. | Embedded (1 SS) |
| **75.8** | Export Center | Aktivitas Export | Mengunduh file data export yang tersedia | Positive Case | High | Pada baris data yang berstatus Berhasil, klik icon Download | Berhasil mengunduh file data export. | Embedded (1 SS) |

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   * Sheet `TC BTN SMART Web` baris 867 s/d 891 diperbarui menggantikan TC lama menjadi 25 TC baru:
     * 73.1 s/d 73.8 (Riwayat Export)
     * 74.1 s/d 74.9 (Persetujuan Export)
     * 75.1 s/d 75.8 (Aktivitas Export)
   * Total baris web tetap **890 Test Case** (tidak mengubah nomor modul lain).
2. **SIT Word (`SIT\SIT BTN SMART Web.docx`)**:
   * Table 1 (Info Table) diperbarui memuat nama modul baru:
     * `Modul Export Center - Riwayat Export`
     * `Modul Export Center - Persetujuan Export`
     * `Modul Export Center - Aktivitas Export`
   * Heading modul 73, 74, 75 dan Tables 74, 75, 76 diperbarui memuat 25 TC baru dengan format list strip `-` (tanpa angka `1. 2.`). Total script tetap **890 TC**.
3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * Table 147 s/d Table 152 diperbarui.
   * Screenshot bukti uji dari `TC Baru\export center\` telah di-embed ke masing-masing baris tabel dengan proporsi rapi (`width=5.9 inch`).
   * Atribut duplicate XML `w14:paraId` dan `w14:textId` telah dibersihkan sehingga dokumen valid tanpa warning saat dibuka di MS Word.
4. **Struktur Folder Screenshot (`Hasil Uji\Screenshot\Web\`)**:
   * Folder lama dihapus:
     * `73. Export data management - Riwayat export saya`
     * `74. Export data management - Persetujuan export`
     * `75. Export data management - Management export`
   * Folder baru dibuat lengkap dengan subfolder TC dan file panduan `.txt`:
     * `73. Export Center - Riwayat Export` (8 subfolder)
     * `74. Export Center - Persetujuan Export` (9 subfolder)
     * `75. Export Center - Aktivitas Export` (8 subfolder)
5. **Tri-Drive Verification**:
   * Local D (`D:\Project\BTN Smart\Refactor`)
   * Google Drive H (`H:\My Drive\Zegen\BTN Smart\Refactor`)
   * Google Drive G (`G:\My Drive\Zegen\BTN Smart\Refactor`)
   * Seluruh dokumen dan folder screenshot disinkronkan dan diverifikasi 100% identik byte-for-byte (MD5 hash verified).
6. **Git Version Control**:
   * Seluruh perubahan telah di-commit dan di-push ke GitHub repository branch `main`.
