# 📝 Testing Log - Modul 61 Kalender Web (Fitur Daftar Task)

Catatan pengujian portal **BTN SMART Web** untuk penambahan test case dan bukti uji fitur **Daftar Task** pada **Modul 61. Kalender**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Web (Portal Admin / Web App)
* **Modul**: Modul 61. Kalender (Tanpa Sub Menu)
* **Fitur**: Daftar Task (Header Kalender Web)
* **Tanggal Update**: 9 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **TC SELESAI DIEKSEKUSI (18 TC LENGKAP, 2 TC STANDBY) - DOKUMEN & HASIL UJI SYNCED** ✅

---

## 🔍 Ringkasan Penambahan Test Case (Daftar Task)
Fitur **Daftar Task** diakses langsung melalui tombol/menu pada header kalender web (Breadcrumb: `Kalender / Daftar Task`). Sesuai arahan Mas Dani:
1. **Tidak Ada Sub Menu**: Kolom Sub Modul dikosongkan (`-` / `None`).
2. **Standardisasi Penamaan Mencontek Mobile**: Judul test case, alur, dan format expected result diselaraskan dengan standar **Modul 10 Kalender versi Mobile** (misal: *Memulai pengerjaan task*, *Membatalkan task*, *Membuka kembali task yang telah selesai*, *Mengubah data task*, *Membagikan task kepada user*, *Menghapus penugasan task kepada user*).
3. **Penomoran Terpadu di Modul 61**: Test case dimasukkan sebagai kelanjutan Modul 61 Kalender (**TC 61.9 s/d 61.20**), sehingga tidak menggeser modul 62 s/d 77.
4. **Total Test Case Web**: Bertambah menjadi **919 Test Case** (resmi terdaftar di SIT Word & Excel).

---

## 📋 Daftar 12 Test Case Fitur Daftar Task (Web)

