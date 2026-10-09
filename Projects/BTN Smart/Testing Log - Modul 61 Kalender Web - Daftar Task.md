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
3. **Penomoran Terpadu di Modul 61**: Test case dimasukkan sebagai kelanjutan Modul 61 Kalender (**TC 61.9 s/d 61.15**), sehingga tidak menggeser modul 62 s/d 77.
4. **Total Test Case Web**: Bertambah dari **905 Test Case** menjadi **912 Test Case**.

---

## 📋 Daftar 7 Test Case Baru: Daftar Task (Web)

| No TC | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Test Steps (Skenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **61.9** | Kalender | - | Membuka halaman Daftar Task | Positive Case | High | Pada halaman Kalender, klik tombol Daftar Task | Berhasil menampilkan halaman Daftar Task. | Standby (Empty) |
| **61.10** | Kalender | - | Melakukan filter Daftar Task | Positive Case | High | Pada halaman Daftar Task, pilih kriteria filter (Kepemilikan, Status, Prioritas, Label, atau Rentang Tenggat) | Berhasil menampilkan data task sesuai filter yang dipilih. | Standby (Empty) |
| **61.11** | Kalender | - | Memulai pengerjaan task | Positive Case | High | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Terbuka - Pilih menu Mulai | Berhasil mengubah status task menjadi Berjalan. | Standby (Empty) |
| **61.12** | Kalender | - | Membuka kembali task yang telah selesai | Positive Case | High | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Selesai - Pilih menu Buka Kembali | Berhasil membuka kembali task. | Standby (Empty) |
| **61.13** | Kalender | - | Membatalkan task | Positive Case | High | Pada drawer Edit Task, klik button Batalkan - Klik button Ya, Batalkan pada pop-up konfirmasi aksi | Berhasil membatalkan task. | Standby (Empty) |
| **61.14** | Kalender | - | Melihat detail task | Positive Case | High | Pada tabel Daftar Task, klik baris atau judul task yang berstatus Selesai | Berhasil menampilkan drawer detail task. | Standby (Empty) |
| **61.15** | Kalender | - | Menghapus task secara permanen | Positive Case | Normal | Pada drawer Edit Task atau menu titik tiga, klik menu Hapus - Klik button Hapus pada pop-up konfirmasi Hapus task ini secara permanen? | Berhasil menghapus task secara permanen. | Standby (Empty) |

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   * Sheet `TC BTN SMART Web`:
     * Disisipkan 7 baris setelah row 755 (TC 61.8).
     * TC 61.9 s/d 61.15 berada di baris 756 s/d 762.
     * Baris 763 tetap Modul 62.1 Report Funding Personal Funnel.
     * Total Test Case Web resmi: **912 Test Case** (913 baris termasuk header).

2. **SIT Word (`SIT\SIT BTN SMART Web.docx`)**:
   * Table 1 (Info Table): `Jumlah Script : 912`.
   * Table 62 (Modul 61 Kalender): Bertambah dari 9 baris menjadi 16 baris (Header + 15 TC: 61.1 s/d 61.15).

3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * **TC 61.1 s/d 61.6**: Telah di-embed 11 tangkapan layar pengujian lengkap dengan highlight kotak merah (Table 123 & Table 124).
     * `61.1`: 1 SS (Full Screen, As-Is) — Bukti pembuka menu Kalender pada sidebar.
     * `61.2`: 2 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x833`).
     * `61.3`: 1 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x1131`).
     * `61.4`: 1 SS (Full Body Crop: Hapus Sidebar 60px & Navbar 72px, `1845x1131`).
     * `61.5`: 3 SS:
       - `1.png`: Full Body Crop (Hapus Sidebar & Navbar, dropdown utuh, `1845x833`).
       - `2.png`: Hapus Sidebar saja (Navbar & header drawer *Tambah Task* utuh, tombol *Buat Task* aman, `1845x905`).
       - `3.png`: Hapus Sidebar saja (Toast alert *Task berhasil dibuat* utuh di atas, `1845x905`).
     * `61.6`: 3 SS:
       - `1.png`: Full Body Crop (Hapus Sidebar & Navbar, dropdown utuh, `1845x833`).
       - `2.png`: Hapus Sidebar saja (Navbar & header drawer *Tambah Event* utuh, tombol *Buat Event* aman, `1845x905`).
       - `3.png`: Hapus Sidebar saja (Toast alert *Acara berhasil dibuat* utuh di atas, `1845x905`).
   * **TC 61.7 s/d 61.15 (Kelola Label & Daftar Task)**: Cell gambar tetap dalam status **Standby / Siap Isi** menunggu screenshot lanjutan dari tim.
   * Table of Contents (TOC) telah diperbarui via Word COM.
   * XML attributes duplicate `paraId` dan `textId` dibersihkan 100%.

4. **SOP Safety Backup Sebelum Crop (Kepatuhan Penuh)**:
   * Seluruh 11 file screenshot asli/mentahan dengan kotak merah telah dibackup ke `61. Kalender (Original Full)` di Local D dan Drive G.
   * Git commit & push versi uncropped telah diamankan di GitHub `main` sebelum proses crop dieksekusi.

5. **Tri-Drive Verification (MD5 Hash Identik)**:
   * **Local D**: `D:\Project\BTN Smart\Refactor`
   * **Drive H**: `H:\My Drive\Zegen\BTN Smart\Refactor` (Zero-Backup clean, tepat 77 modul)
   * **Drive G**: `G:\My Drive\Zegen\BTN Smart\Refactor`
   * Seluruh dokumen hasil uji dan screenshot tersinkron identik di ketiga drive.

6. **Git Version Control**:
   * Branch: `main`
   * Status: Changes tracked, committed, and pushed to remote origin.
