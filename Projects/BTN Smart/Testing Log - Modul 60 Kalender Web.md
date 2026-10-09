# 📝 Testing Log - Modul 60 Kalender Web (Penyelarasan Menu UI Web)

Catatan pengujian web untuk penambahan fitur baru **Modul 60. Kalender** dan penyesuaian urutan penomoran modul sesuai susunan menu sidebar pada portal **BTN SMART Web**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Web (Portal Admin / Web App)
* **Modul**: Modul 60. Kalender
* **Tanggal Update**: 9 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **TC SELESAI DISESUAIKAN (8 ESSENTIAL TC) - DOKUMEN & HASIL UJI SYNCED** ✅

---

## 🔍 Ringkasan Penyelarasan Urutan Menu (Sidebar UI Web)
Berdasarkan susunan navigasi sidebar pada portal BTN SMART Web, menu **Kalender** terletak sebagai menu utama mandiri (level-1) sebelum menu Report:
```text
...
Sales Force (Modul 43 s/d 59)
Corporate Banking
Inspect Potential Prospek
Kalender           <-- Dialokasikan sebagai Modul 60
Agenda
Report Funding     <-- Bergeser ke Modul 61 s/d 65
Report Lending     <-- Bergeser ke Modul 66 s/d 70
Re-Assign          <-- Bergeser ke Modul 71 s/d 73
Export Center      <-- Bergeser ke Modul 74 s/d 76
```

Sesuai arahan Mas Dani, urutan modul diselaraskan mengikuti tata letak menu sidebar (**Opsi 2**):
* Menu **Kalender** dialokasikan sebagai **Modul 60** (TC `60.1` s/d `60.8`).
* Seluruh modul setelahnya digeser mundur (+1) menjadi **Modul 61 s/d 76**.
* Total Test Case Web bertambah dari **890 TC** menjadi **898 TC**.
* **Catatan Fitur "Daftar Task"**: Tombol *Daftar Task* pada header kalender di-hold sementara karena masih mengalami kendala teknis (issue tidak dapat dibuka). TC dan bukti uji untuk Daftar Task akan disusulkan setelah perbaikan bug selesai.

---

## 📋 Daftar 8 Test Case Baru (Modul 60. Kalender)

| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Steps (Scenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **60.1** | Kalender | - | Membuka halaman Kalender | Positive Case | High | Masuk ke menu utama - Klik menu Kalender pada sidebar | Berhasil menampilkan halaman Kalender beserta ringkasan status dan grid kalender. | Embedded (1 SS) |
| **60.2** | Kalender | - | Melakukan navigasi periode kalender | Positive Case | Normal | Pada halaman Kalender, klik tombol navigasi panah (< / >) atau tombol Hari ini | Berhasil mengubah tampilan periode kalender sesuai pilihan. | Standby (Empty) |
| **60.3** | Kalender | - | Mengubah mode tampilan kalender | Positive Case | Normal | Pada halaman Kalender, klik tombol mode tampilan (Bulan / Minggu / Hari / Daftar) | Berhasil menampilkan kalender berdasarkan mode tampilan yang dipilih. | Standby (Empty) |
| **60.4** | Kalender | - | Memfilter entri kalender berdasarkan kategori | Positive Case | Normal | Centang atau uncentang checkbox kategori entri (Task / Acara / Hari Libur / Time Off / Pola Kerja) | Berhasil menampilkan entri kalender sesuai kategori yang dipilih. | Embedded (1 SS) |
| **60.5** | Kalender | - | Menambahkan task baru | Positive Case | High | Klik tombol Tambah - Pilih Tambah Task - Lengkapi formulir task - Klik Buat Task | Berhasil menambahkan task baru ke dalam kalender. | Embedded (1 SS) |
| **60.6** | Kalender | - | Menambahkan acara baru | Positive Case | High | Klik tombol Tambah - Pilih Tambah Acara - Lengkapi formulir event - Klik Buat Event | Berhasil menambahkan acara baru ke dalam kalender. | Embedded (1 SS) |
| **60.7** | Kalender | - | Menambahkan label baru | Positive Case | High | Klik tombol Kelola Label - Masukkan Nama label - Pilih warna label - Klik Tambah Label | Berhasil menambahkan label baru dan menampilkan notifikasi sukses. | Embedded (2 SS) |
| **60.8** | Kalender | - | Menghapus label | Positive Case | High | Pada daftar label, klik icon Hapus pada label yang dipilih - Konfirmasi Hapus | Berhasil menghapus label dari sistem. | Embedded (1 SS) |

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   * Sheet `TC BTN SMART Web`:
     * Baris 741 s/d 748 disisipkan Modul 60 (TC 60.1 s/d 60.8).
     * Baris 749 s/d 899 memuat pergeseran modul 61 s/d 76.
     * Total Test Case Web resmi: **898 Test Case**.
2. **SIT Word (`SIT\SIT BTN SMART Web.docx`)**:
   * Table 1 (Info Table): `Jumlah Script : 898` dan daftar modul memuat `Modul Kalender`.
   * Menambahkan heading `60. Modul Kalender` dan tabel baru Modul 60 (8 baris TC).
   * Seluruh heading dan tabel Modul 61 s/d 76 digeser rapi (+1).
3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * Menambahkan heading `60. Modul Kalender`.
   * Menambahkan Table 121 (TC 60.1 dengan header UAT) dan Table 122 (TC 60.2 s/d 60.8).
   * Screenshot dari `TC Baru\kalender web\` di-embed rapi dengan proporsi standar (`width=5.9 inch`).
   * Seluruh tabel modul 61 s/d 76 digeser nomor TC-nya.
   * Atribut duplicate XML `paraId` dan `textId` dibersihkan 100%.
4. **Struktur Folder Screenshot (`Hasil Uji\Screenshot\Web\`)**:
   * Folder 60 s/d 75 digeser menjadi 61 s/d 76 beserta seluruh subfolder dan file deskripsi `.txt`.
   * Folder baru `60. Kalender\` dibuat lengkap dengan 8 subfolder TC dan file panduan `.txt`.
5. **Tri-Drive Verification**:
   * Local D (`D:\Project\BTN Smart\Refactor`), Google Drive H (`H:\My Drive\Zegen\BTN Smart\Refactor`), dan Google Drive G (`G:\My Drive\Zegen\BTN Smart\Refactor`) tersinkron identik 100% byte-for-byte (MD5 hash verified).
6. **Git Version Control**:
   * Seluruh perubahan di-commit dan di-push ke branch `main`.
