# 📝 Testing Log - Modul 61 Kalender Web (Fitur Daftar Task)

Catatan pengujian portal **BTN SMART Web** untuk penambahan test case dan bukti uji fitur **Daftar Task** pada **Modul 61. Kalender**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Web (Portal Admin / Web App)
* **Modul**: Modul 61. Kalender (Tanpa Sub Menu)
* **Fitur**: Daftar Task (Header Kalender Web)
* **Tanggal Update**: 9 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **TC SELESAI DIEKSEKUSI (7 TC) - DOKUMEN & HASIL UJI SYNCED** ✅

---

## 🔍 Ringkasan Penambahan Test Case (Daftar Task)
Fitur **Daftar Task** diakses langsung melalui tombol/menu pada header kalender web (Breadcrumb: `Kalender / Daftar Task`). Sesuai arahan Mas Dani:
1. **Tidak Ada Sub Menu**: Kolom Sub Modul dikosongkan (`-` / `None`).
2. **Standardisasi Penamaan Mencontek Mobile**: Judul test case, alur, dan format expected result diselaraskan dengan standar **Modul 10 Kalender versi Mobile** (misal: *Memulai pengerjaan task*, *Membatalkan task*, *Membuka kembali task yang telah selesai*).
3. **Penomoran Terpadu di Modul 61**: Test case dimasukkan sebagai kelanjutan Modul 61 Kalender (**TC 61.9 s/d 61.17**), sehingga tidak menggeser modul 62 s/d 77.
4. **Total Test Case Web**: Bertambah menjadi **916 Test Case** (resmi terdaftar di SIT Word & Excel).

---

## 📋 Daftar 9 Test Case Baru: Daftar Task (Web)

| No TC | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Test Steps (Skenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **61.9** | Kalender | - | Membuka halaman Daftar Task | Positive Case | High | Pada halaman Kalender, klik tombol Daftar Task | Berhasil menampilkan halaman Daftar Task. | **2 SS Embedded** ✅ |
| **61.10** | Kalender | - | Melakukan filter Daftar Task | Positive Case | High | Pada halaman Daftar Task, pilih kriteria filter (Kepemilikan, Status, Prioritas, Label, atau Rentang Tenggat) | Berhasil menampilkan data task sesuai filter yang dipilih. | **1 SS Embedded** ✅ |
| **61.11** | Kalender | - | Melakukan pencarian task | Positive Case | Normal | Pada halaman Daftar Task, masukkan kata kunci pada field Cari task | Berhasil menampilkan data task sesuai kata kunci pencarian. | Standby (Empty) |
| **61.12** | Kalender | - | Mereset filter Daftar Task | Positive Case | Normal | Pada halaman Daftar Task, klik tombol Reset Filter | Berhasil mereset filter dan menampilkan seluruh data task ke kondisi default. | Standby (Empty) |
| **61.13** | Kalender | - | Memulai pengerjaan task | Positive Case | High | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Terbuka - Pilih menu Mulai | Berhasil mengubah status task menjadi Berjalan. | Standby (Empty) |
| **61.14** | Kalender | - | Membuka kembali task yang telah selesai | Positive Case | High | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Selesai - Pilih menu Buka Kembali | Berhasil membuka kembali task. | Standby (Empty) |
| **61.15** | Kalender | - | Membatalkan task | Positive Case | High | Pada drawer Edit Task, klik button Batalkan - Klik button Ya, Batalkan pada pop-up konfirmasi aksi | Berhasil membatalkan task. | Standby (Empty) |
| **61.16** | Kalender | - | Melihat detail task | Positive Case | High | Pada tabel Daftar Task, klik baris atau judul task yang berstatus Selesai | Berhasil menampilkan drawer detail task. | Standby (Empty) |
| **61.17** | Kalender | - | Menghapus task secara permanen | Positive Case | Normal | Pada drawer Edit Task atau menu titik tiga, klik menu Hapus - Klik button Hapus pada pop-up konfirmasi Hapus task ini secara permanen? | Berhasil menghapus task secara permanen. | Standby (Empty) |

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   * Sheet `TC BTN SMART Web`:
     * Disisipkan total 9 baris setelah row 755 (TC 61.8).
     * TC 61.9 s/d 61.17 berada di baris 756 s/d 766.
     * Baris 767 tetap Modul 62.1 Report Funding Personal Funnel.
     * Total Test Case Web resmi: **916 Test Case** (917 baris termasuk header).

2. **SIT Word (`SIT\SIT BTN SMART Web.docx`)**:
   * Table 1 (Info Table): `Jumlah Script : 916`.
   * Table 62 (Modul 61 Kalender): Bertambah menjadi 18 baris (Header + 17 TC: 61.1 s/d 61.17).

3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * **Total Bukti Uji Ter-embed**: **20 Tangkapan Layar** (TC 61.1 s/d 61.10).
   * **TC 61.1 s/d 61.6 (11 SS)**:
     * `61.1`: 1 SS (Full Screen, As-Is) — Bukti pembuka menu Kalender pada sidebar.
     * `61.2`: 2 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x833`).
     * `61.3`: 1 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x1131`).
     * `61.4`: 1 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x1131`).
     * `61.5`: 3 SS (Dropdown `1845x833`, Drawer `1845x905`, Toast `1845x905`).
     * `61.6`: 3 SS (Dropdown `1845x833`, Drawer `1845x905`, Toast `1845x905`).
   * **TC 61.7 s/d 61.10 (9 SS Baru)**:
     * `61.7`: 3 SS (Kelola Label: 1. Full Body Crop tombol Kelola Label `1845x833`, 2. Drawer Buat Label `1845x905`, 3. Toast Sukses Buat Label `1845x905`).
     * `61.8`: 3 SS (Hapus Label: 1. Drawer List Label `1845x905`, 2. Popover Konfirmasi Hapus `1860x905`, 3. Toast Sukses Hapus Label `1845x905`).
     * `61.9`: 2 SS (Buka Daftar Task: 1. Full Body Crop tombol Daftar Task `1845x833`, 2. Full Body Crop tabel Daftar Task `1845x833`).
     * `61.10`: 1 SS (Filter Daftar Task: 1. Full Body Crop tabel terfilter `1845x833`).
   * **TC 61.11 s/d 61.17 (Daftar Task Actions & Controls)**:
     * Cell gambar dalam status **STANDBY / KOSONG / NO PICTURE** sesuai permintaan Mas Dani agar tester tim yang mengisi bukti screenshot-nya.
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
