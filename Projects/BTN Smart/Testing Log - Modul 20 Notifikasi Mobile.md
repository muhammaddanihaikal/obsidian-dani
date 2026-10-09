# 📝 Testing Log - Modul 20 Notifikasi Mobile (Penambahan Fitur Baru)

Catatan pengujian mobile untuk penambahan fitur baru **Modul 20. Notifikasi** pada aplikasi **BTN SMART Mobile (v3)**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Mobile (Android)
* **Modul**: Modul 20. Notifikasi
* **Tanggal Update**: 9 Oktober 2026
* **Tester**: Dani & Team QA
* **Status**: **TC SELESAI DIEKSEKUSI (8 TC) - HASIL UJI & SCREENSHOT EMBEDDED** ✅

---

## 🔍 Ringkasan Fitur Notifikasi Mobile
Fitur Notifikasi pada aplikasi BTN SMART Mobile menyediakan pusat riwayat pemberitahuan kerja sales/karyawan:
1. **Entry Point Beranda**: Icon lonceng (Bell) pada header merah Beranda dengan counter badge notifikasi belum dibaca.
2. **Search Bar**: Pencarian riwayat notifikasi dengan kata kunci valid maupun validasi data tidak ditemukan.
3. **Tab Status Keterbacaan & Arsip**:
   - Tab **Semua**: Menampilkan seluruh riwayat notifikasi yang dikelompokkan berdasarkan waktu (*Hari Ini*, *Kemarin*, *Minggu Lalu*, dll).
   - Tab **Belum Dibaca**: Memfilter riwayat notifikasi yang berstatus unread (ditandai dengan indikator titik biru).
   - Tab **Diarsipkan**: Menampilkan notifikasi yang disimpan dalam arsip.
4. **Halaman Detail Notifikasi**: Menampilkan informasi lengkap tanggal, waktu, judul, tag kategori (*info*), dan isi rincian pesan.
5. **Fitur Arsipkan & Buka Arsip (Archive & Unarchive)**:
   - Aksi pengarsipan dari icon kotak arsip pada halaman detail.
   - Aksi pembatalan arsip (unarchive) untuk mengembalikan notifikasi ke daftar utama.

---

## 📋 Daftar 8 Test Case Baru (Modul 20)

| No | Modul | Judul Test Case | Tipe | Prioritas | Steps (Scenario) | Expected Result | Status Bukti Uji |
| :---: | :---: | :--- | :---: | :---: | :--- | :--- | :---: |
| **20.1** | Notifikasi | Membuka halaman Notifikasi | Positive Case | High | Buka aplikasi BTN Smart - Masuk ke Beranda - Klik icon Lonceng (Notifikasi) | Berhasil menampilkan halaman Notifikasi. | Embedded (2 SS) |
| **20.2** | Notifikasi | Mencari notifikasi dengan kata kunci valid | Positive Case | Normal | Masukkan kata kunci valid pada Search Bar | Berhasil menampilkan data notifikasi yang dicari. | Embedded (1 SS) |
| **20.3** | Notifikasi | Mencari notifikasi dengan kata kunci tidak valid | Negative Case | Normal | Masukkan kata kunci tidak valid pada Search Bar | Berhasil menampilkan informasi data tidak ditemukan. | Standby (Empty) |
| **20.4** | Notifikasi | Melihat data notifikasi Belum Dibaca | Positive Case | Normal | Pada halaman Notifikasi, klik tab Belum Dibaca | Berhasil menampilkan data notifikasi belum dibaca. | Embedded (1 SS) |
| **20.5** | Notifikasi | Melihat data notifikasi Diarsipkan | Positive Case | Normal | Pada halaman Notifikasi, klik tab Diarsipkan | Berhasil menampilkan data notifikasi diarsipkan. | Embedded (1 SS) |
| **20.6** | Notifikasi | Melihat detail notifikasi | Positive Case | High | Pada halaman Notifikasi, klik salah satu notifikasi | Berhasil menampilkan detail notifikasi. | Embedded (1 SS) |
| **20.7** | Notifikasi | Mengarsipkan notifikasi | Positive Case | High | Pada halaman Detail Notifikasi, klik icon Arsipkan | Berhasil mengarsipkan notifikasi. | Embedded (1 SS) |
| **20.8** | Notifikasi | Membatalkan arsip notifikasi | Positive Case | High | Pada detail notifikasi di tab Diarsipkan, klik icon Buka Arsip | Berhasil membatalkan arsip notifikasi. | Standby (Empty) |

---

## 🗂️ Status Sinkronisasi Dokumen & Tri-Drive

1. **Excel Master (`SIT\Test Case.xlsx`)**:
   - Sheet `TC BTN SMART Mobile` ditambahkan:
     - TC 19.1 s/d 19.3 (Kunjungan) disinkronkan agar selaras dengan dokumen SIT Word.
     - TC 20.1 s/d 20.8 (Notifikasi) ditambahkan lengkap.
   - Total baris: 232 Test Case resmi.
2. **SIT Word (`SIT\SIT BTN SMART Mobile.docx`)**:
   - Table 1 (Info Table) diperbarui: `Jumlah Script : 251` dan daftar modul memuat `Modul Notifikasi`.
   - Menambahkan section `20. Modul Notifikasi` dan Table 22 (8 TC).
3. **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Mobile.docx`)**:
   - Menambahkan section `20. Modul Notifikasi`.
   - Menambahkan Table 203 (TC 20.1 dengan header row UAT) hingga Table 210 (TC 20.8).
   - Gambar screenshot bukti uji dari `TC Baru\notif mobile` telah berhasil di-embed ke masing-masing tabel TC.
4. **Struktur Folder Screenshot**:
   - Folder `Hasil Uji\Screenshot\Mobile\20. Notifikasi\` telah dibuat lengkap dengan 8 subfolder TC dan file panduan `.txt`.
5. **Tri-Drive Verification**:
   - Local D, Google Drive H (`H:\My Drive\Zegen\BTN Smart\Refactor`), dan Google Drive G (`G:\My Drive\Zegen\BTN Smart\Refactor`) tersinkron identik 100% byte-for-byte (MD5 hash verified).
6. **Git Version Control**:
   - Commit `27ea513` ter-push ke `origin/main`.
