# 📝 Testing Log - Modul 15 Agenda - Pengingat (Refactor Task & Acara)

Catatan pengujian mobile untuk **Modul 15. Agenda - Pengingat** pada aplikasi **BTN Smart Mobile**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN Smart Mobile (Android)
* **Modul**: Modul 15. Agenda - Pengingat
* **Tanggal Update**: 8 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **TC TERBARU TERDAFTAR (14 TC) - SCREENSHOT STANDBY (BLANK / EMPTY)** ⏳

---

## 🔍 Ringkasan Perubahan Arsitektur Fitur (Refactor)
Aplikasi BTN Smart Mobile telah melakukan perombakan besar (refactor) pada modul Pengingat:
* **Versi Lama**: Hanya memuat tab statis (Aktif & Selesai) dan form pengingat tunggal sederhana.
* **Versi Refactor**: Mengintegrasikan konsep agenda kerja berbasis **Task (Tugas)** dan **Acara (Event)**:
  1. Halaman utama memiliki 2 tab: **Task** (status `TERBUKA`, `SELESAI`) dan **Acara** (status `TERJADWAL`).
  2. Tombol `+ Baru` memiliki opsi penambahan **Tambah Task** dan **Tambah Acara**.
  3. Detail Task & Detail Acara dilengkapi tab **Detail** dan tab **Aktivitas & Percakapan (Komentar)**.
  4. Fitur pengubahan data (**Edit Task** / **Edit Acara**).
  5. Fitur pembagian penugasan (**Bagikan Task** / **Bagikan Acara**) ke user/role, serta penghapusan penugasan (**Unassign**).

---

## 📋 Daftar 14 Test Case Baru (Modul 15)

| No. HU | No. SIT | Judul Test Case | Tipe | Prioritas | Status Dokumen |
| :---: | :---: | :--- | :---: | :---: | :---: |
| **15.1** | **9.1** | Membuka halaman Pengingat | Positive Case | High | Terdaftar (SS Blank) |
| **15.2** | **9.2** | Melihat daftar agenda pada tab Acara | Positive Case | Normal | Terdaftar (SS Blank) |
| **15.3** | **9.3** | Melihat detail task | Positive Case | High | Terdaftar (SS Blank) |
| **15.4** | **9.4** | Mengubah data task dengan data valid | Positive Case | High | Terdaftar (SS Blank) |
| **15.5** | **9.5** | Membagikan task kepada user | Positive Case | High | Terdaftar (SS Blank) |
| **15.6** | **9.6** | Menghapus penugasan task kepada user | Positive Case | High | Terdaftar (SS Blank) |
| **15.7** | **9.7** | Menambahkan komentar pada task | Positive Case | Normal | Terdaftar (SS Blank) |
| **15.8** | **9.8** | Menghapus komentar pada task | Positive Case | Normal | Terdaftar (SS Blank) |
| **15.9** | **9.9** | Melihat detail acara | Positive Case | High | Terdaftar (SS Blank) |
| **15.10**| **9.10**| Mengubah data acara dengan data valid | Positive Case | High | Terdaftar (SS Blank) |
| **15.11**| **9.11**| Membagikan acara kepada user | Positive Case | High | Terdaftar (SS Blank) |
| **15.12**| **9.12**| Menghapus penugasan acara kepada user | Positive Case | High | Terdaftar (SS Blank) |
| **15.13**| **9.13**| Menambahkan komentar pada acara | Positive Case | Normal | Terdaftar (SS Blank) |
| **15.14**| **9.14**| Menghapus komentar pada acara | Positive Case | Normal | Terdaftar (SS Blank) |

---

## 🗂️ Status Sinkronisasi Dokumen & Drive
1. **Dokumen Hasil Uji Mobile Word (`Hasil Uji\Dokumen_Hasil_Uji_Mobile.docx`)**:
   - Modul 15 telah diperbarui dari 5 tabel lama menjadi **14 tabel baru** (Table 164 s/d Table 177).
   - Seluruh baris screenshot **dikosongkan (blank)** sesuai instruksi QA.
2. **SIT Excel (`SIT\Test Case.xlsx` sheet `TC BTN SMART Mobile`)**:
   - Baris 185 s/d 198 telah diperbarui memuat 14 TC lengkap (Steps & Expected Results).
3. **SIT Word (`SIT\SIT BTN SMART Mobile (Updated).docx`)**:
   - Table 23 telah diperbarui memuat TC 9.1 s/d 9.14 (Pengingat) dan penomoran Daily Sales Agenda disesuaikan menjadi 9.15 s/d 9.22.
4. **Struktur Folder Bukti Uji**:
   - Folder sub-TC di `Hasil Uji\Screenshot\Mobile\15. Agenda - Pengingat\` telah dibuat 14 folder lengkap dengan file spesifikasi `.txt` (tanpa gambar screenshot).
5. **Tri-Drive Sync**:
   - Local D, Google Drive H (`H:\My Drive\Zegen\BTN Smart\Refactor`), dan Google Drive G (`G:\My Drive\Zegen\BTN Smart\Refactor`) memiliki MD5 hash yang identik 100%.
   - Git commit: `6f00506` ter-push ke `origin/main`.