| No TC | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Test Steps (Skenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **61.9** | Kalender | - | Membuka halaman Daftar Task | Positive Case | High | Pada halaman Kalender, klik tombol Daftar Task | Berhasil menampilkan halaman Daftar Task. | **2 SS Embedded** ✅ |
| **61.10** | Kalender | - | Melakukan filter Daftar Task | Positive Case | High | Pada halaman Daftar Task, pilih kriteria filter (Kepemilikan, Status, Prioritas, Label, atau Rentang Tenggat) | Berhasil menampilkan data task sesuai filter yang dipilih. | **1 SS Embedded** ✅ |
| **61.11** | Kalender | - | Mencari task dengan keyword valid | Positive Case | Normal | Pada halaman Daftar Task, masukkan kata kunci valid pada field Cari task | Berhasil menampilkan data task yang sesuai dengan kata kunci pencarian. | **1 SS Embedded** ✅ |
| **61.12** | Kalender | - | Mencari task dengan keyword tidak valid | Negative Case | Normal | Pada halaman Daftar Task, masukkan kata kunci yang tidak valid / tidak terdaftar pada field Cari task | Berhasil menampilkan informasi bahwa data task tidak ditemukan. | **1 SS Embedded** ✅ |
| **61.13** | Kalender | - | Mereset filter Daftar Task | Positive Case | Normal | Pada halaman Daftar Task, klik tombol Reset Filter | Berhasil mereset filter dan menampilkan seluruh data task ke kondisi default. | **1 SS Embedded** ✅ |
| **61.14** | Kalender | - | Memulai pengerjaan task | Positive Case | High | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Terbuka - Pilih menu Mulai | Berhasil mengubah status task menjadi Berjalan. | **2 SS Embedded** ✅ |
| **61.15** | Kalender | - | Membuka kembali task yang telah selesai | Positive Case | High | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Selesai - Pilih menu Buka Kembali | Berhasil membuka kembali task. | **2 SS Embedded** ✅ |
| **61.16** | Kalender | - | Membatalkan task | Positive Case | High | Pada drawer Edit Task, klik button Batalkan - Klik button Ya, Batalkan pada pop-up konfirmasi aksi | Berhasil membatalkan task. | **2 SS Embedded** ✅ |
| **61.17** | Kalender | - | Mengubah data task | Positive Case | High | Pada tabel Daftar Task, klik baris task atau icon titik tiga - Pilih menu Edit - Ubah data pada drawer Edit Task - Klik tombol Simpan | Berhasil mengubah data task. | **2 SS Embedded** ✅ |
| **61.18** | Kalender | - | Menghapus task secara permanen | Positive Case | Normal | Pada drawer Edit Task atau menu titik tiga, klik menu Hapus - Klik button Hapus pada pop-up konfirmasi Hapus task ini secara permanen? | Berhasil menghapus task secara permanen. | **2 SS Embedded** ✅ |
| **61.19** | Kalender | - | Membagikan task kepada user | Positive Case | High | Pada drawer Edit Task, klik button Bagikan - Pada pop-up Bagikan Task, pilih penerima dan role - Klik Tambahkan | Berhasil membagikan task kepada user. | Standby (Empty / Menunggu SS) ⏳ |
| **61.20** | Kalender | - | Menghapus penugasan task kepada user | Positive Case | Normal | Pada pop-up Bagikan Task, klik icon Hapus (tempat sampah) pada user yang ditugaskan - Tutup pop-up | Berhasil menghapus penugasan task kepada user. | Standby (Empty / Menunggu SS) ⏳ |

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   * Sheet `TC BTN SMART Web`:
     * TC 61.17 diperbarui menjadi `Mengubah data task`.
     * Ditambahkan baris baru untuk TC 61.19 dan TC 61.20.
     * Baris 770 tetap Modul 62.1 Report Funding Personal Funnel.
     * Total Test Case Web resmi: **919 Test Case** (920 baris termasuk header).

2. **SIT Word (`SIT\SIT BTN SMART Web.docx`)**:
   * Table 1 (Info Table): `Jumlah Script : 919`.
   * Table 62 (Modul 61 Kalender): Bertambah menjadi 21 baris (Header + 20 TC: 61.1 s/d 61.20).

3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * **Total Bukti Uji Ter-embed**: **33 Tangkapan Layar** (TC 61.1 s/d 61.18 lengkap 100%).
   * **TC 61.19 & 61.20 (Bagikan & Hapus Bagikan Task)**:
     * Cell gambar dalam status **STANDBY / KOSONG / NO PICTURE** sesuai SOP penambahan TC baru agar tester tim yang mengisi bukti screenshot-nya.
   * **TC 61.1 s/d 61.6 (11 SS)**:
     * `61.1`: 1 SS (Full Screen, As-Is) — Bukti pembuka menu Kalender pada sidebar.
     * `61.2`: 2 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x833`).
     * `61.3`: 1 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x1131`).
     * `61.4`: 1 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x1131`).
     * `61.5`: 3 SS (Dropdown `1845x833`, Drawer `1845x905`, Toast `1845x905`).
     * `61.6`: 3 SS (Dropdown `1845x833`, Drawer `1845x905`, Toast `1845x905`).
   * **TC 61.7 s/d 61.10 (9 SS)**:
     * `61.7`: 3 SS (Kelola Label: 1. Full Body Crop tombol Kelola Label `1845x833`, 2. Drawer Buat Label `1845x905`, 3. Toast Sukses Buat Label `1845x905`).
     * `61.8`: 3 SS (Hapus Label: 1. Drawer List Label `1845x905`, 2. Popover Konfirmasi Hapus `1860x905`, 3. Toast Sukses Hapus Label `1845x905`).
     * `61.9`: 2 SS (Buka Daftar Task: 1. Full Body Crop tombol Daftar Task `1845x833`, 2. Full Body Crop tabel Daftar Task `1845x833`).
     * `61.10`: 1 SS (Filter Daftar Task: 1. Full Body Crop tabel terfilter `1845x833`).
   * **TC 61.11 s/d 61.18 (13 SS Ter-embed)**:
     * `61.11`: 1 SS (Cari valid: Full Body Crop `1845x833`).
     * `61.12`: 1 SS (Cari invalid: Full Body Crop `1845x833`).
     * `61.13`: 1 SS (Reset filter: Full Body Crop `1845x833`).
     * `61.14`: 2 SS (Mulai task: 1. Dropdown titik tiga 'Mulai' `1845x833`, 2. Toast alert 'Task dimulai' `1845x905` [Navbar dipertahankan]).
     * `61.15`: 2 SS (Buka kembali: 1. Dropdown titik tiga 'Buka Kembali' `1845x833`, 2. Toast alert 'Task dibuka kembali' `1845x905` [Navbar dipertahankan]).
     * `61.16`: 2 SS (Batalkan task: 1. Dropdown titik tiga 'Batalkan' `1845x833`, 2. Toast alert 'Task dibatalkan' `1845x905` [Navbar dipertahankan]).
     * `61.17`: 2 SS (Mengubah data task: 1. Drawer Edit Task `1845x905`, 2. Tabel Daftar Task hasil ubah `1845x833`).
     * `61.18`: 2 SS (Hapus permanen: 1. Dropdown titik tiga 'Hapus Permanen' `1845x833`, 2. Toast alert 'Task dihapus permanen' `1845x905` [Navbar dipertahankan]).
   * Table of Contents (TOC) telah diperbarui via Word COM.
   * XML attributes duplicate `paraId` dan `textId` dibersihkan 100%.

4. **SOP Safety Backup Sebelum Crop (Kepatuhan Penuh)**:
   * Seluruh screenshot asli/mentahan dengan kotak merah telah dibackup ke `61. Kalender (Original Full)` di Local D dan Drive G.
   * Git commit & push versi uncropped selalu diamankan terlebih dahulu.

5. **Tri-Drive Verification (MD5 Hash Identik)**:
   * **Local D**: `D:\Project\BTN Smart\Refactor`
   * **Drive H**: `H:\My Drive\Zegen\BTN Smart\Refactor` (Zero-Backup clean, tepat 77 modul)
   * **Drive G**: `G:\My Drive\Zegen\BTN Smart\Refactor`
   * Seluruh dokumen hasil uji, SIT Excel, SIT Word, dan folder screenshot tersinkron identik di ketiga drive.

6. **Git Version Control**:
   * Branch: `main`
   * Status: Changes tracked, committed, and pushed to remote origin.
