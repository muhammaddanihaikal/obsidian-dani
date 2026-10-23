---
tags:
  - SIT
  - BTN
  - Web
  - QA
  - TestScript
date: 2026-10-22
project: BTN Smart
platform: Web
source_file: SIT BTN SMART Web.docx
total_script: 864
converter: markitdown
---

|  |  |  |
| --- | --- | --- |
| ![](data:image/png;base64...) | **System Integration Testing (SIT)** | **Page** 1 |

|  |  |  |
| --- | --- | --- |
| **Application : BTN SMART V3** | Jumlah Script : 864 | **Version : 1.0** |
| Modul : Modul Login Modul Profile Modul Notifikasi Modul Overview - Overview Fund Modul Overview - Overview Lend Modul Overview - Pengaturan Overview Modul User Authority - User Modul User Authority - Group Role Modul User Authority - Tipe Karyawan Modul User Authority - Hak Akses Role Modul User Authority - Keamanan Akun Modul Profile Nasabah & Sales - Sales Modul Profile Nasabah & Sales - Nasabah Perorangan Modul Bisnis dan Produk - Unit Bisnis Modul Bisnis dan Produk - Produk Modul Bisnis dan Produk - Program Produk Modul Kantor - Tipe Kantor Modul Kantor - Data Kantor Modul Menu Target Modul Upload Bulk - Upload Target Bulk Modul Upload Bulk - Bulk Import User Modul Upload Bulk - Bulk Import Prospek - Prospek Personal Modul Upload Bulk - Bulk Import Prospek - Prospek Lembaga Modul Lead Generation - Prospek Individu Modul Lead Generation - Prospek Lembaga Modul Lead Qualification - Aktifitas Modul Lead Qualification - Aktifitas Referal Modul List Prospek ETB Modul Menu Absent - Dashboard Absent Modul Menu Absent - Daily Absent Modul Menu Absent - Rekap Absent Modul Menu Absent - Approval Absent Modul Sales Tracking Activity - Dashboard Visit Modul Sales Tracking Activity - Client Visit List Modul Sales Tracking Activity - Rekap Visit Modul Sales Tracking Activity - Rekap Monthly Visit Modul Setting Absent - Attendance Spot Modul Setting Absent - Work Pattern Modul Setting Absent - Holiday Modul Sales Force - Sales code Modul Sales Force - Pipeline - Dashboard Validate Pipeline Modul Sales Force - Pipeline - Input Pipeline Modul Sales Force - Approval Target Growth Modul Sales Force - Approval Sales Code Modul Sales Force - CIF Kelolaan Modul Sales Force - Approval Cif Kelolaan Modul Sales Force - Produktivitas - Target Growth Modul Sales Force - Produktivitas - Target Produktivitas Modul Sales Force - Produktivitas - Bobot Produktivitas Modul Sales Force - Produktivitas - Realisasi Merchant Modul Sales Force - CIF Rebase Modul Sales Force - Report - Report Produktivitas Modul Sales Force - Dashboard Sales Force Modul Sales Force - Pipeline - Setting Role Validate Pipeline Modul Sales Force - Pipeline - Setting Validate Pipeline Modul Sales Force - Pipeline - Input komitmen Modul Kalender Modul Report Funding - Personal Funnel Modul Report Funding - Rekap Funnel Modul Report Funding - Pengaturan Funnel Modul Report Funding - Daily Sales Agenda Modul Report Lending - Personal Funnel Modul Report Lending - Rekap Funnel Modul Report Lending - Pengaturan Funnel Modul Report Lending - Daily Sales Agenda Modul Re-Assign dan Approval - Approval Non Banking Modul Re-Assign dan Approval - Re-Assign Prospek Modul Re-Assign dan Approval - Re-Assign Management Modul Export Center - Riwayat Export Modul Export Center - Persetujuan Export Modul Export Center - Aktivitas Export Modul Ticket Maintenance - Aktivitas Issue Modul Ticket Maintenance - Kategori Aktivitas Issue Modul Ticket Maintenance - Dashboard Aktivitas Issue Modul Ticket Maintenance - Report Aktivitas Issue Modul Dashboard - Aktivitas Consumer Funding Modul Dashboard - Aktivitas Consumer Lending Modul Dashboard - Pengaturan Aktivitas Consumer Modul Dashboard - Optimalisasi Database | **Estimasi Jangka Waktu Pengujian :** 24 September 2026 s/d 09 Oktober 2026 | Last Update : 09 Oktober 2026 |

1. Modul Login

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1.1 | Membuka halaman Login | Buka halaman Login - Pilih tab | Berhasil menampilkan form Login . | Berhasil menampilkan form Login . | P |  |
| 1.2 | Melakukan login dengan email dan password valid | Input email valid - Input password valid - Klik button Masuk | Berhasil menampilkan halaman Verifikasi OTP. | Berhasil menampilkan halaman Verifikasi OTP. | P |  |
| 1.3 | Melakukan login dengan email tidak terdaftar | Input email yang tidak terdaftar - Input password - Klik button Masuk | Berhasil menampilkan pesan email atau password tidak valid. | Berhasil menampilkan pesan email atau password tidak valid. | P |  |
| 1.4 | Melakukan login dengan password salah | Input email valid - Input password yang salah - Klik button Masuk | Berhasil menampilkan pesan email atau password tidak valid. | Berhasil menampilkan pesan email atau password tidak valid. | P |  |
| 1.5 | Melakukan login tanpa mengisi email | Kosongkan email - Input password - Klik button Masuk | Berhasil menampilkan validasi email wajib diisi. | Berhasil menampilkan validasi email wajib diisi. | P |  |
| 1.6 | Melakukan login tanpa mengisi password | Input email - Kosongkan password - Klik button Masuk | Berhasil menampilkan validasi password wajib diisi. | Berhasil menampilkan validasi password wajib diisi. | P |  |
| 1.7 | Melakukan login tanpa mengisi email dan password | Kosongkan email dan password - Klik button Masuk | Berhasil menampilkan validasi field wajib diisi. | Berhasil menampilkan validasi field wajib diisi. | P |  |
| 1.8 | Melakukan verifikasi Email OTP | Input kode Email OTP - Klik button Verifikasi | Berhasil login ke Dashboard. | Berhasil login ke Dashboard. | P |  |
| 1.9 | Melakukan verifikasi Email OTP dengan kode tidak valid | Input kode Email OTP yang tidak valid - Klik button Verifikasi | Berhasil menampilkan pesan kode OTP tidak valid. | Berhasil menampilkan pesan kode OTP tidak valid. | P |  |
| 1.10 | Melakukan verifikasi TOTP | Input kode TOTP - Klik button Verifikasi | Berhasil login ke Dashboard. | Berhasil login ke Dashboard. | P |  |
| 1.11 | Melakukan verifikasi TOTP dengan kode tidak valid | Input kode TOTP yang tidak valid - Klik button Verifikasi | Berhasil menampilkan pesan kode TOTP tidak valid. | Berhasil menampilkan pesan kode TOTP tidak valid. | P |  |
| 1.12 | Melakukan login menggunakan perangkat terpercaya | Input email dan password valid pada perangkat terpercaya - Klik button Masuk | Berhasil login tanpa verifikasi OTP. | Berhasil login tanpa verifikasi OTP. | P |  |
| 1.13 | Menggunakan kode pemulihan | Klik Gunakan kode pemulihan - Input Recovery Code - Klik button Verifikasi | Berhasil login ke Dashboard. | Berhasil login ke Dashboard. | P |  |
| 1.14 | Menggunakan kode pemulihan yang tidak valid | Klik Gunakan kode pemulihan - Input Recovery Code yang tidak valid - Klik button Verifikasi | Berhasil menampilkan pesan Recovery Code tidak valid. | Berhasil menampilkan pesan Recovery Code tidak valid. | P |  |
| 1.15 | Mengajukan Reset MFA | Klik button Ajukan Reset MFA - Input alasan reset - Klik button Ajukan Reset | Berhasil mengajukan permintaan Reset MFA. | Berhasil mengajukan permintaan Reset MFA. | P |  |
| 1.16 | Mengajukan Reset MFA tanpa mengisi alasan reset | Klik button Ajukan Reset MFA - Kosongkan alasan reset - Klik button Ajukan Reset | Berhasil menampilkan validasi alasan reset wajib diisi. | Berhasil menampilkan validasi alasan reset wajib diisi. | P |  |

2. Modul Profile

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 2.1 | Membuka halaman profile | Klik nama/ profile pada kanan atas halaman - Klik pengaturan | Menampilkan halaman profile | Berhasil Menampilkan halaman profile | P |  |
| 2.2 | Mengubah informasi pribadi | Klik button edit - Ubah data - Klik button simpan | Berhasil mengubah data informasi pribadi | Berhasil mengubah data informasi pribadi | P |  |
| 2.3 | Mengubah informasi pribadi dengan tidak menginput data mandatory (negative test) | Klik button edit - hapus data mandatory kemudian klik button simpan | Menampilkan alert mandatory/wajib diisi | Berhasil Menampilkan alert mandatory/wajib diisi | P |  |
| 2.4 | Mengubah foto profile | Klik button Edit - Pilih foto dari folder - Pilih foto yang ingin digunakan - Klik button Simpan | Berhasil mengubah foto profile. | Berhasil mengubah foto profile. | P |  |
| 2.5 | Mengubah profile dengan format yang tidak sesuai (Negative test) | Klik button edit - Klik button ubah foto profile kemudian pilih file menggunakan format selain(jpg/png/jpeg) - klik button simpan | Menampilkan alert format tidak sesuai | Berhasil Menampilkan alert format tidak sesuai | P |  |
| 2.6 | Mengubah kata sandi dengan data valid | Klik submenu Ganti kata sandi - Input kata sandi saat ini - Input kata sandi baru dan konfirmasi kata sandi - Klik button simpan | Berhasil mengubah kata sand | Berhasil mengubah kata sand | P |  |
| 2.7 | Menginput konfirmasi kata sandi berbeda dengan kata sandi baru (Negative test) | Input konfirmasi kata sandi yang berbeda dengan kata sandi baru | Menampilkan validasi kata sandi tidak cocok | Berhasil Menampilkan validasi kata sandi tidak cocok | P |  |
| 2.8 | Menginput kata sandi dengan huruf kecil saja | Input kata sandi dengan huruf kecil saja | Menampilkan validasi persyaratan kata sandi | Berhasil Menampilkan validasi persyaratan kata sandi | P |  |
| 2.9 | Menginput kata sandi dengan huruf kapital saja | Input kata sandi dengan huruf kapital saja | Menampilkan validasi persyaratan kata sandi | Berhasil Menampilkan validasi persyaratan kata sandi | P |  |
| 2.10 | Menginput kata sandi kurang dari 8 karakter | Input kata sandi kurang dari 8 karakter | Menampilkan validasi persyaratan kata sandi | Berhasil Menampilkan validasi persyaratan kata sandi | P |  |
| 2.11 | Menginput kata sandi tidak menggunakan angka | Input kata sandi tidak menggunakan angka | Menampilkan validasi persyaratan kata sandi | Berhasil Menampilkan validasi persyaratan kata sandi | P |  |
| 2.12 | Menginput kata sandi baru sama dengan kata sandi yang lama | Input kata sandi baru sama dengan kata sandi yang lama | Gagal update password | Berhasil Gagal update password | P |  |
| 2.13 | Membuka halaman keamanan | Klik submenu Keamanan | Menampilkan halaman Keamanan | Berhasil Menampilkan halaman Keamanan | P |  |
| 2.14 | Mengaktifkan MFA menggunakan metode TOTP scan barcode | Klik metode TOTP - Scan barcode menggunakan aplikasi google authenticator - Mendapatkan kode, input kode pada btn smart kolom kode verifikasi - Klik button continue | Berhasil mengaktifkan MFA menggunakan metode TOTP | Berhasil mengaktifkan MFA menggunakan metode TOTP | P |  |
| 2.15 | Mengaktifkan MFA menggunakan metode TOTP menggunakan kode manual | Klik metode TOTP - Salin kode manual, paste pada aplikasi google authenticator - Mendapatkan kode kemudian input kode pada btn smart kolom kode verifikasi - Klik button continue | Berhasil mengaktifkan MFA menggunakan metode TOTP | Berhasil mengaktifkan MFA menggunakan metode TOTP | P |  |
| 2.16 | Mengaktifkan MFA menggunakan metode TOTP dengan menginput kode OTP salah | Melaakukan setup, kemudian input kode OTP yang salah | Menampilkan validasi kode OTP tidak sesuai | Berhasil Menampilkan validasi kode OTP tidak sesuai | P |  |
| 2.17 | Mangaktifkan MFA menggunakan metode email OTP | Klik metode email OTP - Masukan kode Verifikasi yang sudah dikirim ke email user yang terdaftar pada BTN Smart verifikasi dan aktifkan | Berhasil mengaktifkan MFA menggunakan metode email OTP dan mendapatkan kode Cadangan | Berhasil mengaktifkan MFA menggunakan metode email OTP dan mendapatkan kode Cadangan | P |  |
| 2.18 | Mengaktifkan MFA menggunakan metode email OTP dengan mengirim ulang kode OTP | Klik metode email OTP - Klik button kirim ulang kode OTP input kode yang terkirim ulang verifikasi dan aktifkan | berhasil mengaktifkan MFA menggunakan kode yang dikirim ulang | berhasil mengaktifkan MFA menggunakan kode yang dikirim ulang | P |  |
| 2.19 | Mengaktifkan MFA menggunakan metode email OTP dengan menginput kode otp yang salah | Melakukan setup, kemudian input kode OTP yang salah | Menampilkan validasi kode OTP tidak sesuai | Berhasil Menampilkan validasi kode OTP tidak sesuai | P |  |
| 2.20 | Mengganti metode MFA | Klik button Ganti metode pilih metode email OTP/TOTP yang akan diubah, kemudian ikuti langkah seperti saat mengaktifkan MFA pertama kali | Berhasil mengubah metode MFA | Berhasil mengubah metode MFA | P |  |
| 2.21 | Mengganti metode MFA dengan input password yang salah | Klik button ganti metode, input password yang tidak sesuai | Berhasil menampilkan validasi password tidak valid | Berhasil menampilkan validasi password tidak valid | P |  |
| 2.22 | Melakukan recovery code | Klik button recovery code, input password yang digunakan pada saat login btn smart | Menampilkan data recovery code | Berhasil Menampilkan data recovery code | P |  |
| 2.23 | Melakukan recovery code dengan input password yang salah | Klik button ganti metode, input paswword yang salah | Menampilkan validasi password tidak valid | Berhasil Menampilkan validasi password tidak valid | P |  |
| 2.24 | Generate ulang recovery code | Klik button recovery code – input password yang digunakan saat login BTN Smart, klik button generate code | Berhasil mendapatkan kode recovery baru | Berhasil mendapatkan kode recovery baru | P |  |
| 2.25 | Menyalin semua recovery code | Klik button recovery code – input password yang digunakan saat login BTN Smart – klik button salin semua | Berhasil menyalin kode di halaman lain seperti note/word | Berhasil menyalin kode di halaman lain seperti note/word | P |  |
| 2.26 | mengunduh data Recovery code | Klik button recovery code – input password yang digunakan saat login BTN Smart, klik button download | Berhasil mengunduh data recovery code | Berhasil mengunduh data recovery code | P |  |
| 2.27 | Melihat riwayat login | Klik submenu keamanan | Menampilkan data riwayat login | Berhasil Menampilkan data riwayat login | P |  |
| 2.28 | Data login berhasil | Melakukan login menggunakan username dan password yang sesuai | Menampilkan data di riwayat login sebagai login berhasil | Berhasil Menampilkan data di riwayat login sebagai login berhasil | P |  |
| 2.29 | Data gagal login | Melakukan login menggunakan username dan password yang tidak sesuai | Menampilkan data di riwayat login sebagai login gagal | Berhasil Menampilkan data di riwayat login sebagai login gagal | P |  |
| 2.30 | Lihat semua riwayat aktifitas | Klik button lihat semua riawayat aktifitaas | Menampilkan seluruh riwayat login | Berhasil Menampilkan seluruh riwayat login | P |  |
| 2.31 | Melakukan filter data | Pilih tipe atau status | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 2.32 | Melakukan search data | Input data pada kolom pencarian | Menampilkan data sesuai yang di cari | Berhasil Menampilkan data sesuai yang di cari | P |  |
| 2.33 | Pengecekan Riwayat login sebelum mengaktifkan MFA | Melakukan login menggunakan user yang belum mengaktifkan MFA kemudian cek Riwayat login | Menampilkan data riwayat login non aktif MFA | Berhasil Menampilkan data riwayat login non aktif MFA | P |  |
| 2.34 | Pengecekan Riwayat login sesudah mengaktifkan MFA | Melakukan login menggunakan user yang sudah mengaktifkan MFA kemudian cek Riwayat login | Menampilkan data riwayat login MFA | Berhasil Menampilkan data riwayat login MFA | P |  |
| 2.35 | pengecekan data logout | Melakukan logout lakun | Menampilkan data logout pada riwayat login | Berhasil Menampilkan data logout pada riwayat login | P |  |
| 2.36 | pengecekan data logout karena sesi habis | Cek data login karena sesi habis | Menampilkan data Riwayat login dengan label “sesi tidak aktif selama 15 menit” | Berhasil Menampilkan data Riwayat login dengan label “sesi tidak aktif selama 15 menit” | P |  |
| 2.37 | Melihat perangkat terhubung | Klik submenu keamanan | Menampilkan list data perangkat terhubung | Berhasil Menampilkan list data perangkat terhubung | P |  |
| 2.38 | Melihat detail perangkat terhubung | Klik icon opsi perangkat, klik lihat detail | Menampilkan detail peraangkat terhubung | Berhasil Menampilkan detail peraangkat terhubung | P |  |
| 2.39 | Percayai perangkat terhubung | Klik icon opsi perangkat, klik percayai perangkat | Perangkat yang di percayai tidak perlu melakukan verifikasi MFA jika login | Berhasil Perangkat yang di percayai tidak perlu melakukan verifikasi MFA jika login | P |  |
| 2.40 | Ganti nama perangkat | Klik icon opsi perangkat, klik Ganti nama – ubah nama perangkat klik “ok” | Berhasil mengubah nama label perangkat pada perangkat terhubung dan Riwayat login | Berhasil mengubah nama label perangkat pada perangkat terhubung dan Riwayat login | P |  |
| 2.41 | Putuskan perangkat terhubung | Klik icon opsi perangkat pada perangkat terhubung yang status nya aktif - Klik button Putuskan | Berhasil memutuskan perangkat terhubung dan auto logout. | Berhasil memutuskan perangkat terhubung dan auto logout. | P |  |
| 2.42 | Menghapus perangkat terhubung | Klik icon opsi pengkat, klik hapus | Berhasil menghapus perangkat yang terhubung | Berhasil menghapus perangkat yang terhubung | P |  |
| 2.43 | Putuskan semua perangkat terhubung | Klik putuskan semua perangkat yang terhubung | Semua perangkat terhubung akan auto logout kecuali “perangkat ini” | Berhasil Semua perangkat terhubung akan auto logout kecuali “perangkat ini” | P |  |
| 2.44 | Pengecekan masa berlaku percayai perangkat | Percayai perangkat | Perangkat yang dipercayai hanya berlaku 30 hari | Berhasil Perangkat yang dipercayai hanya berlaku 30 hari | P |  |
| 2.45 | Pengecekan perangkat terhubung sebelum mengaktifkan MFA | Melakukan login menggunakan user yang belum mengaktifkan MFA kemudian cek Perangkat terhubung | Menampilkan data perangkat terhubung non aktif MFA | Berhasil Menampilkan data perangkat terhubung non aktif MFA | P |  |
| 2.46 | Pengecekan perangkat terhubung sesudah mengaktifkan MFA | Melakukan login menggunakan user yang sudah mengaktifkan MFA – kemudian cek Perangkat terhubung | menampilkan data perangkat terhubung user MFA | Berhasil menampilkan data perangkat terhubung user MFA | P |  |
| 2.47 | Pengecekan perangkat terhubung berbagai browser (chrome, edge, mozila, dll) | Melakukan login di berbagai browser, kemudian cek Perangkat terhubung | Menampilkan data perangkat terhubung berbagai browser | Berhasil Menampilkan data perangkat terhubung berbagai browser | P |  |

3. Modul Notifikasi

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 3.1 | Membuka notifikasi pada header | Klik icon Lonceng (Notifikasi) pada header bar | Berhasil menampilkan daftar notifikasi terbaru. | Berhasil menampilkan daftar notifikasi terbaru. | P |  |
| 3.2 | Mencari notifikasi dengan kata kunci valid | Masukkan kata kunci valid pada kolom Cari notifikasi | Berhasil menampilkan data notifikasi yang dicari. | Berhasil menampilkan data notifikasi yang dicari. | P |  |
| 3.3 | Mencari notifikasi dengan kata kunci tidak valid | Masukkan kata kunci tidak valid pada kolom Cari notifikasi | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 3.4 | Melihat data notifikasi Belum Dibaca | Pada daftar notifikasi, klik tab Belum Dibaca | Berhasil menampilkan data notifikasi belum dibaca. | Berhasil menampilkan data notifikasi belum dibaca. | P |  |
| 3.5 | Menandai semua notifikasi telah dibaca | Pada notifikasi, klik tombol Tandai semua dibaca | Berhasil menandai seluruh notifikasi telah dibaca. | Berhasil menandai seluruh notifikasi telah dibaca. | P |  |
| 3.6 | Melihat semua notifikasi | Pada daftar notifikasi, klik tombol Lihat semua | Berhasil menampilkan seluruh daftar notifikasi. | Berhasil menampilkan seluruh daftar notifikasi. | P |  |
| 3.7 | Melihat data notifikasi Diarsipkan | Pada halaman Pengaturan Profile - Notifikasi, klik tab Diarsipkan | Berhasil menampilkan data notifikasi diarsipkan. | Berhasil menampilkan data notifikasi diarsipkan. | P |  |
| 3.8 | Melihat detail notifikasi | Pada daftar notifikasi, klik salah satu notifikasi yang ingin dilihat | Berhasil menampilkan halaman Detail Notifikasi. | Berhasil menampilkan halaman Detail Notifikasi. | P |  |
| 3.9 | Mengarsipkan notifikasi | Pada halaman Detail Notifikasi, klik tombol Arsipkan | Berhasil mengarsipkan notifikasi. | Berhasil mengarsipkan notifikasi. | P |  |
| 3.10 | Membatalkan arsip notifikasi | Pada halaman Detail Notifikasi yang diarsipkan, klik tombol Kembalikan dari arsip | Berhasil membatalkan arsip notifikasi. | Berhasil membatalkan arsip notifikasi. | P |  |

4. Modul Overview - Overview Fund

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 4.1 | Membuka halaman Overview Funding | Buka menu Overview - Klik sub menu Overview Funding | Berhasil menampilkan halaman Overview Funding. | Berhasil menampilkan halaman Overview Funding. | P |  |
| 4.2 | Melakukan filter data Overview Funding | Pilih opsi filter yang diinginkan - Klik tombol Cari/Filter | Berhasil menampilkan data Overview Funding yang sesuai dengan filter. | Berhasil menampilkan data Overview Funding yang sesuai dengan filter. | P |  |
| 4.3 | Melakukan filter data Overview Funding tanpa mengisi field mandatory | Kosongkan field mandatory pada filter - Klik tombol Cari/Filter | Tampil pesan peringatan bahwa field mandatory wajib diisi. | Berhasil Tampil pesan peringatan bahwa field mandatory wajib diisi. | P |  |
| 4.4 | Mengubah ukuran (perbesar/perkecil) tampilan widget pada Overview Funding | Klik icon perbesar/perkecil pada salah satu widget | Berhasil memperbesar atau memperkecil ukuran tampilan widget. | Berhasil memperbesar atau memperkecil ukuran tampilan widget. | P |  |
| 4.5 | Me-refresh data pada halaman Overview Funding | Klik tombol Refresh pada halaman Overview Funding | Berhasil memuat ulang (refresh) data terbaru pada seluruh widget. | Berhasil memuat ulang (refresh) data terbaru pada seluruh widget. | P |  |

5. Modul Overview - Overview Lend

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 5.1 | Membuka halaman Overview Lending | Buka menu Overview - Klik sub menu Overview Lending | Berhasil menampilkan halaman Overview Lending. | Berhasil menampilkan halaman Overview Lending. | P |  |
| 5.2 | Melakukan filter data Overview Lending | Pilih opsi filter yang diinginkan - Klik tombol Cari/Filter | Berhasil menampilkan data Overview Lending yang sesuai dengan filter. | Berhasil menampilkan data Overview Lending yang sesuai dengan filter. | P |  |
| 5.3 | Melakukan filter data Overview Lending tanpa mengisi field mandatory | Kosongkan field mandatory pada filter - Klik tombol Cari/Filter | Tampil pesan peringatan bahwa field mandatory wajib diisi. | Berhasil Tampil pesan peringatan bahwa field mandatory wajib diisi. | P |  |
| 5.4 | Mengubah ukuran (perbesar/perkecil) tampilan widget pada Overview Lending | Klik icon perbesar/perkecil pada salah satu widget | Berhasil memperbesar atau memperkecil ukuran tampilan widget. | Berhasil memperbesar atau memperkecil ukuran tampilan widget. | P |  |
| 5.5 | Me-refresh data pada halaman Overview Lending | Klik tombol Refresh pada halaman Overview Lending | Berhasil memuat ulang (refresh) data terbaru pada seluruh widget. | Berhasil memuat ulang (refresh) data terbaru pada seluruh widget. | P |  |

6. Modul Overview - Pengaturan Overview

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 6.1 | Membuka halaman Pengaturan Overview | Klik menu Overview - Klik sub menu Pengaturan Overview | Berhasil menampilkan halaman Pengaturan Overview. | Berhasil menampilkan halaman Pengaturan Overview. | P |  |
| 6.2 | Mengubah Role pada Pengaturan Overview | Mengisi field Role dengan satu atau lebih role yang tersedia - Klik button Simpan | Berhasil menyimpan perubahan Role pada Pengaturan Overview. | Berhasil menyimpan perubahan Role pada Pengaturan Overview. | P |  |
| 6.3 | Mengubah Role pada Pengaturan Overview tanpa mengisi field mandatory | Mengosongkan field Role (menghapus semua role yang ada) - Klik button Simpan | Berhasil menampilkan pesan validasi bahwa field Role wajib diisi. | Berhasil menampilkan pesan validasi bahwa field Role wajib diisi. | P |  |

7. Modul User Authority - User

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 7.1 | Membuka halaman User | Klik menu User Authority - Klik sub menu User | Berhasil menampilkan halaman User. | Berhasil menampilkan halaman User. | P |  |
| 7.2 | Mencari data User dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 7.3 | Mencari data User dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 7.4 | Menambahkan data User | Klik button Tambah User - Input seluruh field mandatory - Klik button Simpan | Berhasil menyimpan data user. | Berhasil menyimpan data user. | P |  |
| 7.5 | Menambahkan data User tanpa mengisi field mandatory | Klik button Tambah User - Kosongkan field mandatory - Klik button Simpan | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 7.6 | Mengubah data User | Klik button Aksi (...) - Klik menu Ubah Data - Ubah data user - Klik button Update | Berhasil menyimpan perubahan data user. | Berhasil menyimpan perubahan data user. | P |  |
| 7.7 | Mengubah data User tanpa mengisi field mandatory | Klik button Aksi (...) - Klik buton Ubah Data - Kosongkan field mandatory - Klik button Update | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 7.8 | Menghapus data User | Pilih salah satu data user - Klik button Hapus 1 data - Klik button Yes | Berhasil menghapus data user. | Berhasil menghapus data user. | P |  |
| 7.9 | Mengekspor data User | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

8. Modul User Authority - Group Role

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 8.1 | Membuka halaman Group Role | Klik menu User Authority - Klik sub menu Group Role | Berhasil menampilkan halaman Group Role. | Berhasil menampilkan halaman Group Role. | P |  |
| 8.2 | Mencari data Group Role dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 8.3 | Mencari data Group Role dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 8.4 | Menambahkan data Group Role | Klik button Tambah Role - Input seluruh field mandatory - Pilih hak akses menu - Klik button Submit | Berhasil menyimpan data group role. | Berhasil menyimpan data group role. | P |  |
| 8.5 | Menambahkan data Group Role tanpa mengisi field mandatory | Klik button Tambah Role - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 8.6 | Mengubah data Group Role | Klik button Aksi (...) - Klik menu Ubah Data - Ubah data group role - Klik button Submit | Berhasil menyimpan perubahan data group role. | Berhasil menyimpan perubahan data group role. | P |  |
| 8.7 | Mengubah data Group Role tanpa mengisi field mandatory | Klik button Aksi (...) - Klik menu Ubah Data - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 8.8 | Menghapus data Group Role | Pilih salah satu data group role - Klik button Hapus 1 data - Klik button Yes | Berhasil menghapus data group role. | Berhasil menghapus data group role. | P |  |
| 8.9 | Mengekspor data Group Role | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

9. Modul User Authority - Tipe Karyawan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 9.1 | Membuka halaman Tipe Karyawan | Klik menu User Authority - Klik sub menu Tipe Karyawan | Berhasil menampilkan halaman Tipe Karyawan. | Berhasil menampilkan halaman Tipe Karyawan. | P |  |
| 9.2 | Mencari data Tipe Karyawan dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 9.3 | Mencari data Tipe Karyawan dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 9.4 | Menambahkan data Tipe Karyawan | Klik button Tambah Tipe Karyawan - Input field Name - Pilih minimal satu checkbox Selling Role - Klik button Simpan | Berhasil menyimpan data tipe karyawan. | Berhasil menyimpan data tipe karyawan. | P |  |
| 9.5 | Menambahkan data Tipe Karyawan tanpa mengisi field mandatory | Klik button Tambah Tipe Karyawan - Kosongkan field Name dan Selling Role - Klik button Simpan | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 9.6 | Mengubah data Tipe Karyawan | Klik button Aksi (...) - Klik menu Ubah Data - Ubah data tipe karyawan - Klik button Submit | Berhasil menyimpan perubahan data tipe karyawan. | Berhasil menyimpan perubahan data tipe karyawan. | P |  |
| 9.7 | Mengubah data Tipe Karyawan tanpa mengisi field mandatory | Klik button Aksi (...) - Klik menu Ubah Data - Kosongkan field Name - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 9.8 | Menghapus data Tipe Karyawan | Pilih salah satu data tipe karyawan - Klik button Hapus 1 data - Klik button Yes | Berhasil menghapus data tipe karyawan. | Berhasil menghapus data tipe karyawan. | P |  |

10. Modul User Authority - Hak Akses Role

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 10.1 | Membuka halaman Hak Akses Role | Klik menu User Authority - Klik sub menu Hak Akses Role | Berhasil menampilkan halaman Hak Akses Role beserta daftar data role. | Berhasil menampilkan halaman Hak Akses Role beserta daftar data role. | P |  |
| 10.2 | Mencari data Role dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 10.3 | Mencari data Role dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 10.4 | Mengubah Hak Akses Role | Klik button Aksi (...) - Klik menu Ubah Akses - Pilih atau hapus checklist hak akses - Klik button Simpan | Berhasil menyimpan perubahan hak akses role. | Berhasil menyimpan perubahan hak akses role. | P |  |
| 10.5 | Mengubah Hak Akses Role tanpa memilih hak akses | Klik button Aksi (...) - Klik menu Ubah Akses - Hapus seluruh checklist hak akses - Klik button Simpan | Berhasil menampilkan validasi hak akses wajib dipilih. | Berhasil menampilkan validasi hak akses wajib dipilih. | P |  |
| 10.6 | Mencari data Hak Akses dengan keyword valid | Klik button Aksi (...) - Klik menu Ubah Akses - Input keyword pada field Search | Berhasil menampilkan hak akses sesuai keyword. | Berhasil menampilkan hak akses sesuai keyword. | P |  |
| 10.7 | Mencari data Hak Akses dengan keyword tidak valid | Klik button Aksi (...) - Klik menu Ubah Akses - Input keyword yang tidak terdaftar pada field Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |

11. Modul User Authority - Keamanan Akun

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 11.1 | Membuka halaman Keamanan Akun | Klik menu User Authority - Klik sub menu Keamanan Akun | Berhasil menampilkan halaman Keamanan Akun beserta informasi ringkasan dan daftar akun. | Berhasil menampilkan halaman Keamanan Akun beserta informasi ringkasan dan daftar akun. | P |  |
| 11.2 | Melihat informasi Total Pengguna | Lihat card Total Pengguna | Berhasil menampilkan jumlah total pengguna. | Berhasil menampilkan jumlah total pengguna. | P |  |
| 11.3 | Melihat informasi MFA Aktif | Lihat card MFA Aktif | Berhasil menampilkan jumlah dan persentase MFA aktif. | Berhasil menampilkan jumlah dan persentase MFA aktif. | P |  |
| 11.4 | Melihat informasi Permintaan Reset | Lihat card Permintaan Reset | Berhasil menampilkan jumlah permintaan reset MFA. | Berhasil menampilkan jumlah permintaan reset MFA. | P |  |
| 11.5 | Melihat informasi User Aktif | Lihat card User Aktif | Berhasil menampilkan jumlah user aktif. | Berhasil menampilkan jumlah user aktif. | P |  |
| 11.6 | Melihat informasi Login Gagal | Lihat card Login Gagal (24 jam) | Berhasil menampilkan jumlah login gagal dalam 24 jam. | Berhasil menampilkan jumlah login gagal dalam 24 jam. | P |  |
| 11.7 | Melihat informasi Perangkat Terpercaya | Lihat card Perangkat Terpercaya | Berhasil menampilkan persentase perangkat terpercaya. | Berhasil menampilkan persentase perangkat terpercaya. | P |  |
| 11.8 | Mencari akun dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 11.9 | Mencari akun dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 11.10 | Melihat detail akun | Klik button Aksi (...) - Klik menu Lihat Detail | Berhasil menampilkan detail akun. | Berhasil menampilkan detail akun. | P |  |
| 11.11 | Mereset MFA pengguna | Klik button Aksi (...) - Klik menu Reset MFA - Input field Alasan - Klik button Reset | Berhasil mereset MFA pengguna. | Berhasil mereset MFA pengguna. | P |  |
| 11.12 | Mereset MFA tanpa mengisi alasan | Klik button Aksi (...) - Klik menu Reset MFA - Kosongkan field Alasan - Klik button Reset | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 11.13 | Mengaktifkan MFA Email | Klik button Aksi (...) - Klik menu Aktifkan MFA (EMAIL) - Input field Alasan - Klik button Aktifkan | Berhasil mengaktifkan MFA Email. | Berhasil mengaktifkan MFA Email. | P |  |
| 11.14 | Mengaktifkan MFA Email tanpa mengisi alasan | Klik button Aksi (...) - Klik menu Aktifkan MFA (EMAIL) - Kosongkan field Alasan - Klik button Aktifkan | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 11.15 | Mengaktifkan MFA TOTP | Klik button Aksi (...) - Klik menu Aktifkan MFA (TOTP) - Input field Alasan - Klik button Aktifkan | Berhasil mengaktifkan MFA TOTP. | Berhasil mengaktifkan MFA TOTP. | P |  |
| 11.16 | Mengaktifkan MFA TOTP tanpa mengisi alasan | Klik button Aksi (...) - Klik menu Aktifkan MFA (TOTP) - Kosongkan field Alasan - Klik button Aktifkan | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 11.17 | Mengekspor data akun | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 11.18 | Membuka halaman Permintaan Reset MFA | Klik menu User Authority - Klik sub menu Keamanan Akun - Klik tab Permintaan Reset MFA | Berhasil menampilkan daftar Permintaan Reset MFA. | Berhasil menampilkan daftar Permintaan Reset MFA. | P |  |
| 11.19 | Mencari permintaan reset MFA dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 11.20 | Mencari permintaan reset MFA dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 11.21 | Melakukan filter data permintaan reset MFA | Pilih filter Status dan/atau Rentang Tanggal Permintaan - Klik button Filter | Berhasil Melakukan filter data permintaan reset MFA. | Berhasil Melakukan filter data permintaan reset MFA. | P |  |
| 11.22 | Mereset filter data permintaan reset MFA | Klik button Reset Filter | Berhasil Mereset filter data permintaan reset MFA. | Berhasil Mereset filter data permintaan reset MFA. | P |  |
| 11.23 | Melihat detail permintaan reset MFA | Klik button Aksi (...) - Klik menu Lihat Detail | Berhasil menampilkan detail permintaan reset MFA. | Berhasil menampilkan detail permintaan reset MFA. | P |  |
| 11.24 | Menyetujui permintaan reset MFA | Klik button Aksi (...) - Klik menu Setujui - Input field Remark - Klik button Setujui Permintaan | Berhasil menyetujui permintaan reset MFA. | Berhasil menyetujui permintaan reset MFA. | P |  |
| 11.25 | Menyetujui permintaan reset MFA tanpa mengisi remark | Klik button Aksi (...) - Klik menu Setujui - Kosongkan field Remark - Klik button Setujui Permintaan | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 11.26 | Menolak permintaan reset MFA | Klik button Aksi (...) - Klik menu Tolak - Input field Remark - Klik button Tolak Permintaan | Berhasil menolak permintaan reset MFA. | Berhasil menolak permintaan reset MFA. | P |  |
| 11.27 | Menolak permintaan reset MFA tanpa mengisi remark | Klik button Aksi (...) - Klik menu Tolak - Kosongkan field Remark - Klik button Tolak Permintaan | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 11.28 | Membuka halaman Perangkat & Sesi | Klik menu User Authority - Klik sub menu Keamanan Akun - Klik tab Perangkat & Sesi | Berhasil menampilkan daftar Perangkat & Sesi. | Berhasil menampilkan daftar Perangkat & Sesi. | P |  |
| 11.29 | Mencari perangkat dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 11.30 | Mencari perangkat dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 11.31 | Melakukan filter data perangkat & sesi | Pilih filter Status Sesi, Perangkat Terpercaya, dan/atau Rentang Tanggal Aktivitas Terakhir - Klik button Filter | Berhasil Melakukan filter data perangkat & sesi. | Berhasil Melakukan filter data perangkat & sesi. | P |  |
| 11.32 | Mereset filter data perangkat & sesi | Klik button Reset Filter | Berhasil Mereset filter data perangkat & sesi. | Berhasil Mereset filter data perangkat & sesi. | P |  |
| 11.33 | Melihat detail perangkat | Klik button Aksi (...) - Klik menu Lihat Detail | Berhasil menampilkan detail perangkat. | Berhasil menampilkan detail perangkat. | P |  |
| 11.34 | Mengekspor data perangkat | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 11.35 | Membuka halaman Log Aktivitas | Klik menu User Authority - Klik sub menu Keamanan Akun - Klik tab Log Aktivitas | Berhasil menampilkan halaman Log Aktivitas. | Berhasil menampilkan halaman Log Aktivitas. | P |  |
| 11.36 | Mencari log aktivitas dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 11.37 | Mencari log aktivitas dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 11.38 | Melakukan filter log aktivitas | Pilih filter - Klik button Filter | Berhasil menampilkan data sesuai filter. | Berhasil menampilkan data sesuai filter. | P |  |
| 11.39 | Mereset filter log aktivitas | Klik button Reset Filter | Berhasil mengembalikan filter ke nilai default. | Berhasil mengembalikan filter ke nilai default. | P |  |
| 11.40 | Melihat detail log aktivitas | Klik button Aksi (...) - Klik menu Lihat Detail | Berhasil menampilkan detail log aktivitas. | Berhasil menampilkan detail log aktivitas. | P |  |

12. Modul Profile Nasabah & Sales - Sales

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 12.1 | Membuka halaman Profile Sales | Klik menu Profile Nasabah & Sales - Klik sub menu Sales | Berhasil menampilkan halaman Profile Sales. | Berhasil menampilkan halaman Profile Sales. | P |  |
| 12.2 | Mencari data Sales dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 12.3 | Mencari data Sales dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 12.4 | Melakukan filter data Sales dengan mengisi field mandatory | Pilih Kategori pada dropdown - Pilih Role pada dropdown - Klik button Filter | Berhasil menampilkan data Sales yang difilter sesuai dengan Kategori dan Role yang dipilih. | Berhasil menampilkan data Sales yang difilter sesuai dengan Kategori dan Role yang dipilih. | P |  |
| 12.5 | Melakukan filter data Sales tanpa mengisi field mandatory | Kosongkan field Kategori and Role - Klik button Filter | Berhasil menampilkan pesan error validasi 'Kategori dibutuhkan!' dan 'Role dibutuhkan!'. | Berhasil menampilkan pesan error validasi 'Kategori dibutuhkan!' dan 'Role dibutuhkan!'. | P |  |
| 12.6 | Mengekspor (Export) data Sales | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 12.7 | Melihat detail Profile Sales | Klik icon '...' pada field Action salah satu data Sales - Klik Detail | Berhasil membuka halaman Detail Sales yang memuat informasi Performa, Staging Prospek, Product Ownership, dan Aktivitas Terakhir. | Berhasil membuka halaman Detail Sales yang memuat informasi Performa, Staging Prospek, Product Ownership, dan Aktivitas Terakhir. | P |  |
| 12.8 | Mengubah periode filter (Bulan/Tahun) pada grafik Staging Prospek | Pada bagian Staging Prospek, ubah pilihan dropdown periode (misal: 'Mei 2026') | Berhasil mengubah dropdown periode dan data pada container Staging Prospek berhasil difilter menyesuaikan periode yang dipilih. | Berhasil mengubah dropdown periode dan data pada container Staging Prospek berhasil difilter menyesuaikan periode yang dipilih. | P |  |
| 12.9 | Melihat histori Aktivitas Terakhir secara keseluruhan | Pada halaman Detail Sales, klik link 'Lihat semua ->' di bagian Aktivitas Terakhir | Berhasil pengguna diarahkan ke halaman 'Lead Qualification - Aktivitas'. | Berhasil pengguna diarahkan ke halaman 'Lead Qualification - Aktivitas'. | P |  |

13. Modul Profile Nasabah & Sales - Nasabah Perorangan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 13.1 | Membuka halaman Nasabah Perorangan | Klik menu Profile Nasabah & Sales - Klik sub menu Nasabah Perorangan | Berhasil menampilkan halaman Nasabah Perorangan. | Berhasil menampilkan halaman Nasabah Perorangan. | P |  |
| 13.2 | Mencari data Nasabah dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword pencarian. | Berhasil menampilkan data sesuai keyword pencarian. | P |  |
| 13.3 | Mencari data Nasabah dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 13.4 | Melihat detail Nasabah Perorangan | Klik icon '...' pada field Action salah satu data Nasabah - Klik Detail | Berhasil membuka halaman Detail Nasabah yang memuat informasi Biodata Nasabah, Data Pekerjaan, Saldo Rekening Tertinggi, serta tab Produk, Aktivitas Sales, dan Daftar Rekening (Tab Produk terpilih secara default). | Berhasil membuka halaman Detail Nasabah yang memuat informasi Biodata Nasabah, Data Pekerjaan, Saldo Rekening Tertinggi, serta tab Produk, Aktivitas Sales, dan Daftar Rekening (Tab Produk terpilih secara default). | P |  |
| 13.5 | Mencari data pada tab Produk dengan keyword valid | Pada tab Produk di halaman Detail Nasabah, input keyword pada field Search - Klik button Search | Berhasil menampilkan data Produk sesuai keyword pencarian. | Berhasil menampilkan data Produk sesuai keyword pencarian. | P |  |
| 13.6 | Mencari data pada tab Produk dengan keyword tidak valid | Pada tab Produk di halaman Detail Nasabah, input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan pada tab Produk. | Berhasil menampilkan informasi data tidak ditemukan pada tab Produk. | P |  |
| 13.7 | Mengekspor (Export) data Produk | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 13.8 | Membuka tab Aktivitas Sales | Pada halaman Detail Nasabah, klik tab 'Aktivitas Sales' | Berhasil membuka tab Aktivitas Sales dan menampilkan tabel histori Aktivitas Sales. | Berhasil membuka tab Aktivitas Sales dan menampilkan tabel histori Aktivitas Sales. | P |  |
| 13.9 | Mencari data pada tab Aktivitas Sales dengan keyword valid | Pada tab Aktivitas Sales, input keyword pada field Search - Klik button Search | Berhasil menampilkan data Aktivitas Sales sesuai keyword pencarian. | Berhasil menampilkan data Aktivitas Sales sesuai keyword pencarian. | P |  |
| 13.10 | Mencari data pada tab Aktivitas Sales dengan keyword tidak valid | Pada tab Aktivitas Sales, input kata kunci yang tidak valid pada field pencarian - Klik icon pencarian | Sistem menampilkan pesan bahwa data tidak ditemukan / tabel kosong. | Berhasil Sistem menampilkan pesan bahwa data tidak ditemukan / tabel kosong. | P |  |
| 13.11 | Mengekspor (Export) data Aktivitas Sales | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 13.12 | Melihat detail Aktivitas Sales pada kolom Action | Pada tab Aktivitas Sales, klik icon '...' pada salah satu data aktivitas - Klik Detail | Berhasil menampilkan detail data pribadi nasabah. | Berhasil menampilkan detail data pribadi nasabah. | P |  |
| 13.13 | Membuka tab Daftar Rekening | Pada halaman Detail Nasabah, klik tab 'Daftar Rekening' | Berhasil membuka tab Daftar Rekening dan menampilkan tabel Daftar Rekening nasabah. | Berhasil membuka tab Daftar Rekening dan menampilkan tabel Daftar Rekening nasabah. | P |  |
| 13.14 | Mencari data pada tab Daftar Rekening dengan keyword valid | Pada tab Daftar Rekening, input keyword pada field Search - Klik button Search | Berhasil Mencari data pada tab Daftar Rekening dengan keyword valid. | Berhasil Mencari data pada tab Daftar Rekening dengan keyword valid. | P |  |
| 13.15 | Mencari data pada tab Daftar Rekening dengan keyword tidak valid | Pada tab Daftar Rekening, input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil Mencari data pada tab Daftar Rekening dengan keyword tidak valid. | Berhasil Mencari data pada tab Daftar Rekening dengan keyword tidak valid. | P |  |
| 13.16 | Melihat detail load saldo rekening | Pada tab Daftar Rekening, klik salah satu Nomor Rekening pada tabel | Berhasil Melihat detail load saldo rekening. | Berhasil Melihat detail load saldo rekening. | P |  |
| 13.17 | Mengekspor (Export) data Daftar Rekening | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

14. Modul Bisnis dan Produk - Unit Bisnis

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 14.1 | Membuka halaman Unit Bisnis | Klik menu Bisnis & Produk - Klik sub menu Unit Bisnis | Berhasil membuka sub menu Unit Bisnis. | Berhasil membuka sub menu Unit Bisnis. | P |  |
| 14.2 | Mencari data Unit Bisnis dengan keyword valid | Input keyword valid pada field Cari Data - Klik button Cari | Berhasil menampilkan data sesuai pencarian. | Berhasil menampilkan data sesuai pencarian. | P |  |
| 14.3 | Mencari data Unit Bisnis dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data - Klik button Cari | Menampilkan data kosong. | Menampilkan data kosong. | P |  |
| 14.4 | Menambahkan data Unit Bisnis | Klik button Tambah Unit Bisnis - Isi field mandatory Name, Kode Unit Bisnis, dan Jenis Bisnis - Klik button Submit | Berhasil menyimpan unit bisnis baru. | Berhasil menyimpan unit bisnis baru. | P |  |
| 14.5 | Menambahkan data Unit Bisnis tanpa mengisi field mandatory | Klik button Tambah Unit Bisnis - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 14.6 | Mengubah data Unit Bisnis | Klik action menu titik tiga - Klik button Ubah Data - Ubah data pada form - Klik button Submit | Berhasil menyimpan perubahan. | Berhasil menyimpan perubahan. | P |  |
| 14.7 | Mengubah data Unit Bisnis tanpa mengisi field mandatory | Klik action menu titik tiga - Klik button Ubah Data - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 14.8 | Menghapus data Unit Bisnis | Klik action menu titik tiga - Klik button Hapus - Klik button Ya | Berhasil menghapus unit bisnis. | Berhasil menghapus unit bisnis. | P |  |
| 14.9 | Mengekspor data Unit Bisnis | Klik button Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

15. Modul Bisnis dan Produk - Produk

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 15.1 | Membuka halaman Produk | Klik menu Bisnis & Produk - Klik sub menu Produk | Berhasil membuka sub menu Produk. | Berhasil membuka sub menu Produk. | P |  |
| 15.2 | Mencari data Produk dengan keyword valid | Input keyword valid pada field Cari Data - Klik button Cari | Berhasil menampilkan data sesuai pencarian. | Berhasil menampilkan data sesuai pencarian. | P |  |
| 15.3 | Mencari data Produk dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data - Klik button Cari | Menampilkan data kosong. | Menampilkan data kosong. | P |  |
| 15.4 | Menambahkan data Produk | Klik button Tambah Produk - Isi field mandatory seluruh field mandatory - Klik button Submit | Berhasil menyimpan data Produk baru. | Berhasil menyimpan data Produk baru. | P |  |
| 15.5 | Menambahkan data Produk tanpa mengisi field mandatory | Klik button Tambah Produk - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 15.6 | Mengubah data Produk | Klik action menu titik tiga - Klik button Ubah Data - Ubah data pada form - Klik button Submit | Berhasil menyimpan perubahan. | Berhasil menyimpan perubahan. | P |  |
| 15.7 | Mengubah data Produk tanpa mengisi field mandatory | Klik action menu titik tiga - Klik button Ubah Data - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 15.8 | Menghapus data Produk secara massal (Bulk Delete) | Pilih beberapa data yang ingin dihapus dengan mencentang checkbox pada baris data - Klik button Hapus X data - Klik button Ya | Berhasil menghapus data Produk yang dipilih. | Berhasil menghapus data Produk yang dipilih. | P |  |
| 15.9 | Mengekspor data Produk | Klik button Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

16. Modul Bisnis dan Produk - Program Produk

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 16.1 | Membuka halaman Program Produk | Klik menu Bisnis & Produk - Klik sub menu Program Produk | Berhasil membuka sub menu Program Produk. | Berhasil membuka sub menu Program Produk. | P |  |
| 16.2 | Mencari data Program Produk dengan keyword valid | Input keyword valid pada field Cari Data - Klik button Cari | Berhasil menampilkan data sesuai pencarian. | Berhasil menampilkan data sesuai pencarian. | P |  |
| 16.3 | Mencari data Program Produk dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data - Klik button Cari | Menampilkan data kosong. | Menampilkan data kosong. | P |  |
| 16.4 | Menambahkan data Program Produk | Klik button Tambah Program Produk - Isi field mandatory Nama, Kode, dan deskripsi - Klik button Submit | Berhasil menyimpan data Program Produk baru. | Berhasil menyimpan data Program Produk baru. | P |  |
| 16.5 | Menambahkan data Program Produk tanpa mengisi field mandatory | Klik button Tambah Program Produk - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 16.6 | Mengubah data Program Produk | Klik action menu titik tiga - Klik button Ubah Data - Ubah data pada form - Klik button Submit | Berhasil menyimpan perubahan. | Berhasil menyimpan perubahan. | P |  |
| 16.7 | Mengubah data Program Produk tanpa mengisi field mandatory | Klik action menu titik tiga - Klik button Ubah Data - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 16.8 | Menghapus data Program Produk secara massal (Bulk Delete) | Pilih beberapa data yang ingin dihapus dengan mencentang checkbox pada baris data - Klik button Hapus X data - Klik button Ya | Berhasil menghapus data Program Produk yang dipilih. | Berhasil menghapus data Program Produk yang dipilih. | P |  |
| 16.9 | Mengekspor data Program Produk | Klik button Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 16.10 | Melakukan validasi data hasil export | Validasi data excel dengan tabel | Data pada excel sesuai dengan data pada tabel | Data pada excel sesuai dengan data pada tabel | P |  |

17. Modul Kantor - Tipe Kantor

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 17.1 | Membuka halaman Tipe Kantor | Klik menu Kantor - Klik sub menu Tipe Kantor | Berhasil membuka halaman Tipe Kantor. | Berhasil membuka halaman Tipe Kantor. | P |  |
| 17.2 | Mencari data Tipe Kantor dengan keyword valid | Input keyword valid pada field Cari Data - Klik button Search | Berhasil menampilkan data Tipe Kantor sesuai keyword. | Berhasil menampilkan data Tipe Kantor sesuai keyword. | P |  |
| 17.3 | Mencari data Tipe Kantor dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data - Klik button Search | Menampilkan pesan bahwa data tidak ditemukan. | Berhasil Menampilkan pesan bahwa data tidak ditemukan. | P |  |
| 17.4 | Menambahkan data Tipe Kantor | Klik button Tambah Tipe Kantor - Isi semua field mandatory - Klik button Submit | Berhasil menambahkan data Tipe Kantor. | Berhasil menambahkan data Tipe Kantor. | P |  |
| 17.5 | Menambahkan data Tipe Kantor tanpa mengisi field mandatory | Klik button Tambah Tipe Kantor - Kosongkan field mandatory - Klik button Submit | Menampilkan pesan error validasi mandatory. | Berhasil Menampilkan pesan error validasi mandatory. | P |  |
| 17.6 | Mengubah data Tipe Kantor | Klik menu Action pada salah satu data - Klik button Ubah data - Ubah data pada field yang tersedia - Klik button Submit | Berhasil mengubah data Tipe Kantor. | Berhasil mengubah data Tipe Kantor. | P |  |
| 17.7 | Mengubah data Tipe Kantor tanpa mengisi field mandatory | Klik menu Action pada salah satu data - Klik button Ubah data - Kosongkan field mandatory - Klik button Submit | Menampilkan pesan error validasi mandatory. | Berhasil Menampilkan pesan error validasi mandatory. | P |  |
| 17.8 | Menghapus data Tipe Kantor secara massal (Bulk Delete) | Pilih beberapa data yang ingin dihapus menggunakan checkbox - Klik button Hapus data - Klik button Yes pada popup konfirmasi | Berhasil menghapus data Tipe Kantor. | Berhasil menghapus data Tipe Kantor. | P |  |

18. Modul Kantor - Data Kantor

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 18.1 | Membuka halaman Data Kantor | Klik menu Kantor - Klik sub menu Data Kantor | Berhasil membuka sub menu Data Kantor. | Berhasil membuka sub menu Data Kantor. | P |  |
| 18.2 | Mencari data kantor dengan keyword valid | Input keyword valid pada field Cari Data - Klik button Cari | Berhasil menampilkan data sesuai pencarian. | Berhasil menampilkan data sesuai pencarian. | P |  |
| 18.3 | Mencari data kantor dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data - Klik button Cari | Menampilkan data kosong. | Berhasil Menampilkan data kosong. | P |  |
| 18.4 | Menambahkan data kantor | Klik button Tambah Data Kantor - Isi field mandatory Nama, Kode Kantor, Tipe Kantor, No Telepon, dan Parent - Klik button Submit | Berhasil menyimpan data kantor baru. | Berhasil menyimpan data kantor baru. | P |  |
| 18.5 | Menambahkan data kantor tanpa mengisi field mandatory | Klik button Tambah Data Kantor - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Berhasil Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 18.6 | Mengubah data kantor | Klik action menu titik tiga - Klik button Ubah Data - Ubah data pada form - Klik button Submit | Berhasil menyimpan perubahan. | Berhasil menyimpan perubahan. | P |  |
| 18.7 | Mengubah data kantor tanpa mengisi field mandatory | Klik action menu titik tiga - Klik button Ubah Data - Kosongkan salah satu field mandatory - Klik button Submit | Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | Berhasil Menampilkan pesan validasi wajib diisi dan data tidak disimpan. | P |  |
| 18.8 | Menghapus data kantor secara massal (Bulk Delete) | Pilih beberapa data yang ingin dihapus dengan mencentang checkbox pada baris data - Klik button Hapus X data - Klik button Yes | Berhasil menghapus data kantor yang dipilih. | Berhasil menghapus data kantor yang dipilih. | P |  |
| 18.9 | Mengekspor data kantor | Klik button Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

19. Modul Menu Target

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 19.1 | Membuka halaman menu target | Klik menu 'Menu Target' | Menampilkan halaman menu target | Berhasil Menampilkan halaman menu target | P |  |
| 19.2 | Filter data | Pilih kantor wilayah - Pilih kantor cabang - Pilih kantor cabang pembantu (jika ada) - Pilih Bisnis Unit - Pilih Produk - Pilih sales - Pilih bulan - Pilih tahun - Klik button Submit | Berhasil menampilkan data target sesuai dengan filter yang di pilih | Berhasil menampilkan data target sesuai dengan filter yang di pilih | P |  |
| 19.3 | Mengosongkan semua filter mandatory | Kosongkan semua filter - Klik button Submit | Menampilkan alert pada setiap filter mandatory dengan informasi 'dibutuhkan' | Berhasil Menampilkan alert pada setiap filter mandatory dengan informasi 'dibutuhkan' | P |  |
| 19.4 | Set data target untuk semua sales dalam satu kantor cabang | Ketika filter data sales, pilih semua sales - Input data target di tabel 'Set Target Cabang (nama kc)' - Klik button Set ke semua sales - Klik button Simpan | Berhasil menyimpan dan mengatur data target semua sales di kc tersebut sesuai dengan bisnis unit dan produk yang di pilih, menampilkan popup 'Sukses menyimpan data target' | Berhasil menyimpan dan mengatur data target semua sales di kc tersebut sesuai dengan bisnis unit dan produk yang di pilih, menampilkan popup 'Sukses menyimpan data target' | P |  |
| 19.5 | Set data target tanpa klik button Simpan | Input data target - Klik button Set ke semua sales | Berhasil set ke semua sales tetapi data nya tidak tersimpan | Berhasil set ke semua sales tetapi data nya tidak tersimpan | P |  |
| 19.6 | Set data target untuk satu sales | Ketika filter sales, pilih salah satu sales - Input data target sales - Klik button Simpan | Berhasil menyimpan dan mengatur data target sales tersebut, menampilkan popup 'Sukses menyimpan data target' | Berhasil menyimpan dan mengatur data target sales tersebut, menampilkan popup 'Sukses menyimpan data target' | P |  |

20. Modul Upload Bulk - Upload Target Bulk

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 20.1 | Membuka halaman Upload Target Bulk | Klik menu Upload Bulk - Klik submenu Upload Target Bulk | Menampilkan halaman Upload target bulk | Berhasil Menampilkan halaman Upload target bulk | P |  |
| 20.2 | Download Template upload target bulk | Pilih Bisnis Unit - Klik button Download dan Upload File - Klik button Download file template - Buka file excel | File excel dapat di buka | Berhasil File excel dapat di buka | P |  |
| 20.3 | Download Template upload bulk tanpa memilih bisnis unit | Kosongkan bisnis unit - Klik button Download dan Upload File - Klik button Download file template | Tidak bisa mengunduh dan menampilkan alert 'Bisnis Unit wajib dipilih sebelum download template' | Berhasil Tidak bisa mengunduh dan menampilkan alert 'Bisnis Unit wajib dipilih sebelum download template' | P |  |
| 20.4 | Upload Target bulk dengan data yang valid | Buka file excel - Input data upload target bulk - Simpan file excel - Pilih Bisnis Unit yang sesuai - Klik 'Pilih atau seret file Template (.xlsx) ke area ini' - Pilih file yang sudah di input - Klik button Open pada file manager | Berhasil mengupload data target secara bulk, dan status nya Selesai | Berhasil mengupload data target secara bulk, dan status nya Selesai | P |  |
| 20.5 | Upload Target bulk dengan template yang tidak sesuai | Upload data target bulk dengan template yang tidak sesuai | Menampilkan status Template Tidak Valid dan gagal upload bulk data tidak tersimpan atau terupdate | Berhasil Menampilkan status Template Tidak Valid dan gagal upload bulk data tidak tersimpan atau terupdate | P |  |
| 20.6 | Menampilkan detail batch | Klik button Aksi (...) - Klik detail batch | Menampilkan data detail | Berhasil Menampilkan data detail | P |  |
| 20.7 | Download source File | Klik button Aksi (...) – Klik download souce file | Berhasil mengunduh data souce file | Berhasil mengunduh data souce file | P |  |
| 20.8 | Menampilkan preview data | Klik button Aksi (...) - Klik preview data | Menampilkan detail data hasil upload dan penjelasan jika terdapat validasi error pada file yang diupload | Berhasil Menampilkan detail data hasil upload dan penjelasan jika terdapat validasi error pada file yang diupload | P |  |
| 20.9 | Menghapus batch data | Klik button Aksi (...) – klik hapus batch | Berhasil menghapus data | Berhasil menghapus data | P |  |
| 20.10 | Download error file | Klik button Aksi (...) pada file dengan status “validasi gagal” – klik download error file | Berhasil download error file | Berhasil download error file | P |  |
| 20.11 | Batalkan batch | Klik button Aksi (...) pada file dengan status “validasi gagal” – klik batalkan | Berhasil membatalkan batch | Berhasil membatalkan batch | P |  |
| 20.12 | Upload ulang file gagal | Klik button Aksi (...) pada file dengan status “gagal” – klik coba lagi (retry) | Berhasil mengupload ulang file | Berhasil mengupload ulang file | P |  |
| 20.13 | Mencari data pada kolom pencarian | Input batch id pada kolom pencarian | Berhasil menampilkan data sesuai kata kunci yang diinput | Berhasil menampilkan data sesuai kata kunci yang diinput | P |  |
| 20.14 | Melakukan filter data | Pilih status | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |

21. Modul Upload Bulk - Bulk Import User

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 21.1 | Membuka halaman Bulk Import User | Klik menu Upload Bulk - Klik submenu Bulk Import User | Menampilkan halaman Bulk Import User | Berhasil Menampilkan halaman Bulk Import User | P |  |
| 21.2 | Download Template upload bulk User | Klik button Download dan Upload File - Klik button Download file template - Buka file excel | File excel dapat di buka | Berhasil File excel dapat di buka | P |  |
| 21.3 | Upload file data upload bulk user dengan data yang valid | Buka file excel - Input data user - Simpan file excel - Klik 'Pilih atau seret file Template (.xlsx) ke area ini' - Pilih file yang sudah di input - Klik button Open pada file manager | Berhasil mengupload data user secara bulk dengan status Selesai, kemudian data akan masuk pada menu user | Berhasil mengupload data user secara bulk dengan status Selesai, kemudian data akan masuk pada menu user | P |  |
| 21.4 | Upload file dengan no telepon bukan berupa angka | Buka file excel - Input data user - Simpan file excel - Klik 'Pilih atau seret file Template (.xlsx) ke area ini' - Pilih file yang sudah di input - Klik button Open pada file manager | Menampilkan validasi error ‘nomor telepon harus berupa angka’ | Berhasil Menampilkan validasi error ‘nomor telepon harus berupa angka’ | P |  |
| 21.5 | Upload file dengan email yang sudah terdaftar | Buka file excel - Input data user - Simpan file excel - Klik 'Pilih atau seret file Template (.xlsx) ke area ini' - Pilih file yang sudah di input - Klik button Open pada file manager | Menampilkan validasi error  ’email sudah terdaftar’ | Berhasil Menampilkan validasi error  Berhasil ’email sudah terdaftar’ | P |  |
| 21.6 | Menginput email tanpa spesial karakter | Input password tanpa special character | Indikator One special character tidak terpenuhi dan button Save Password tetap disabled | Berhasil Indikator One special character tidak terpenuhi dan button Save Password tetap disabled | P |  |

22. Modul Upload Bulk - Bulk Import Prospek - Prospek Personal

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 22.1 | Membuka halaman upload bulk prospek personal | Klik menu Upload Bulk - Klik submenu Bulk Import Prospek - Klik Prospek Personal | Menampilkan halaman bulk import prospek personal | Berhasil Menampilkan halaman bulk import prospek personal | P |  |
| 22.2 | Download Template upload bulk prospek personal | Klik button Download dan Upload File - Klik button Download file template - Buka file excel | File excel dapat di buka | Berhasil File excel dapat di buka | P |  |
| 22.3 | Upload file prospek personal dengan data yang valid | Buka file excel - Input data prospek personal - Simpan file excel - Klik 'Pilih atau seret file Template (.xlsx) ke area ini' - Pilih file yang sudah di input - Klik button Open pada file manager | Berhasil mengupload data prospek personal secara bulk, dan status nya Selesai | Berhasil mengupload data prospek personal secara bulk, dan status nya Selesai | P |  |
| 22.4 | Validasi data yang berhasil di upload | Login menggunakan user yang di assign ketika input data pada excel - Klik menu Lead Qualification - Klik submenu Aktifitas - Cek data prospek yang di uplaod melalui menu Bulk Import Prospek - Cek detail prospek pada halaman detail dan aktifitas marketing | Menampilkan semua informasi data prospek yang sesuai dengan yang di upload di menu Bulk Import Prospek Personal dengan keterangan 'Registered based on excel' | Berhasil Menampilkan semua informasi data prospek yang sesuai dengan yang di upload di menu Bulk Import Prospek Personal dengan keterangan 'Registered based on excel' | P |  |
| 22.5 | Upload file prospek dengan template yang tidak sesuai | Upload data prospek personal dengan template yang tidak sesuai | Berhasil upload dengan status 'Template Tidak Valid' dan data tidak tersimpan | Berhasil upload dengan status 'Template Tidak Valid' dan data tidak tersimpan | P |  |
| 22.6 | Tidak menginput kolom data mandatory | Input data pada template excel yang telah di download, tetapi kosongkan kolom yang wajib diisi (email dan produk) - Simpan file - Klik 'Pilih atau seret file template (.xlsx) ke area ini' - Pilih file yang tadi di simpan - Klik button Open pada file manager | Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'Wajid diisi' pada halaman preview data dan dokumen error. data prospek tidak tersimpan | Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'Wajid diisi' pada halaman preview data dan dokumen error. data prospek tidak tersimpan | P |  |
| 22.7 | Menginput email yang tidak valid | Input email yang tidak valid pada kolom email (ex. heri.com) - Simpan file - Upload file | Berhasil upload file dengan status 'Validasi Gagal' dan menampilkan informasi validation error 'Format email tidak valid' pada halaman preview data dan dokumen error. data prospek tidak tersimpan | Berhasil upload file dengan status 'Validasi Gagal' | P |  |
| 22.8 | Menginput no CIF yang tidak valid untuk nasabah ETB | Input no CIF yang tidak valid - Simpan file - Upload file | Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'no CIF tidak ditemukan' pada halaman preview data dan dokumen error. data prospek tidak tersimpan | Berhasil upload file dengan status 'Validasi Gagal' | P |  |
| 22.9 | Menginput tanggal aktivitas (call, open account, dan top up) sebelum tanggal prospek | Input tanggal Call, Open Account, Top up sebelum tanggal prospek - Simpan file - Upload file - Cek data pada halaman preview data dan dokumen error | Menampilkan informasi 'Tanggal call tidak boleh sebelum tanggal prospek', 'Tanggal Open Account tidak boleh sebelum tanggal prospek' , 'Tanggal Top up tidak boleh sebelum tanggal prospek' pada masing masing kolom | Berhasil upload file dengan status 'Validasi Gagal' | P |  |
| 22.10 | Validasi Format tanggal | Input tanggal dengan format yang tidak sesuai - Simpan file - Upload file - Cek data pada halaman preview data dan dokumen error | Menampilkan informasi 'Format tanggal harus DD-MM-YYYY' | Menampilkan informasi 'Tanggal aktivitas tidak boleh sebelum tanggal prospek' | P |  |
| 22.11 | Validasi input Potensi dan Jumlah Dana Masuk | Input selain nominal angka di kolom Potensi dan Jumlah Dana Masuk (Top Up) - Simpan file - Upload file - Cek data pada halaman preview data dan dokumen error | Menampilkan informasi 'Jumlah dana masuk (Top Up) harus angka' | Menampilkan informasi 'Format tanggal tidak sesuai' | P |  |
| 22.12 | Membatalkan upload data prospek personal | Upload file data prospek personal yang valid - Klik Action titik tiga - Klik button Batalkan selagi status upload masih dalam antrian | Berhasil membatalkan upload bulk data prospek personal, status nya menjadi 'Dibatalkan' | Menampilkan informasi 'Jumlah dana harus berupa angka' | P |  |
| 22.13 | Pagination di Preview Data | Klik pagination (10/halaman) - Pilih berapa data yang ingin di tampilkan | Berhasil menampilkan data sesuai dengan pagination yang di pilih | Berhasil membatalkan upload bulk data prospek personal | P |  |
| 22.14 | Pindah Halaman di Preview Data | Input angka halaman di field pindah halaman - Klik Enter pada keyboard | Berhasil menampilkan halaman sesuai dengan angka halaman yang di input | Berhasil menampilkan data sesuai dengan limit pagination yang dipilih | P |  |
| 22.15 | Mencari data berdasarkan batch id upload bulk prospek personal | Input batch id pada field search - Klik icon search atau klik Enter | Menampilkan data upload bulk prospek personal sesuai dengan batch id yang di cari | Berhasil menampilkan halaman sesuai dengan input nomor halaman | P |  |
| 22.16 | Filter status upload bulk prospek personal | Klik Filter Status - Pilih dan klik salah satu status | Menampilkan data upload bulk prospek personal sesuai dengan status yang di pilih | Menampilkan data upload bulk prospek personal sesuai batch id pencarian | P |  |
| 22.17 | Validasi data yang berhasil di upload | Login menggunakan user yang di assign ketika input data pada excel - Klik menu Lead Qualification - Klik submenu Aktifitas - Cek data prospek yang di uplaod melalui menu Bulk Import Prospek - Cek detail prospek pada halaman detail dan aktifitas marketing | Menampilkan semua informasi data prospek yang sesuai dengan yang di upload di menu Bulk Import Prospek lembaga dengan keterangan 'Registered based on excel' | Menampilkan data upload bulk prospek personal sesuai filter yang dipilih | P |  |
| 22.18 | Upload file prospek dengan template yang tidak sesuai | Upload data prospek lembaga dengan template yang tidak sesuai | Menampilkan status Template Tidak Valid dan gagal upload bulk data tidak tersimpan | Menampilkan semua informasi data prospek yang telah berhasil diupload | P |  |

23. Modul Upload Bulk - Bulk Import Prospek - Prospek Lembaga

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 23.1 | Membuka halaman upload bulk Prospek Lembaga | Klik menu Upload Bulk - Klik submenu Bulk Import Prospek - Klik Prospek Lembaga | Menampilkan halaman bulk import prospek lembaga | Berhasil Menampilkan halaman bulk import prospek lembaga | P |  |
| 23.2 | Download Template upload bulk Prospek Lembaga | Klik button Download dan Upload File - Klik button Download file template - Buka file excel | File excel dapat di buka | Berhasil File excel dapat di buka | P |  |
| 23.3 | Upload file Prospek Lembaga dengan data yang valid | Buka file excel - Input data prospek lembaga - Simpan file excel - Klik 'Pilih atau seret file Template (.xlsx) ke area ini' - Pilih file yang sudah di input - Klik button Open pada file manager | Berhasil mengupload data prospek lembaga secara bulk, dan status nya Selesai | Berhasil mengupload data prospek lembaga secara bulk, dan status nya Selesai | P |  |
| 23.4 | Menginput no CIF yang tidak valid untuk nasabah lembaga ETB | Input no CIF yang tidak valid - Simpan file - Upload file | Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'no CIF tidak ditemukan' pada halaman preview data dan dokumen error. data prospek tidak tersimpan | Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'no CIF tidak ditemukan' pada halaman preview data dan dokumen error. data prospek tidak tersimpan | P |  |
| 23.5 | Membatalkan upload data Prospek Lembaga | Upload file data prospek lembaga yang valid - Klik Action titik tiga - Klik button Batalkan selagi status upload masih dalam antrian | Berhasil membatalkan upload bulk data prospek lembaga, status nya menjadi 'Dibatalkan' | Berhasil membatalkan upload bulk data prospek lembaga, status nya menjadi 'Dibatalkan' | P |  |
| 23.6 | Mencari data berdasarkan batch id upload bulk Prospek Lembaga | Input batch id pada field search - Klik icon search atau klik Enter | Menampilkan data upload bulk prospek lembaga sesuai dengan batch id yang di cari | Berhasil Menampilkan data upload bulk prospek lembaga sesuai dengan batch id yang di cari | P |  |
| 23.7 | Filter status upload bulk Prospek Lembaga | Klik Filter Status - Pilih dan klik salah satu status | Menampilkan data upload bulk prospek lembaga sesuai dengan status yang di pilih | Berhasil Menampilkan data upload bulk prospek lembaga sesuai dengan status yang di pilih | P |  |

24. Modul Lead Generation - Prospek Individu

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 24.1 | Membuka halaman prospek individu | Klik menu Lead Generation - Klik submenu Prospek Individu | Menampilkan halaman input prospek individu Step 1 | Berhasil Menampilkan halaman input prospek individu Step 1 | P |  |
| 24.2 | Menginput data prospek individu step 1 | Input nama nasabah - Input nomor telepon - Input kontak - Input nomor KTP - Klik button arrow kanan | Menampilkan form inputan prospek individu step 2 | Berhasil Menampilkan form inputan prospek individu step 2 | P |  |
| 24.3 | Menginput huruf di field nomor telepon | Input huruf pada field nomor telepon | Menampilkan informasi 'Nomor telepon tidak valid' | Berhasil Menampilkan informasi 'Nomor telepon tidak valid' | P |  |
| 24.4 | Menginput nomor telepon kurang dari 10 digit | Input nomor telepon kurang dari 10 digit | Menampilkan informasi 'Panjang nomor telepon minimal 10 digit angka' | Berhasil Menampilkan informasi 'Panjang nomor telepon minimal 10 digit angka' | P |  |
| 24.5 | Menginput huruf di field nomor KTP | Input huruf pada field nomor KTP | Menampilkan informasi 'Nomor KTP tidak valid, harus berupa angka' | Berhasil Menampilkan informasi 'Nomor KTP tidak valid, harus berupa angka' | P |  |
| 24.6 | Menginput angka di field nomor KTP kurang dari 16 digit | Input angka nomor ktp kurang dari 16 digit | Menampilkan informasi ' Panjang nomor KTP minimal 16' | Berhasil Menampilkan informasi ' Panjang nomor KTP minimal 16' | P |  |
| 24.7 | Tidak menginput field mandatory step 1 (nama nasabah dan nomor telepon) | Kosongkan field inputan nama nasabah dan nomor telepon - Input Step 2 - Input Step 3 - Input Step 4 - Klik button Simpan | Menampilkan alert 'nama nasabah / lembaga belum di masukkan' dan 'Nomor telepon belum dimasukkan' | Berhasil Menampilkan alert 'nama nasabah / lembaga belum di masukkan' dan 'Nomor telepon belum dimasukkan' | P |  |
| 24.8 | Menginput data prospek step 2 | Input email - Input alamat - Input RT - Input RW - Input kelurahan - Input kecamatan - Input kota - Input kode pos - Input tempat lahir - Pilih tanggal lahir - Pilih jenis kelamin - Pilih agama - Pilih status rumah - Pilih pendidikan terakhir - Klik button Selanjutnya | Menampilkan halaman step 3 (Pekerjaan Nasabah) | Berhasil Menampilkan halaman step 3 (Pekerjaan Nasabah) | P |  |
| 24.9 | Menginput data prospek step 3 | Input nama perusahaan - Input alamat perusahaan - Input kota perusahaan - Input kontak perusahaan - Input gaji - Input posisi - Input departemen - Klik button Selanjutnya | Berhasil menyimpan data pekerjaan dan menampilkan form input data step 4 | Berhasil menyimpan data pekerjaan dan menampilkan form input data step 4 | P |  |
| 24.10 | Menginput data step 4 | Pilih apakah prospek berupa referal - Pilih produk - Pilih program - Pilih sumber prospek - Input potensi kredit/dana - Pilih tanggal potensi dana masuk/realisasi kredit - Input catatan tambahan mengenai prospek - Pilih apakah nasabah ini termasuk ekosistem? - Klik button Simpan - Klik button Selesai - Klik button Lihat aktifitas | Berhasil menginput data prospek dan data akan tampil pada menu lead qualification aktifitas | Berhasil menginput data prospek dan data akan tampil pada menu lead qualification aktifitas | P |  |
| 24.11 | Melakukan reset data prospek yang sudah di input | Klik button Reset Form - Klik OK | Berhasil mengosongkan semua field yang sudah di input dari step 1 sampai 4 | Berhasil mengosongkan semua field yang sudah di input dari step 1 sampai 4 | P |  |

25. Modul Lead Generation - Prospek Lembaga

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 25.1 | Membuka halaman prospek lembaga | Klik menu Lead Generation - Klik submenu Prospek Lembaga | Menampilkan halaman input prospek lembaga step 1 | Berhasil Menampilkan halaman input prospek lembaga step 1 | P |  |
| 25.2 | Menginput data prospek lembaga step 1 | Input nama lembaga - Input nomor telepon - Input kontak - Input nomor NPWP - Klik right arrow button | Menampilkan halaman input data step 2 | Berhasil Menampilkan halaman input data step 2 | P |  |
| 25.3 | Menginput data prospek lembaga step 2 | Input email perusahaan - Pilih tanggal berdiri - Input alamat perusahaan - Input kode pos - Input pemegang saham, bidang usaha, nama direktur utama, wakil direktur utama, direktur keuangan, direktur perencanaan, direktur pengembangan bisnis, direktur pemasaran, direktur SDM, website perusahaan, penunjangan bisnis, Nomor SIUP, dan kode developer - Klik button Selanjutnya | Menampilkan halaman input data prospek lembaga step 3 | Berhasil Menampilkan halaman input data prospek lembaga step 3 | P |  |
| 25.4 | Menginput data step 3 | Pilih apakah prospek berupa referal - Pilih produk - Pilih program - Pilih sumber prospek - Input potensi kredit/dana - Pilih tanggal potensi dana masuk/realisasi kredit - Input catatan tambahan mengenai prospek - Pilih apakah nasabah ini termasuk ekosistem? - Klik button Simpan - Klik button Selesai - Klik button Lihat aktifitas | Berhasil menginput data prospek dan data akan tampil pada menu lead qualification aktifitas | Berhasil menginput data prospek dan data akan tampil pada menu lead qualification aktifitas | P |  |

26. Modul Lead Qualification - Aktifitas

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 26.1 | Membuka halaman Aktifitas | Klik menu Lead Qualification - Klik submenu Aktifitas | Menampilkan halaman Aktifitas | Berhasil Menampilkan halaman Aktifitas | P |  |
| 26.2 | Filter data | Pilih Produk - Pilih Staging - Pilih Bulan - Pilih Tahun - Pilih source debitur - Pilih status prospek - Pilih apakah nasabah lembaga - Klik button Filter Data | Menampilkan data aktifitas prospek sesuai dengan filter yang telah di pilih | Berhasil Menampilkan data aktifitas prospek sesuai dengan filter yang telah di pilih | P |  |
| 26.3 | Melihat detail prospek | Klik titik tiga - Klik Detail Prospek | Menampilkan halaman detail prospek | Berhasil Menampilkan halaman detail prospek | P |  |
| 26.4 | Mengubah data prospek | Klik titik tiga - Klik Aktifitas Marketing - Klik salah satu data yang ada pada section registered (Input data nasabah, data pribadi,Pekerjaan dan produk) - Ubah data - Klik button Simpan atau Submit | Berhasil menyimpan perubahan data nasabah | Berhasil menyimpan perubahan data nasabah | P |  |
| 26.5 | Melakukan aktifitas marketing (Call) | Klik Input data call - Pilih status call - Input remark call - Klik button Simpan | Berhasil menyimpan data aktifitas marketing call. menampilkan popup 'Sukses update call nasabah'. informasi masuk pada log staging call dan log aktifitas kemudian staging berubah dari registered menjadi call | Berhasil menyimpan data aktifitas marketing call. menampilkan popup 'Sukses update call nasabah'. informasi masuk pada log staging call dan log aktifitas kemudian staging berubah dari registered menjadi call | P |  |
| 26.6 | Melakukan aktifitas marketing prospek (Call) dengan status 'nasabah menolak' | Lakukan aktifitas marketing call dengan status call 'Menolak' - Lakukan aktifitas marketing call kembali dengan status lain | Menampilkan popup alert 'Anda tidak dapat memindahkan dari stage Ditolak ke Call' | Berhasil Menampilkan popup alert 'Anda tidak dapat memindahkan dari stage Ditolak ke Call' | P |  |
| 26.7 | Melakukan call dengan menambahkan pengingat | Buka halaman Aktifitas Marketing - Klik "Input Data Call" - Pilih Status Call - Isi Remark - Centang checkbox "Buat reminder pengingat (tugas Calendar) setelah simpan" - Klik button "Simpan" | Berhasil menyimpan data aktivitas call nasabah dan sistem otomatis membuat pengingat (tugas) pada section Tugas Terkait / Kalender | Berhasil menyimpan data aktivitas call dan otomatis membuat pengingat pada section Tugas Terkait / Kalender | P |  |
| 26.8 | Validasi data visit in prospek | Klik input data visit - Cek detail status dan deskripsi visit | Menampilkan detail data yang sesuai dengan status dan deskripsi visit yang di input sales | Berhasil Menampilkan detail data yang sesuai dengan status dan deskripsi visit yang di input sales | P |  |
| 26.9 | Melakukan aktifitas marketing open account | Klik Input Data NOA Open Account - Input nomor rekening - Pilih tanggal dana masuk - Pilih apakah nasabah sudah mengaktifkan Mbanking - Input remark - Klik button Simpan | Berhasil menyimpan data NOA Open Account, menampilkan popup 'berhasil melakukan input data open account sukses' dan status prospek atau staging berubah menjadi Pembukaan | Berhasil menyimpan data NOA Open Account, menampilkan popup 'berhasil melakukan input data open account sukses' dan status prospek atau staging berubah menjadi Pembukaan | P |  |
| 26.10 | Menginput huruf pada field nomor rekening di form Input data NOA Open Account | Input huruf pada field nomor rekening | Karakter huruf tidak dapat diinput ke field Nomor Rekening. Field tetap kosong atau hanya menerima karakter numerik. | Berhasil Karakter huruf tidak dapat diinput ke field Nomor Rekening. Field tetap kosong atau hanya menerima karakter numerik. | P |  |
| 26.11 | Melakukan aktifitas marketing ETB (Top up Dana ) | Klik Input Data Top Up pada halaman aktifitas prospek ETB - Input nomor rekening - Pilih tanggal masuk - Input dana top up - Pilih apakah nasabah sudah mengaktifkan Mbanking? - Input Remark | Berhasil menginput remark | Berhasil menginput remark | P |  |
| 26.12 | Tidak menginput field mandatory pada halaman Dana Top Up | Kosongkan salah satu atau semua inputan field mandatory - Klik button Simpan | Menampilkan alert pada setiap field mandatory bahwa field tersebut dibutuhkan untuk diisi | Berhasil Menampilkan alert pada setiap field mandatory bahwa field tersebut dibutuhkan untuk diisi | P |  |
| 26.13 | Membatalkan prospek | Klik button Batalkan Prospek - Klik 'Iya' | Berhasil membatalkan prospek, muncul popup 'Prospek telah dibatalkan' dan staging berubah menjadi Batal | Berhasil membatalkan prospek, muncul popup 'Prospek telah dibatalkan' dan staging berubah menjadi Batal | P |  |
| 26.14 | Membuka halaman Aktifitas Marketing prospek Lending | Klik icon titik tiga (...) pada prospek Lending - Klik Aktifitas Marketing | Menampilkan halaman Aktifitas Marketing prospek Lending | Berhasil menampilkan halaman Aktifitas Marketing prospek Lending | P |  |
| 26.15 | Melakukan aktifitas marketing prospek Lending (Call) | Klik Input Data Call - Pilih Status Call - Input remark - Klik button Simpan | Berhasil menyimpan data aktifitas call nasabah Lending | Berhasil menyimpan data aktifitas call nasabah Lending | P |  |
| 26.16 | Validasi data visit prospek Lending | Klik Input Data Visit - Cek detail data visit | Menampilkan detail data visit nasabah Lending yang sesuai | Berhasil menampilkan detail data visit nasabah Lending yang sesuai | P |  |
| 26.17 | Validasi data Proses Pemeriksaan prospek Lending | Klik Detail Data Proses Pemeriksaan - Cek detail data proses pemeriksaan | Menampilkan detail data proses pemeriksaan prospek Lending | Berhasil menampilkan detail data proses pemeriksaan prospek Lending | P |  |
| 26.18 | Validasi data Proses Verifikasi dan Analisa prospek Lending | Klik Detail Data Proses Verifikasi dan Analisa - Cek detail data proses verifikasi dan analisa | Menampilkan detail data proses verifikasi dan analisa prospek Lending | Berhasil menampilkan detail data proses verifikasi dan analisa prospek Lending | P |  |
| 26.19 | Validasi data Persetujuan Kredit prospek Lending | Klik Detail Data Persetujuan Kredit - Cek detail data persetujuan kredit | Menampilkan detail data persetujuan kredit prospek Lending | Berhasil menampilkan detail data persetujuan kredit prospek Lending | P |  |
| 26.20 | Validasi data Realisasi/Pencairan Kredit prospek Lending | Klik Detail Data Realisasi/Pencairan Kredit - Cek detail data realisasi pencairan kredit | Menampilkan detail data realisasi/pencairan kredit prospek Lending | Berhasil menampilkan detail data realisasi/pencairan kredit prospek Lending | P |  |
| 26.21 | Validasi data Batal prospek Lending | Klik Detail Data Batal - Cek detail data pembatalan | Menampilkan detail data pembatalan prospek Lending | Berhasil menampilkan detail data pembatalan prospek Lending | P |  |
| 26.22 | Validasi data Ditolak prospek Lending | Klik Detail Data Ditolak - Cek detail data penolakan | Menampilkan detail data penolakan prospek Lending | Berhasil menampilkan detail data penolakan prospek Lending | P |  |

27. Modul Lead Qualification - Aktifitas Referal

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 27.1 | Membuka halaman Aktifitas Referal | Klik menu Lead Qualification - Klik sub menu Aktifitas Referal | Berhasil membuka halaman Aktifitas Referal. | Berhasil membuka halaman Aktifitas Referal. | P |  |
| 27.2 | Melakukan filter data Aktifitas Referal | Klik button Filter - Pilih parameter filter - Klik button Terapkan | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 27.3 | Melihat data tab Prospek yang saya referalkan | Klik tab Prospek yang saya referalkan | Berhasil menampilkan data pada tab Prospek yang saya referalkan. | Berhasil menampilkan data pada tab Prospek yang saya referalkan. | P |  |
| 27.4 | Mencari data tab Prospek yang saya referalkan dengan keyword valid | Mengisi field Search dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 27.5 | Mencari data tab Prospek yang saya referalkan dengan keyword tidak valid | Mengisi field Search dengan keyword tidak valid - Klik button Search | Menampilkan pesan data tidak ditemukan. | Berhasil Menampilkan pesan data tidak ditemukan. | P |  |
| 27.6 | Melihat detail tab Prospek yang saya referalkan | Klik icon aksi detail pada salah satu baris tab Prospek yang saya referalkan | Berhasil menampilkan detail prospek. | Berhasil menampilkan detail prospek. | P |  |
| 27.7 | Melihat data tab Prospek yang direferalkan ke saya | Klik tab Prospek yang direferalkan ke saya | Berhasil menampilkan data pada tab Prospek yang direferalkan ke saya. | Berhasil menampilkan data pada tab Prospek yang direferalkan ke saya. | P |  |
| 27.8 | Mencari data tab Prospek yang direferalkan ke saya dengan keyword valid | Mengisi field Search dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |

28. Modul List Prospek ETB

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 28.1 | Membuka halaman List Prospek ETB | Klik menu List Prospek ETB | Menampilkan halaman list prospek ETB | Berhasil Menampilkan halaman list prospek ETB | P |  |
| 28.2 | Filter data list prospek ETB | Pilih produk - Pilih jenis nasabah - Pilih bulan - Pilih tahun - Klik button Filter Data | Berhasil menampilkan data list prospek ETB sesuai dengan filter yang di pilih | Berhasil menampilkan data list prospek ETB sesuai dengan filter yang di pilih | P |  |
| 28.3 | Mencari data list prospek ETB | Input keyword pada field search - Klik icon search yang ada di sebelah field search | Berhasil menampilkan data list prospek ETB sesuai dengan keyword yang dai cari | Berhasil menampilkan data list prospek ETB sesuai dengan keyword yang dai cari | P |  |
| 28.4 | Menghapus data list prospek ETB | Klik chcekbox yang ada di samping data list prospek ETB - Klik Hapus data terpilih - Klik button Ya, Hapus | Berhasil menghapus data list prospek ETB yang telah di pilih | Berhasil menghapus data list prospek ETB yang telah di pilih | P |  |
| 28.5 | Menghapus semua data list prospek ETB | Klik button Hapus semua data () - Klik button Ya, Hapus semua | Berhasil menghapus semua data list prospek ETB dan data tabel menjadi kosong | Berhasil menghapus semua data list prospek ETB dan data tabel menjadi kosong | P |  |
| 28.6 | Mengunduh data list prospek ETB | Klik button Export Data - Klik icon unduh data pada download history drawer | Berhasil mengunduh data list prospek ETB dalam bentuk file Excel | Berhasil mengunduh data list prospek ETB dalam bentuk file Excel | P |  |
| 28.7 | Menampilkan detail list prospek ETB | Klik titik tiga pada Aksi - Klik Detail Prospek | Menampilkan halaman detail prospek ETB | Berhasil Menampilkan halaman detail prospek ETB | P |  |
| 28.8 | Melakukan Prospek Ulang | Klik titik tiga pada Aksi - Klik Prospek Ulang - Input data Informasi Produk - Klik button Simpan - Klik button Ya | Berhasil melakukan prospek ulang dengan popup 'Prospek Ulang Berhasil' dan data prospek tersebut akan masuk ke halaman aktifitas | Berhasil melakukan prospek ulang dengan popup 'Prospek Ulang Berhasil' dan data prospek tersebut akan masuk ke halaman aktifitas | P |  |
| 28.9 | Menampilkan informasi rekening | Klik titik tiga pada Aksi - Klik Informasi rekening - Klik button Tutup | Modal informasi rekening tertutup dan tetap di halaman list prospek ETB | Berhasil Modal informasi rekening tertutup dan tetap di halaman list prospek ETB | P |  |

29. Modul Menu Absent - Dashboard Absent

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 29.1 | Membuka halaman Dashboard Absent | Klik menu Menu Absent - Klik sub menu Dashboard Absent | Berhasil menampilkan halaman Dashboard Absent. | Berhasil menampilkan halaman Dashboard Absent. | P |  |
| 29.2 | Melakukan filter data Dashboard Absent | Klik button Filter - Isi filter - Klik Filter | Berhasil data dashboard ditampilkan sesuai filter. | Berhasil data dashboard ditampilkan sesuai filter. | P |  |
| 29.3 | Mereset filter Dashboard Absent | Buka panel Filter - Klik Reset | Berhasil mereset seluruh filter ke nilai default. | Berhasil mereset seluruh filter ke nilai default. | P |  |
| 29.4 | Melihat detail daftar absensi Kantor Wilayah | Klik salah satu card Kantor Wilayah | Berhasil Melihat detail daftar absensi Kantor Wilayah. | Berhasil Melihat detail daftar absensi Kantor Wilayah. | P |  |
| 29.5 | Mencari data pada detail Kantor Wilayah dengan keyword valid | Buka popup detail - Masukkan kata kunci pada field pencarian | Berhasil data ditampilkan sesuai kata kunci. | Berhasil data ditampilkan sesuai kata kunci. | P |  |
| 29.6 | Mencari data pada detail Kantor Wilayah dengan keyword tidak valid | Input keyword pencarian yang tidak valid pada tabel detail Kantor Wilayah - Klik Enter/Cari | Berhasil menampilkan tabel kosong atau pesan data tidak ditemukan. | Berhasil menampilkan tabel kosong atau pesan data tidak ditemukan. | P |  |

30. Modul Menu Absent - Daily Absent

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 30.1 | Membuka halaman Daily Absent | Klik menu Menu Absent - Klik sub menu Daily Absent | Berhasil menampilkan halaman Daily Absent. | Berhasil menampilkan halaman Daily Absent. | P |  |
| 30.2 | Menampilkan data berdasarkan status absent | Klik salah satu tab status absent | Berhasil menampilkan data sesuai status absent yang dipilih. | Berhasil menampilkan data sesuai status absent yang dipilih. | P |  |
| 30.3 | Melakukan filter Daily Absent | Klik Filter - Pilih filter - Klik Filter | Berhasil menampilkan data sesuai filter. | Berhasil menampilkan data sesuai filter. | P |  |
| 30.4 | Mereset filter | Klik Reset | Berhasil mengembalikan filter ke nilai default. | Berhasil mengembalikan filter ke nilai default. | P |  |
| 30.5 | Mengubah status absensi | Klik dropdown Status - Pilih status | Berhasil mengubah status absensi. | Berhasil mengubah status absensi. | P |  |
| 30.6 | Melihat Note Clock In | Klik ikon Note Clock In | Berhasil menampilkan Note Clock In. | Berhasil menampilkan Note Clock In. | P |  |
| 30.7 | Melihat Attachment Clock In | Klik ikon Attachment Clock In | Berhasil menampilkan Attachment Clock In. | Berhasil menampilkan Attachment Clock In. | P |  |
| 30.8 | Melihat Lokasi Clock In | Klik ikon Lokasi Clock In | Berhasil menampilkan lokasi Clock In. | Berhasil menampilkan lokasi Clock In. | P |  |
| 30.9 | Melihat Note Clock Out | Klik ikon Note Clock Out | Berhasil menampilkan Note Clock Out. | Berhasil menampilkan Note Clock Out. | P |  |
| 30.10 | Melihat Attachment Clock Out | Klik ikon Attachment Clock Out | Berhasil menampilkan Attachment Clock Out. | Berhasil menampilkan Attachment Clock Out. | P |  |
| 30.11 | Melihat Lokasi Clock Out | Klik ikon Lokasi Clock Out | Berhasil menampilkan lokasi Clock Out. | Berhasil menampilkan lokasi Clock Out. | P |  |
| 30.12 | Membuka Settings | Klik Settings | Berhasil membuka Settings. | Berhasil membuka Settings. | P |  |
| 30.13 | Mencari data pada Settings | Input keyword - Klik Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 30.14 | Mencari data Settings dengan keyword tidak valid | Input keyword tidak valid - Klik Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 30.15 | Mengubah status Requires Approval | Buka Settings - Klik toggle Requires Approval | Berhasil mengubah status Requires Approval. | Berhasil mengubah status Requires Approval. | P |  |
| 30.16 | Mengekspor data Daily Absent | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

31. Modul Menu Absent - Rekap Absent

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 31.1 | Membuka halaman Rekap Absent | Klik menu Menu Absent - Klik sub menu Rekap Absent | Berhasil menampilkan halaman Rekap Absent. | Berhasil menampilkan halaman Rekap Absent. | P |  |
| 31.2 | Mencari data rekap absent dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 31.3 | Mencari data rekap absent dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 31.4 | Melakukan filter rekap absent | Pilih filter - Klik button Filter | Berhasil menampilkan data sesuai filter. | Berhasil menampilkan data sesuai filter. | P |  |
| 31.5 | Mereset filter rekap absent | Klik button Reset Filter | Berhasil mengembalikan filter ke nilai default. | Berhasil mengembalikan filter ke nilai default. | P |  |
| 31.6 | Mengekspor data rekap absent | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

32. Modul Menu Absent - Approval Absent

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 32.1 | Membuka halaman Approval Absent | Klik menu Menu Absent - Klik sub menu Approval Absent | Berhasil menampilkan halaman Approval Absent. | Berhasil menampilkan halaman Approval Absent. | P |  |
| 32.2 | Mencari data dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 32.3 | Mencari data dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 32.4 | Melakukan filter approval absent | Pilih filter - Klik button Filter | Berhasil menampilkan data sesuai filter. | Berhasil menampilkan data sesuai filter. | P |  |
| 32.5 | Melihat Attendance detail | Klik nama Sales | Berhasil menampilkan Attendance Detail. | Berhasil menampilkan Attendance Detail. | P |  |
| 32.6 | Melihat Note | Klik icon Note | Berhasil menampilkan Note. | Berhasil menampilkan Note. | P |  |
| 32.7 | Melihat Attachment | Klik icon Attachment | Berhasil menampilkan Attachment. | Berhasil menampilkan Attachment. | P |  |
| 32.8 | Melihat Lokasi | Klik icon Lokasi | Berhasil menampilkan lokasi pada peta. | Berhasil menampilkan lokasi pada peta. | P |  |
| 32.9 | Menyetujui approval absent | Klik button Approve - Isi Comments - Klik button Approve | Berhasil mengubah status menjadi Approved. | Berhasil mengubah status menjadi Approved. | P |  |
| 32.10 | Menyetujui approval absent tanpa mengisi Comments | Klik button Approve - Kosongkan Comments - Klik button Approve | Muncul validasi Comments wajib diisi. | Berhasil Muncul validasi Comments wajib diisi. | P |  |
| 32.11 | Menolak approval absent | Klik button Reject - Isi Comments - Klik button Reject | Berhasil mengubah status menjadi Rejected. | Berhasil mengubah status menjadi Rejected. | P |  |
| 32.12 | Menolak approval absent tanpa mengisi Comments | Klik button Reject - Kosongkan Comments - Klik button Reject | Muncul validasi Comments wajib diisi. | Berhasil Muncul validasi Comments wajib diisi. | P |  |
| 32.13 | Membatalkan approval yang sudah disetujui | Klik button Cancel Approval - Klik Yes | Berhasil status kembali menjadi Pending. | Berhasil status kembali menjadi Pending. | P |  |
| 32.14 | Membatalkan approval yang sudah di reject | Klik button Cancel Approval pada data yang berstatus Rejected - Klik Yes pada pop up konfirmasi | Berhasil membatalkan status Rejected dan status approval kembali menjadi Pending. | Berhasil membatalkan status Rejected dan status approval kembali menjadi Pending. | P |  |
| 32.15 | Mengekspor data approval absent | Klik button Export - Klik icon Mendownload pada panel Mendownload Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

33. Modul Sales Tracking Activity - Dashboard Visit

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 33.1 | Membuka halaman Dashboard Visit | Klik menu Sales Tracking Activity - Klik sub menu Dashboard Visit | Berhasil membuka halaman Dashboard Visit. | Berhasil membuka halaman Dashboard Visit. | P |  |
| 33.2 | Melakukan filter data Dashboard Visit | Klik button Filter - Input data pada field filter - Klik button Filter pada popup | Berhasil melakukan filter data Dashboard Visit. | Berhasil melakukan filter data Dashboard Visit. | P |  |
| 33.3 | Melakukan filter data Dashboard Visit dengan data yang tidak ada | Klik button Filter - Input data yang tidak ada pada field filter - Klik button Filter pada popup | Data tidak ditemukan. | Berhasil Data tidak ditemukan. | P |  |
| 33.4 | Mereset filter Dashboard Visit | Klik button Filter - Klik button Reset | Berhasil mereset filter Dashboard Visit. | Berhasil mereset filter Dashboard Visit. | P |  |
| 33.5 | Melihat detail cabang | Klik icon panah pada card cabang | Berhasil menampilkan popup detail cabang. | Berhasil menampilkan popup detail cabang. | P |  |
| 33.6 | Mencari data detail cabang dengan keyword valid | Klik icon panah pada card cabang - Input keyword valid pada field Search - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 33.7 | Mencari data detail cabang dengan keyword tidak valid | Klik icon panah pada card cabang - Input keyword tidak valid pada field Search - Klik button Search | Data tidak ditemukan. | Berhasil Data tidak ditemukan. | P |  |
| 33.8 | Mengekspor data detail cabang | Klik icon panah pada card cabang - Klik button Export Data | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

34. Modul Sales Tracking Activity - Client Visit List

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 34.1 | Membuka halaman Client Visit List | Klik menu Sales Tracking Activity - Klik sub menu Client Visit List | Berhasil membuka sub menu Client Visit List. | Berhasil membuka sub menu Client Visit List. | P |  |
| 34.2 | Menampilkan daftar data Client Visit List | Klik menu Sales Tracking Activity - Klik sub menu Client Visit List | Berhasil menampilkan daftar data Client Visit List beserta informasi Total Visit. | Berhasil menampilkan daftar data Client Visit List beserta informasi Total Visit. | P |  |
| 34.3 | Memvalidasi pembaruan data Total Visit setelah menerapkan filter | Klik button Filter - Pilih salah satu parameter filter (misal: Sales) - Klik button Filter (Terapkan) - Periksa kesesuaian angka pada card Total Visit dengan jumlah data yang terfilter | Angka pada card Total Visit ter-update secara otomatis sesuai dengan jumlah baris data hasil filter. | Berhasil Angka pada card Total Visit ter-update secara otomatis sesuai dengan jumlah baris data hasil filter. | P |  |
| 34.4 | Mencari data Client Visit List dengan keyword valid | Input keyword valid pada field Cari Data - Klik button Cari | Berhasil menampilkan data sesuai pencarian. | Berhasil menampilkan data sesuai pencarian. | P |  |
| 34.5 | Mencari data Client Visit List dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data - Klik button Cari | Menampilkan data kosong. | Berhasil Menampilkan data kosong. | P |  |
| 34.6 | Melakukan filter data Client Visit List | Klik button Filter - Pilih parameter filter pada dropdown Kantor Wilayah, Kantor Cabang, Kantor Cabang Pembantu, Job Role, dan/atau Sales - Tentukan Date Range - Klik button Filter | Berhasil menampilkan data sesuai filter yang dipilih. | Berhasil menampilkan data sesuai filter yang dipilih. | P |  |
| 34.7 | Mereset filter data Client Visit List | Klik button Filter - Klik button Reset | Berhasil mereset seluruh parameter filter dan menampilkan seluruh data. | Berhasil mereset seluruh parameter filter dan menampilkan seluruh data. | P |  |
| 34.8 | Melihat detail profil Sales Name | Klik nama Sales pada kolom Sales Name | Berhasil membuka halaman detail profil Sales. | Berhasil membuka halaman detail profil Sales. | P |  |
| 34.9 | Melihat lokasi Tag Location Visit In pada peta | Klik link Tag Location pada kolom Tag Location di bagian Visit In | Berhasil menampilkan popup peta Visit In Location beserta informasi Visit Activity dan Client Name. | Berhasil menampilkan popup peta Visit In Location beserta informasi Visit Activity dan Client Name. | P |  |
| 34.10 | Melihat lokasi Tag Location Visit Out pada peta | Klik link Tag Location pada kolom Tag Location di bagian Visit Out | Berhasil menampilkan popup peta Visit Out Location beserta informasi Visit Activity dan Client Name. | Berhasil menampilkan popup peta Visit Out Location beserta informasi Visit Activity dan Client Name. | P |  |
| 34.11 | Melihat detail aktivitas Visit In | Klik button Show Detail pada kolom Detail Visit di bagian Visit In | Berhasil menampilkan popup Activity Visit Detail yang berisi foto, Visit In Date & Time, Visit In Location, dan Visit In Description. | Berhasil menampilkan popup Activity Visit Detail yang berisi foto, Visit In Date & Time, Visit In Location, dan Visit In Description. | P |  |
| 34.12 | Melihat detail aktivitas Visit Out | Klik button Show Detail pada kolom Detail Visit di bagian Visit Out | Berhasil menampilkan popup Activity Visit Detail yang berisi foto, Visit Out Date & Time, Visit Out Location, dan Visit Out Description. | Berhasil menampilkan popup Activity Visit Detail yang berisi foto, Visit Out Date & Time, Visit Out Location, dan Visit Out Description. | P |  |
| 34.13 | Mengekspor data Client Visit List | Klik button Export Data | Berhasil mendownload file export data Client Visit List. | Berhasil mendownload file export data Client Visit List. | P |  |

35. Modul Sales Tracking Activity - Rekap Visit

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 35.1 | Membuka halaman Rekap Visit | Klik menu Sales Tracking Activity - Klik sub menu Rekap Visit | Berhasil membuka halaman Rekap Visit. | Berhasil membuka halaman Rekap Visit. | P |  |
| 35.2 | Menampilkan daftar data Rekap Visit | Klik menu Sales Tracking Activity - Klik sub menu Rekap Visit | Berhasil menampilkan daftar data Rekap Visit. | Berhasil menampilkan daftar data Rekap Visit. | P |  |
| 35.3 | Mencari data Rekap Visit dengan keyword valid | Input keyword valid pada field Search - Klik button Search | Berhasil menampilkan data Rekap Visit sesuai keyword. | Berhasil menampilkan data Rekap Visit sesuai keyword. | P |  |
| 35.4 | Mencari data Rekap Visit dengan keyword tidak valid | Input keyword tidak valid pada field Search - Klik button Search | Menampilkan pesan bahwa data tidak ditemukan. | Berhasil Menampilkan pesan bahwa data tidak ditemukan. | P |  |
| 35.5 | Melakukan filter data Rekap Visit | Pilih opsi pada field Filter - Klik button Filter | Berhasil menampilkan data Rekap Visit sesuai filter. | Berhasil menampilkan data Rekap Visit sesuai filter. | P |  |
| 35.6 | Mereset filter Rekap Visit | Klik button filter - Klik button Reset Filter | Berhasil mereset filter dan menampilkan seluruh data Rekap Visit. | Berhasil mereset filter dan menampilkan seluruh data Rekap Visit. | P |  |
| 35.7 | Mengekspor data Rekap Visit | Klik button Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

36. Modul Sales Tracking Activity - Rekap Monthly Visit

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 36.1 | Membuka halaman Rekap Monthly Visit | Klik menu Sales Tracking Activity - Klik sub menu Rekap Monthly Visit | Berhasil membuka halaman Rekap Monthly Visit. | Berhasil membuka halaman Rekap Monthly Visit. | P |  |
| 36.2 | Mencari data Rekap Monthly Visit dengan keyword valid | Input keyword valid pada field Cari Data - Klik button Search | Berhasil menampilkan data Rekap Monthly Visit sesuai keyword. | Berhasil menampilkan data Rekap Monthly Visit sesuai keyword. | P |  |
| 36.3 | Mencari data Rekap Monthly Visit dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data - Klik button Search | Menampilkan pesan bahwa data tidak ditemukan. | Berhasil Menampilkan pesan bahwa data tidak ditemukan. | P |  |
| 36.4 | Melakukan filter data Rekap Monthly Visit | Klik button Filter - Pilih opsi pada field filter yang tersedia - Klik button Filter pada panel | Berhasil menampilkan data Rekap Monthly Visit sesuai filter. | Berhasil menampilkan data Rekap Monthly Visit sesuai filter. | P |  |
| 36.5 | Mereset filter Rekap Monthly Visit | Klik button Filter - Klik button Reset | Berhasil mereset filter dan menampilkan seluruh data Rekap Monthly Visit. | Berhasil mereset filter dan menampilkan seluruh data Rekap Monthly Visit. | P |  |
| 36.6 | Mengekspor data Rekap Monthly Visit | Klik button Export Data - Klik icon Download Export pada navigasi atas - Klik icon Download pada file export yang sesuai | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

37. Modul Setting Absent - Attendance Spot

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 37.1 | Membuka halaman Attendance Spot | Klik menu Setting Absent - Klik sub menu Attendance Spot | Berhasil menampilkan halaman Attendance Spot. | Berhasil menampilkan halaman Attendance Spot. | P |  |
| 37.2 | Mencari data Attendance Spot dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 37.3 | Mencari data Attendance Spot dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 37.4 | Menambahkan data Attendance Spot | Klik button Add New Location - Input seluruh field mandatory - Klik button Submit | Berhasil menyimpan data Attendance Spot. | Berhasil menyimpan data Attendance Spot. | P |  |
| 37.5 | Menambahkan data Attendance Spot tanpa mengisi field mandatory | Klik button Add New Location - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 37.6 | Mencari lokasi spesifik melalui pencarian peta dengan keyword valid | Klik button Add New Location - Input nama lokasi pada field pencarian peta - Pilih lokasi dari hasil pencarian | Berhasil peta berhasil menampilkan titik lokasi yang dipilih. | Berhasil peta berhasil menampilkan titik lokasi yang dipilih. | P |  |
| 37.7 | Mencari lokasi spesifik melalui pencarian peta dengan keyword tidak valid | Input nama lokasi/keyword yang tidak valid pada pencarian peta - Klik Enter/Cari | Peta tidak menemukan lokasi yang dimaksud (menampilkan pesan tidak ditemukan). | Berhasil Peta tidak menemukan lokasi yang dimaksud (menampilkan pesan tidak ditemukan). | P |  |
| 37.8 | Mengubah data Attendance Spot | Klik icon Edit pada salah satu data Attendance Spot - Ubah data pada field mandatory - Klik button Submit | Berhasil menyimpan perubahan data Attendance Spot. | Berhasil menyimpan perubahan data Attendance Spot. | P |  |
| 37.9 | Mengubah data Attendance Spot tanpa mengisi field mandatory | Klik icon Edit pada salah satu data Attendance Spot - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 37.10 | Melihat detail lokasi pada peta | Klik icon View Map pada salah satu data Attendance Spot | Berhasil menampilkan popup peta lokasi Attendance Spot. | Berhasil menampilkan popup peta lokasi Attendance Spot. | P |  |
| 37.11 | Menghapus data Attendance Spot | Klik icon Delete pada salah satu data Attendance Spot - Klik button OK pada popup konfirmasi | Berhasil menghapus data Attendance Spot. | Berhasil menghapus data Attendance Spot. | P |  |
| 37.12 | Membuka halaman Setting Attendance Spot Personnel | Klik icon Setting Attendance Spot Personnel pada salah satu data Attendance Spot | Berhasil menampilkan halaman Setting Attendance Spot Personnel. | Berhasil menampilkan halaman Setting Attendance Spot Personnel. | P |  |
| 37.13 | Melakukan filter data Personnel | Pilih data pada salah satu dropdown filter (Kantor Wilayah, Kantor Cabang, dll) - Klik button Filter | Berhasil menampilkan data Personnel sesuai filter yang dipilih. | Berhasil menampilkan data Personnel sesuai filter yang dipilih. | P |  |
| 37.14 | Mencari data Personnel dengan keyword valid | Input keyword pada field Search di halaman Personnel - Klik button Search | Berhasil menampilkan data Personnel sesuai keyword. | Berhasil menampilkan data Personnel sesuai keyword. | P |  |
| 37.15 | Mencari data Personnel dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search di halaman Personnel - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 37.16 | Menambahkan data Personnel secara single | Klik checkbox pada salah satu data Personnel yang berstatus Tidak Aktif - Klik toggle Status pada data Personnel tersebut | Berhasil mencentang checkbox data Personnel. - Berhasil menambahkan/mengaktifkan personnel ke Attendance Spot secara single. | Berhasil mencentang checkbox data Personnel. - Berhasil menambahkan/mengaktifkan personnel ke Attendance Spot secara single. | P |  |
| 37.17 | Menghapus data Personnel secara single | Klik checkbox pada salah satu data Personnel yang berstatus Aktif - Klik toggle Status pada data Personnel tersebut | Berhasil mencentang checkbox data Personnel. - Berhasil menghapus/menonaktifkan personnel dari Attendance Spot secara single. | Berhasil mencentang checkbox data Personnel. - Berhasil menghapus/menonaktifkan personnel dari Attendance Spot secara single. | P |  |
| 37.18 | Menambahkan data Personnel secara bulk (Add Personnel) | Klik beberapa checkbox data Personnel yang berstatus Tidak Aktif - Klik button Add Personnel | Berhasil mencentang beberapa checkbox data Personnel. - Berhasil menambahkan/mengaktifkan seluruh personnel yang dipilih ke Attendance Spot secara bulk. | Berhasil mencentang beberapa checkbox data Personnel. - Berhasil menambahkan/mengaktifkan seluruh personnel yang dipilih ke Attendance Spot secara bulk. | P |  |
| 37.19 | Menghapus data Personnel secara bulk (Remove Personnel) | Klik beberapa checkbox data Personnel yang berstatus Aktif - Klik button Remove Personnel | Berhasil mencentang beberapa checkbox data Personnel. - Berhasil menghapus/menonaktifkan seluruh personnel yang dipilih dari Attendance Spot secara bulk. | Berhasil mencentang beberapa checkbox data Personnel. - Berhasil menghapus/menonaktifkan seluruh personnel yang dipilih dari Attendance Spot secara bulk. | P |  |

38. Modul Setting Absent - Work Pattern

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 38.1 | Membuka halaman Work Pattern | Klik menu Setting Absent - Klik sub menu Work Pattern | Berhasil menampilkan halaman Work Pattern. | Berhasil menampilkan halaman Work Pattern. | P |  |
| 38.2 | Mencari data Work Pattern dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 38.3 | Mencari data Work Pattern dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 38.4 | Menambahkan data Work Pattern | Klik button Add Work Pattern - Input seluruh field mandatory - Klik button Submit | Berhasil menyimpan data Work Pattern. | Berhasil menyimpan data Work Pattern. | P |  |
| 38.5 | Menambahkan data Work Pattern tanpa mengisi field mandatory | Klik button Add Work Pattern - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 38.6 | Menerapkan jadwal ke beberapa hari secara sekaligus (Terapkan ke Semua) | Klik button Add Work Pattern - Isi status, Clock In, dan Clock Out pada header Set Working Schedule - Centang beberapa checkbox hari - Klik button Terapkan ke Semua | Berhasil menerapkan jadwal yang diinput ke seluruh hari yang dicentang secara bersamaan. | Berhasil menerapkan jadwal yang diinput ke seluruh hari yang dicentang secara bersamaan. | P |  |
| 38.7 | Mereset jadwal pada beberapa hari secara sekaligus (Reset) | Klik button Add Work Pattern - Centang beberapa checkbox hari pada Set Working Schedule - Klik button Reset | Berhasil mengosongkan kembali (reset) jadwal pada seluruh hari yang dicentang secara bersamaan. | Berhasil mengosongkan kembali (reset) jadwal pada seluruh hari yang dicentang secara bersamaan. | P |  |
| 38.8 | Mengubah data Work Pattern | Klik icon Edit pada salah satu data Work Pattern - Ubah data pada field mandatory - Klik button Submit | Berhasil menyimpan perubahan data Work Pattern. | Berhasil menyimpan perubahan data Work Pattern. | P |  |
| 38.9 | Mengubah data Work Pattern tanpa mengisi field mandatory | Klik icon Edit pada salah satu data Work Pattern - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 38.10 | Melihat detail Work Pattern | Klik icon Detail (i) pada salah satu data Work Pattern | Berhasil menampilkan popup Work Pattern Details yang berisi jadwal kerja. | Berhasil menampilkan popup Work Pattern Details yang berisi jadwal kerja. | P |  |
| 38.11 | Menghapus data Work Pattern | Klik icon Delete pada salah satu data Work Pattern - Klik button OK pada popup konfirmasi | Berhasil menghapus data Work Pattern. | Berhasil menghapus data Work Pattern. | P |  |
| 38.12 | Membuka halaman Setting Work Pattern Personnel | Klik icon Setting Work Pattern Personnel pada salah satu data Work Pattern | Berhasil menampilkan halaman Setting Work Pattern Personnel. | Berhasil menampilkan halaman Setting Work Pattern Personnel. | P |  |
| 38.13 | Melakukan filter data Personnel | Pilih data pada salah satu dropdown filter (Kantor Wilayah, Kantor Cabang, dll) - Klik button Filter | Berhasil memilih data filter. - Berhasil menampilkan data Personnel sesuai filter yang dipilih. | Berhasil memilih data filter. - Berhasil menampilkan data Personnel sesuai filter yang dipilih. | P |  |
| 38.14 | Mencari data Personnel dengan keyword valid | Input keyword pada field Search di halaman Personnel - Klik button Search | Berhasil menginput keyword. - Berhasil menampilkan data Personnel sesuai keyword. | Berhasil menginput keyword. - Berhasil menampilkan data Personnel sesuai keyword. | P |  |
| 38.15 | Mencari data Personnel dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search di halaman Personnel - Klik button Search | Berhasil menginput keyword. - Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menginput keyword. - Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 38.16 | Meng-assign data Personnel ke Work Pattern secara single | Klik checkbox pada salah satu data Personnel - Klik icon Assign | Berhasil meng-assign personnel tersebut ke Work Pattern. | Berhasil meng-assign personnel tersebut ke Work Pattern. | P |  |
| 38.17 | Meng-assign data Personnel ke Work Pattern secara bulk | Klik beberapa checkbox data Personnel - Klik icon Assign | Berhasil meng-assign seluruh personnel yang dipilih secara bulk ke Work Pattern. | Berhasil meng-assign seluruh personnel yang dipilih secara bulk ke Work Pattern. | P |  |
| 38.18 | Meng-unassign data Personnel dari Work Pattern secara single | Klik checkbox pada salah satu data Personnel yang sudah ter-assign - Klik icon Unassign (merah) | Berhasil mencentang checkbox data Personnel. - Berhasil menghapus (unassign) personnel tersebut dari Work Pattern. | Berhasil mencentang checkbox data Personnel. - Berhasil menghapus (unassign) personnel tersebut dari Work Pattern. | P |  |
| 38.19 | Meng-unassign data Personnel dari Work Pattern secara bulk | Klik beberapa checkbox data Personnel yang sudah ter-assign - Klik icon Unassign (merah) | Berhasil mencentang beberapa checkbox data Personnel. - Berhasil menghapus (unassign) seluruh personnel yang dipilih secara bulk dari Work Pattern. | Berhasil mencentang beberapa checkbox data Personnel. - Berhasil menghapus (unassign) seluruh personnel yang dipilih secara bulk dari Work Pattern. | P |  |

39. Modul Setting Absent - Holiday

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 39.1 | Membuka halaman Holiday | Klik menu Setting Absent - Klik sub menu Holiday | Berhasil menampilkan halaman Holiday. | Berhasil menampilkan halaman Holiday. | P |  |
| 39.2 | Mencari data Holiday dengan keyword valid | Input keyword pada field Search - Klik button Search | Berhasil menampilkan data sesuai keyword. | Berhasil menampilkan data sesuai keyword. | P |  |
| 39.3 | Mencari data Holiday dengan keyword tidak valid | Input keyword yang tidak terdaftar pada field Search - Klik button Search | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 39.4 | Menambahkan data Holiday | Klik button Add New Holiday - Input seluruh field mandatory (Name, Start Date, End Date) - Klik button Submit | Berhasil menyimpan data Holiday. | Berhasil menyimpan data Holiday. | P |  |
| 39.5 | Menambahkan data Holiday tanpa mengisi field mandatory | Klik button Add New Holiday - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 39.6 | Mengubah data Holiday | Klik icon Edit pada salah satu data Holiday - Ubah data pada field mandatory - Klik button Submit | Berhasil menyimpan perubahan data Holiday. | Berhasil menyimpan perubahan data Holiday. | P |  |
| 39.7 | Mengubah data Holiday tanpa mengisi field mandatory | Klik icon Edit pada salah satu data Holiday - Kosongkan field mandatory - Klik button Submit | Berhasil menampilkan validasi field mandatory wajib diisi. | Berhasil menampilkan validasi field mandatory wajib diisi. | P |  |
| 39.8 | Menghapus data Holiday | Klik icon Delete pada salah satu data Holiday - Klik button OK pada popup konfirmasi | Berhasil menghapus data Holiday. | Berhasil menghapus data Holiday. | P |  |

40. Modul Sales Force - Sales code

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 40.1 | Membuka menu sales code | Klik menu sales force - Klik submenu sales code | Menampilkan halaman sales code | Berhasil Menampilkan halaman sales code | P |  |
| 40.2 | Melakukan filter data | Filter data dengan pilih kantor wilayah, kantor cabang, cabang pembantu, dan jobrole kemudian klik button filter data | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 40.3 | Melakukan filter dengan tidak mengisi filter mandatory (Negative case) | Filter data dengan tidak mengisi filter mandatory | Menampilkan alert "filter mandatory dibutuhkan" | Berhasil Menampilkan alert "filter mandatory dibutuhkan" | P |  |
| 40.4 | Menambahkan sales code | Klik button create kemudian kllik create sales code - Pilih jobrole dan kantor cabang - klik add sales code - Klik button submit | berhasil menambahkan sales code | berhasil menambahkan sales code | P |  |
| 40.5 | Menambahkan sales people | Klik button create kemudian klik input sales poeple - input nip kemudian klik button cari nip - Pilih sales code sesuai dengan jobrole dan kantor cabang nip yang diinput - klik button submit | Berhasil menginput sales people | Berhasil menginput sales people | P |  |
| 40.6 | menambahkan sales people dengan nip yang tidak ada (Negative case) | Klik button create kemudian klik input sales poeple - input nip yang tidak sesuai kemudian klik button cari nip | Menampilkan alert "Nip tidak ditemukan" | Berhasil Menampilkan alert "Nip tidak ditemukan" | P |  |
| 40.7 | Menambahkan sales code dan sales people secara bersamaan | Klik button create kemudian klik create sales code and input sales people - Pilih jobrole dan kantor cabang - Pilih nip - klik button submit | Berhasil create salescode dan input nip | Berhasil create salescode dan input nip | P |  |
| 40.8 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 40.9 | Mencari data kata kunci yang tidak sesuai (Negative test) | Input data yang tidak sesuai | Data tidak ditemukan | Berhasil Data tidak ditemukan | P |  |
| 40.10 | Menghapus sales people | Klik icon titik tiga (opsi) pada data yang terdapat nip pada tabel - klik remove sales people - Klik button ok | berhasil menghapus/ melepaskan nip dari sales code | berhasil menghapus/ melepaskan nip dari sales code | P |  |
| 40.11 | Menghapus sales code | Klik icon titik tiga (opsi) - klik delete - Klik button ok | berhasil menghapus data sales code | berhasil menghapus data sales code | P |  |
| 40.12 | Melihat detail | Klik icon titik tiga (opsi) - klik detail | Menampilkan detail data sales code | Berhasil Menampilkan detail data sales code | P |  |
| 40.13 | Mengubah sales people | Klik icon titik tiga (opsi) - klik detail - kemudian klik buttonn update - input nip kemudian klik buttonn cari nip - klik button update | Berhasil update data sales people | Berhasil update data sales people | P |  |
| 40.14 | mengunduh data sales code | Klik button export | Berhasil mengunduh data sales code | Berhasil mengunduh data sales code | P |  |
| 40.15 | Membuka tab sales code assign | Klik tab sales code not assign | Menampilkan list data sales code yang belum memiliki sales people | Berhasil Menampilkan list data sales code yang belum memiliki sales people | P |  |
| 40.16 | Membuka tab sales code not assign | Klik tab sales code assign | Menampilkan list data sales code yang sudah memiliki sales people | Berhasil Menampilkan list data sales code yang sudah memiliki sales people | P |  |
| 40.17 | Membuka tab sales people not assign | Klik tab sales people not assign | Menampilkan list data sales yang belum memiliki sales code | Berhasil Menampilkan list data sales yang belum memiliki sales code | P |  |

41. Modul Sales Force - Pipeline - Dashboard Validate Pipeline

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 41.1 | Membuka menu dashboard validate pipeline | Klik menu Sales force - Klik Submenu Pipeline - Klik submenu Dashboard Validate Pipeline | Menampilkan halaman Dashboard Validate Pipeline | Berhasil Menampilkan halaman Dashboard Validate Pipeline | P |  |
| 41.2 | Melakukan filter data | Klik filter bulan kemudian pilih bulan | Menampilkan data sesuai dengan bulan yang dipilih | Berhasil Menampilkan data sesuai dengan bulan yang dipilih | P |  |
| 41.3 | Melakukan filter data | Klik button filter – pilih kantor wilayah, kantor cabang, cabang pembantu – kemudian klik apply | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 41.4 | Membuka detail Chart total pipeline DPK | Klik icon (Tanda Panah) pada Chart pipeline data kantor cabang | Menampilkan halaman detail pipeline data kantor cabang | Berhasil Menampilkan halaman detail pipeline data kantor cabang | P |  |
| 41.5 | Mencari data pada kolom pencarian | Input kata kunci pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 41.6 | Membuka detail list pipeline DPK | Klik button detail pada chart pipeline DPK | Menampilkan halaman detail Validate pipeline DPK | Berhasil Menampilkan halaman detail Validate pipeline DPK | P |  |
| 41.7 | Membuka detail Chart pipeline data kantor cabang | Klik icon (Tanda Panah) pada Chart pipeline data kantor cabang | Menampilkan halaman detail pipeline data kantor cabang | Berhasil Menampilkan halaman detail pipeline data kantor cabang | P |  |
| 41.8 | Mencari data pada kolom pencarian | Input kata kunci pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 41.9 | Membuka detail list pipeline kantor cabang | Klik button detail pada chart pipeline kantor cabang | Menampilkan halaman detail Validate pipeline kantor cabang | Berhasil Menampilkan halaman detail Validate pipeline kantor cabang | P |  |
| 41.10 | Membuka detail Chart Sales Input Pipeline | Klik icon (Tanda Panah) pada chart Sales Input Pipeline | Menampilkan halaman detail Sales Input Pipeline | Berhasil Menampilkan halaman detail Sales Input Pipeline | P |  |
| 41.11 | Mencari data pada kolom pencarian | Input kata kunci pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 41.12 | Membuka detail list Sales Input Pipeline | Klik button detail pada chart Sales Input Pipeline | Menampilkan halaman detail Validate pipeline Sales Input Pipeline | Berhasil Menampilkan halaman detail Validate pipeline Sales Input Pipeline | P |  |
| 41.13 | Membuka detail Chart Pipeline Category | Klik icon (Tanda Panah) pada chart Pipeline Category | Menampilkan halaman detail Pipeline Category | Berhasil Menampilkan halaman detail Pipeline Category | P |  |
| 41.14 | Mencari data pada kolom pencarian | Input kata kunci pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 41.15 | Membuka detail list Pipeline Category | Klik button detail pada chart Pipeline Category | Menampilkan halaman detail Validate Pipeline Category | Berhasil Menampilkan halaman detail Validate Pipeline Category | P |  |
| 41.16 | List validate Pipeline - mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 41.17 | Membuka detail list validate pipeline | Klik icon (Tanda Panah) pada list validate pipeline | Menampilkan halaman detail validate pipeline | Berhasil Menampilkan halaman detail validate pipeline | P |  |
| 41.18 | Detail Validate Pipeline - Melakukan Filter data | Pilih kontor wilayah, kantor cabang, cabang pembantu, sales, job role, jenis Lembaga kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 41.19 | Detail Validate pipeline - mengunduh data validate pipeline | Klik button export data | Berhasil mengunduh data | Berhasil mengunduh data | P |  |
| 41.20 | Melakukan Validate data menggunakan user BM | Login menggunakan user BM - Masuk ke menu dashboard validate pipeline halaman detail validate - Pilih data dengan klik checkbox pada table - klik button validate - klik ok | Berhasil melakukan validate pipeline dan data akan tampil pada user RO Head | Berhasil melakukan validate pipeline dan data akan tampil pada user RO Head | P |  |
| 41.21 | Melakukan validate all data menggunakan user BM | Klik button validate all data - Klik ok | Berhasil melakukan validate data secara bersamaan dan data akan tampil pada user RO Head | Berhasil melakukan validate data secara bersamaan dan data akan tampil pada user RO Head | P |  |
| 41.22 | Melakukan unvalidate data menggunakan user BM | Klik Manage pada data yang sudah di validate - Klik button unvalidate - input reason kemudian klik button submit | Berhasil unvalidate pipeline | Berhasil unvalidate pipeline | P |  |
| 41.23 | Melakukan Validate data menggunakan user RO Head | Login menggunakan user RO Head - Masuk ke menu dashboard validate pipeline halaman detail validate - Pilih data dengan klik checkbox pada table - klik button validate - klik ok | Berhasil melakukan validate pipeline | Berhasil melakukan validate pipeline | P |  |
| 41.24 | Melakukan validate all data menggunakan user RO Head | Klik button validate all data - Klik ok | Berhasil melakukan validate data secara bersamaan | Berhasil melakukan validate data secara bersamaan | P |  |
| 41.25 | Melakukan unvalidate data menggunakan user RO Head | Klik Manage pada data yang sudah di validate - Klik button unvalidate - input reason kemudian klik button submit | Berhasil unvalidate pipeline | Berhasil unvalidate pipeline | P |  |

42. Modul Sales Force - Pipeline - Input Pipeline

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 42.1 | Membuka menu input Pipeline | Klik menu Sales Force - Klik Submenu Pipeline - Klik submenu Input Pipeline | Menampilkan halaman Input pipeline | Berhasil Menampilkan halaman Input pipeline | P |  |
| 42.2 | Melakukan filter data | Pilih tahun, bulan, type dan status – kemudian klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 42.3 | Melakukan filter data dengan tidak menginput filter mandatory (Negative test) | kosong kan salah satu fllter mandatory kemudian klik button filter | Menampilkan alert filter dibutuhkan | Berhasil Menampilkan alert filter dibutuhkan | P |  |
| 42.4 | Menambahkan data pipeline NTB | Klik button +add pipeline NTB - input data dengan mengisi (nama nasabah, apakah nasabah ini nasabah lembaga?, produk, segment, potensi, tanggal komitmen masuk, profile nasabah, sumber dana, dan sektor masuk) - kemudian klik button submit pipeline | Pipeline berhasil di submit | Berhasil Pipeline berhasil di submit | P |  |
| 42.5 | Menambahkan data pipeline NTB tidak menginput data mandatory (Negative test) | Klik button +add pipeline NTB - kosong kan salah satu field mandatory kemudian klik button submit pipeline | Menampilkan alert data dibutuhkan | Berhasil Menampilkan alert data dibutuhkan | P |  |
| 42.6 | Menambahkan data pipeline ETB | Klik button +add pipeline NTB - input cif dan nomor rekening kemudian klik button check cif - kemudian input data dengan mengisi (Apakah nasabah ini nasabah lembaga?, produk, segment, potensi, tanggal komitmen masuk, profile nasabah, sumber dana, dan sektor masuk) - klik button submit pipeline | Pipeline berhasil di submit | Berhasil Pipeline berhasil di submit | P |  |
| 42.7 | Menambahkan data ETB dengan menginput nomor cif tidak sesuai (Negative Test) | Klik button +add pipeline NTB - input cif yang tidak sesuai kemudian klik button check cif | Menampilkan alert cif & no rekening tidak di temukan | Berhasil Menampilkan alert cif & no rekening tidak di temukan | P |  |
| 42.8 | Menambahkan data ETB dengan menginput nomor no rekening tidak sesuai (Negative test) | Klik button +add pipeline NTB - input nomor rekening yang tidak sesuai kemudian klik button check cif | Menampilkan alert cif & no rekening tidak di temukan | Berhasil Menampilkan alert cif & no rekening tidak di temukan | P |  |
| 42.9 | Melihat detail pipeline | Klik icon titik tiga - klik action detail | Menampilkan detail pipeline | Berhasil Menampilkan detail pipeline | P |  |
| 42.10 | Mengubah tanggal potensi | Klik icon titik tiga - klik action edit tanggal - ubah tanggal kemudian klik button simpan perubahan | Berhasil mengubah tanggal potensi | Berhasil mengubah tanggal potensi | P |  |
| 42.11 | Melihat potensi perubahan tanggal | Klik icon titik tiga - klik action history perubahan tanggal | Menampilkan list data perubahan tanggal potensi | Berhasil Menampilkan list data perubahan tanggal potensi | P |  |

43. Modul Sales Force - Approval Target Growth

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 43.1 | Melihat detail | Klik icon mata pada salah satu data Target Growth | Menampilkan detail data Approval Target Growth. | Berhasil menampilkan detail data Approval Target Growth. | P |  |
| 43.2 | Melakukan approval data | Klik icon ceklis pada table dengan status data pending request - input remark - klik button submit | Berhasil melakukan approval data Target Growth. | Berhasil melakukan approval data Target Growth. | P |  |
| 43.3 | Melakukan reject data | Klik icon silang pada table dengan status data pending request - input remark - Klik button submit | Berhasil melakukan reject data Target Growth. | Berhasil melakukan reject data Target Growth. | P |  |
| 43.4 | Membuka tab status ( pending request/approved/Rejected/expired) | Klik tab status ( pending request/approved/Rejected/ expired) | Menampilkan list data sesuai status yang dipilih. | Berhasil menampilkan list data sesuai status yang dipilih. | P |  |
| 43.5 | Melihat detail data | Klik icon mata pada salah satu data Target Growth | Menampilkan detail data. | Berhasil menampilkan detail data. | P |  |
| 43.6 | Melakukan approval data | Klik icon ceklis pada table dengan status data pending request - input remark - klik button submit | Berhasil melakukan approval data Target Growth. | Berhasil melakukan approval data Target Growth. | P |  |
| 43.7 | Melakukan reject data | Klik icon silang pada table dengan status data pending request - input remark - Klik button submit | Berhasil melakukan reject data Target Growth. | Berhasil melakukan reject data Target Growth. | P |  |
| 43.8 | Membuka tab status ( pending request/approved/Rejected/expired) | Klik tab status ( pending request/approved/Rejected/ expired) | Menampilkan list data sesuai status yang dipilih. | Berhasil menampilkan list data sesuai status yang dipilih. | P |  |

44. Modul Sales Force - Approval Sales Code

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 44.1 | Membuka menu approval sales code | Klik menu sales force - klik menu approval - Klik submenu Appoval sales code | Menampilkan halaman approval sales code | Berhasil Menampilkan halaman approval sales code | P |  |
| 44.2 | Melakukan filter data | Pilih bulan tahun dan tipe – kemudia klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 44.3 | Melakukan approval data | Klik icon ceklis pada table dengan status data pending request - input remark - klik button submit | Berhasil melakukan approval data sales code | Berhasil melakukan approval data sales code | P |  |
| 44.4 | Melakukan reject data | Klik icon silang pada table dengan status data pending request - input remark - KLik button submit | Berhasil melakukan reject data sales code | Berhasil melakukan reject data sales code | P |  |
| 44.5 | Membuka tab status ( pending request/approved/Rejected/expired) | Klik tab status ( pending request/approved/Rejected/ expired) | Menampilkan list data sesuai status yang dipilih | Berhasil Menampilkan list data sesuai status yang dipilih | P |  |
| 44.6 | Melihat detail data | Klik icon mata | Menampilkan detail data | Berhasil Menampilkan detail data | P |  |
| 44.7 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 44.8 | Mencari data kata kunci invalid | Input data yang belun terdaftar | Data tidak ditemukan | Berhasil Data tidak ditemukan | P |  |

45. Modul Sales Force - CIF Kelolaan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 45.1 | Membuka menu cif kelolaan | Klik menu sales force - Klik submenu CIf Kelolaan | Menampilkan halaman Cif Kelolaan | Berhasil Menampilkan halaman Cif Kelolaan | P |  |
| 45.2 | Melakukan filter data | ilih kantor cabang pembantu, subjab, sales code - kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 45.3 | Assign cif kelolaan | Klik button assign cif kelolaan - Klik button upload file - Download file template dengan klik download file template - Input data file template kemudian upload file template | Berhasil mengupload data Cif Kelolaan | Berhasil mengupload data Cif Kelolaan | P |  |
| 45.4 | Assign cif kelolaan menginput data template tidak sesuai (Negative test) | Klik button assign cif kelolaan - Klik button upload file - Download file template dengan klik download file template - Input data file template tidak sesuai dengan format kemudian upload file template | Data terupload dengan status failed | Berhasil Data terupload dengan status failed | P |  |
| 45.5 | Assign cif kelolaan - Download souce file | Klik icon titik tiga - Klik download sourch file | Berhasil mengunduh data source file | Berhasil mengunduh data source file | P |  |
| 45.6 | Assign cif kelolaan - preview data | Klik icon titik tiga - klik preview data | Menampilkan preview data hasil upload | Berhasil Menampilkan preview data hasil upload | P |  |
| 45.7 | Assign cif kelolaan - download error file | Klik icon titik tiga pada data yang berstatus failed - klik download error file | Berhasil mengunduh data error untuk mengetahui informasi letak error saat upload file template | Berhasil mengunduh data error untuk mengetahui informasi letak error saat upload file template | P |  |
| 45.8 | Mengunduh data cif kelolaan | Klik button export data | Berhasil mengunduh data cif kelolaan | Berhasil mengunduh data cif kelolaan | P |  |
| 45.9 | Menambahkan data cif kelolaan | Klik button input CIF - input data dengan mengisi (pilih scode, input cif dan remark) - klik button submit | Berhasil menambahkan data cif kelolaan | Berhasil menambahkan data cif kelolaan | P |  |
| 45.10 | Menambahkan data cif kelolaan dengan menginput format nip yang tidak sesuai (Negative test) | Klik button input CIF - pilih scode, input cif yang tidak sesuai format - klik button submit | Gagal menambahkan data cif kelolaan | Berhasil Gagal menambahkan data cif kelolaan | P |  |
| 45.11 | Menghapus data cif kelolaan | Pilih data cif kelolaan kemudian klik icon hapus | Menampilkan pop up konfirmasi hapus dan berhasil menghapus data cif kelolaan | Berhasil menghapus data cif kelolaan | P |  |
| 45.12 | Melakukan filter data | Pilih filter yang diinginkan kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 45.13 | Membuka tab status ( pending request/approved/Rejected/expired) | Klik tab status yang diinginkan (pending request/approved/Rejected/expired) | Menampilkan daftar data sesuai tab status yang dipilih | Berhasil Menampilkan daftar data sesuai tab status yang dipilih | P |  |
| 45.14 | Melihat detail data | Klik icon detail pada salah satu baris data | Menampilkan modal detail data cif kelolaan | Berhasil Menampilkan modal detail data cif kelolaan | P |  |
| 45.15 | Mencari data pada kolom pencarian | Masukkan kata kunci valid pada kolom pencarian kemudian tekan enter | Menampilkan data sesuai kata kunci pencarian | Berhasil Menampilkan data sesuai kata kunci pencarian | P |  |
| 45.16 | Mencari data kata kunci yang tidak sesuai | Masukkan kata kunci tidak valid pada kolom pencarian kemudian tekan enter | Menampilkan informasi data tidak ditemukan | Berhasil Menampilkan informasi data tidak ditemukan | P |  |

46. Modul Sales Force - Approval Cif Kelolaan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 46.1 | Membuka menu approval cif kelolaan | Klik menu sales force - klik menu approval - Klik submenu Appoval cif kelolaan | Menampilkan halaman approval cif kelolaan | Berhasil Menampilkan halaman approval cif kelolaan | P |  |
| 46.2 | Melakukan filter data | Pilih bulan tahun dan tipe – kemudia klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 46.3 | Melakukan approval data | Klik icon ceklis pada table dengan status data pending request - input remark - klik button submit | Berhasil melakukan approval data CIF Kelolaan | Berhasil melakukan approval data CIF Kelolaan | P |  |
| 46.4 | Melakukan reject data | Klik icon silang pada table dengan status data pending request - input remark - KLik button submit | Berhasil melakukan reject data CIF Kelolaan | Berhasil melakukan reject data CIF Kelolaan | P |  |
| 46.5 | Membuka tab status ( pending request/approved/Rejected/expired) | Klik tab status ( pending request/approved/Rejected/ expired) | Menampilkan list data sesuai status yang dipilih | Berhasil Menampilkan list data sesuai status yang dipilih | P |  |
| 46.6 | Melihat detail data | Klik icon mata | Menampilkan detail data | Berhasil Menampilkan detail data | P |  |
| 46.7 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 46.8 | Mencari data kata kunci yang tidak sesuai | Input data yang belun terdaftar | Data tidak ditemukan | Berhasil Data tidak ditemukan | P |  |

47. Modul Sales Force - Produktivitas - Target Growth

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 47.1 | Membuka menu Target Growth | Klik menu Sales Force - Klik submenu Produktivitas - Klik submenu Target Growth | Menampilkan halaman target growth | Berhasil Menampilkan halaman target growth | P |  |
| 47.2 | Import data Target growth | Klik button import data - Klik button upload file - Klik button download file template - Input template kemudian upload data template | Berhasil mengupload data target growth | Berhasil mengupload data target growth | P |  |
| 47.3 | Import data target growth dengan ngisi data template yang tidak sesuai (Negative Test) | Klik button import data - Klik button upload file - Klik button download file template - Input template dengan format yang salah kemudian upload data template | Data terupload dengan status validasi gagal | Berhasil Data terupload dengan status validasi gagal | P |  |
| 47.4 | Melakukan Import data tagert growth menggunakan user sales | Login menggunakan user sales - masuk ke halaman target growth - lakukan import data target growth | Berhasil mengupload data target growth dan data akan tampil pada menu approval target growth untuk di tindak lanjuti | Berhasil mengupload data target growth dan data akan tampil pada menu approval target growth untuk di tindak lanjuti | P |  |
| 47.5 | Mengunduh data target growth | Klik button export data | Berhasil mengunduh data target growth | Berhasil mengunduh data target growth | P |  |
| 47.6 | Melakukan Filter data | Pilih wilayah, cabang, cabang pembantu, subjab, sales code, dan tahun kemudian klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 47.7 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 47.8 | Mencari data kata kunci yang tidak sesuai | Input data yang belun terdaftar | Data tidak ditemukan | Berhasil Data tidak ditemukan | P |  |

48. Modul Sales Force - Produktivitas - Target Produktivitas

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 48.1 | Membuka menu Target Produktivitas | Klik menu Sales Force - Klik submenu Produktivitas - Klik submenu Target Produktivitas | Menampilkan halaman target produktivitas | Berhasil Menampilkan halaman target produktivitas | P |  |
| 48.2 | Import data Target Produktivitas | Klik button import data - Klik button upload file - Klik button download file template - Input template kemudian upload data template | Berhasil mengupload data target produktivitas | Berhasil mengupload data target produktivitas | P |  |
| 48.3 | Import data target produktivitas dengan mengisi data template yang tidak sesuai (Negative Test) | Klik button import data - Klik button upload file - Klik button download file template - Input template dengan format yang salah kemudian upload data template | Berhasil mengupload data target produktivitas | Berhasil mengupload data target produktivitas | P |  |
| 48.4 | Mengunduh data target produktivitas | Klik button export data | Berhasil mengunduh data target produktivitas | Berhasil mengunduh data target produktivitas | P |  |
| 48.5 | Melakukan filter data | Pilih wilayah, cabang, cabang pembantu, subjab, sales code, dan tahun kemudian klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 48.6 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 48.7 | Mencari data kata kunci yang tidak sesuai | Input data yang belun terdaftar | Data tidak ditemukan | Berhasil Data tidak ditemukan | P |  |

49. Modul Sales Force - Produktivitas - Bobot Produktivitas

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 49.1 | Membuka menu Bobot Produktivitas | Klik menu Sales Force - Klik submenu Produktivitas - Klik submenu Bobot Produktivitas | Menampilkan halaman bobot produktivitas | Berhasil Menampilkan halaman bobot produktivitas | P |  |
| 49.2 | Import data Bobot Produktivitas | Klik button import data - Klik button upload file - Klik button download file template - Input template kemudian upload data template | Berhasil mengupload data Bobot produktivitas | Berhasil mengupload data Bobot produktivitas | P |  |
| 49.3 | Import data Bobot Produktivitas dengan ngisi data template yang tidak sesuai (Negative Test) | Klik button import data - Klik button upload file - Klik button download file template - Input template dengan format yang salah kemudian upload data template | Data terupload dengan status failed | Berhasil Data terupload dengan status failed | P |  |
| 49.4 | Mengunduh data Bobot Produktivitas | Klik button export data | Berhasil mengunduh data Bobot Produktivitas | Berhasil mengunduh data Bobot Produktivitas | P |  |
| 49.5 | Melakukan filter data | Pilih wilayah, cabang, cabang pembantu, subjab, sales code, dan tahun kemudian klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 49.6 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 49.7 | Mencari data kata kunci yang tidak sesuai | Input data yang belun terdaftar | Data tidak ditemukan | Berhasil Data tidak ditemukan | P |  |

50. Modul Sales Force - Produktivitas - Realisasi Merchant

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 50.1 | Membuka menu realisasi merchant | Klik menu Sales Force - Klik submenu Produktivitas - Klik submenu Realisasi Merchant | Menampilkan halaman Realisasi Merchant | Berhasil Menampilkan halaman Realisasi Merchant | P |  |
| 50.2 | Import data realisasi merchant | Klik button import data - Klik button upload file - Klik button download file template - Input template kemudian upload data template | Berhasil mengupload data Realisasi Merchant | Berhasil mengupload data Realisasi Merchant | P |  |
| 50.3 | Import data realisasi merchant dengan ngisi data template yang tidak sesuai (Negative Test) | Klik button import data - Klik button upload file - Klik button download file template - Input template dengan format yang salah kemudian upload data template | Data terupload dengan status failed | Berhasil Data terupload dengan status failed | P |  |
| 50.4 | Mengunduh data realisasi merchant | Klik button export data | Berhasil mengunduh data Realisasi Merchant | Berhasil mengunduh data Realisasi Merchant | P |  |
| 50.5 | Melakukan filter data | Pilih wilayah, cabang, cabang pembantu, subjab, sales code, dan tahun kemudian klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 50.6 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 50.7 | Mencari data kata kunci yang tidak sesuai | Input data yang belun terdaftar | Data tidak ditemukan | Berhasil Data tidak ditemukan | P |  |

51. Modul Sales Force - CIF Rebase

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 51.1 | Membuka halaman CIF Rebase | Klik menu Sales Force - Klik submenu CIF Reabase | Menampilkan halaman cif rebase | Berhasil Menampilkan halaman cif rebase | P |  |
| 51.2 | Melakukan filter data | Pilih wilayah, cabang, cabang pembantu, subjab, sales code, dan tahun kemudian klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 51.3 | Melakukan rebase | Klik icon (Rebase cif) - input alasan - klik “OK” | Berhasil melakukan rebase cif | Berhasil melakukan rebase cif | P |  |
| 51.4 | Melakukan Archive | Klik icon (archive cif) - input alas an - klik “OK” | Data berhasil di arsipkan | Berhasil Data berhasil di arsipkan | P |  |
| 51.5 | Melihat tab CIF Rebase History | Klik tab cif rebase history | Menampilkan list data cif rebase history | Berhasil Menampilkan list data cif rebase history | P |  |
| 51.6 | Melihat tab CIF Rebase Archive | Klik tab cif rebase archive | Menampilkan list data cif rebase yang di arsipkan | Berhasil Menampilkan list data cif rebase yang di arsipkan | P |  |
| 51.7 | Melakukan Unarchive cif | Klik icon unarchive cif | Cif berhasil di unarchive | Berhasil Cif berhasil di unarchive | P |  |
| 51.8 | Mengunduh data cif rebase history | Klik tab cif rebase history - klik button export data | Berhasil mengunduh data | Berhasil mengunduh data | P |  |
| 51.9 | Mencari data pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |

52. Modul Sales Force - Report - Report Produktivitas

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 52.1 | Membuka menu Report produktivitas | Klik menu Sales Force - Klik submenu Report - Klik submenu Report Produktivitas | Menampilkan halaman Report Produktivitas | Berhasil Menampilkan halaman Report Produktivitas | P |  |
| 52.2 | Melakukan filter data | Klik button filter – pilih kantor wilayah, kantir cabang, cabang pembantu, subjab, sales code, bulan dan tahun – kemudian klik button filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 52.3 | Mengunduh seluruh data report produktifitas | Klik button export all | Berhasil mengunduh all data report produktivitas | Berhasil mengunduh all data report produktivitas | P |  |
| 52.4 | Mengunduh data resume | Klik button Export Pada salah satu tabel | Berhasil mengunduh data | Berhasil mengunduh data | P |  |
| 52.5 | Tab sforce | Klik tab Sforce | Menampilkan report data Target Growth | Berhasil Menampilkan report data Target Growth | P |  |
| 52.6 | mengunduh data sforce | Klik tab Sforce | Menampilkan report data Target Growth | Berhasil Menampilkan report data Target Growth | P |  |
| 52.7 | Tab Calculate | Klik tab calculate | Menampilkan report data kalkulasi nilai produktifitas berdasarkan tipe kantor | Berhasil Menampilkan report data kalkulasi nilai produktifitas berdasarkan tipe kantor | P |  |
| 52.8 | Mengunduh data calculate | Klik button export calculate | Berhasil mengunduh data calculate | Berhasil mengunduh data calculate | P |  |
| 52.9 | Tab Realisasi | Klik tab Realisasi | Menampilkan report data nilai realisasi setiap daftar Target Growth | Berhasil Menampilkan report data nilai realisasi setiap daftar Target Growth | P |  |
| 52.10 | Mengunduh data realisasi | Klik button Export realisasi | Berhasil mengunduh data realisasi | Berhasil mengunduh data realisasi | P |  |
| 52.11 | Tab Target | Klik tab Target | Menampilkan report data target | Berhasil Menampilkan report data target | P |  |
| 52.12 | Mengunduh data Target | Klik button export target | Berhasil mengunduh data target | Berhasil mengunduh data target | P |  |
| 52.13 | Tab Target DPK | Klik tab T.DPK | Menampilkan report data nilai akumulasi target growth atau voa | Berhasil Menampilkan report data nilai akumulasi target growth atau voa | P |  |
| 52.14 | Mengunduh data target DPK | Klik button export Target DPK | Berhasil mengunduh data target dpk | Berhasil mengunduh data target dpk | P |  |
| 52.15 | Tab DPK port | Klik tab DPK \_Port | Menampilkan report data berdasarakan nilai voa atau growth secara aktual | Berhasil Menampilkan report data berdasarakan nilai voa atau growth secara aktual | P |  |
| 52.16 | Mengunduh data Target DPK port | Klik button export DPK Port | Berhasil mengunduh data dpk port | Berhasil mengunduh data dpk port | P |  |
| 52.17 | Tab konek Echannel | Klik tab Konek\_Echnl | Menampilkan report data secara konektifitas mobile banking | Berhasil Menampilkan report data secara konektifitas mobile banking | P |  |
| 52.18 | Mengunduh data konek echannel | Klik button export konek echannel | Berhasil mengunduh data konek echanel | Berhasil mengunduh data konek echanel | P |  |
| 52.19 | Tab All CIF | Klik tab All\_CIF | Menampilkan report data seluruh cif pada Target Growth | Berhasil Menampilkan report data seluruh cif pada Target Growth | P |  |
| 52.20 | Mengunduh data all cif | Klik button export all cif | Berhasil mengunduh data all cif | Berhasil mengunduh data all cif | P |  |
| 52.21 | Tab SegMove | Klik tab SegMove | Menampilkan informasi data voa pada bulan berjalan dan perbandingan nilai voa pada akhir tahun lalu | Berhasil Menampilkan informasi data voa pada bulan berjalan dan perbandingan nilai voa pada akhir tahun lalu | P |  |
| 52.22 | Mengunduh data Segmove | Klik button export segmove | Berhasil mengunduh data segmove | Berhasil mengunduh data segmove | P |  |
| 52.23 | Tab Visit | Klik tab Visit | Menampilkan report data visit | Berhasil Menampilkan report data visit | P |  |
| 52.24 | Mengunduh data Visit | Klik button export Visit | Berhasil mengunduh data visit | Berhasil mengunduh data visit | P |  |
| 52.25 | Tab Merchant | Klik tab Merchant | Menampilkan report data merchant | Berhasil Menampilkan report data merchant | P |  |
| 52.26 | Mengunduh data Merchant | Klik button export Merchant | Berhasil mengunduh data merchant | Berhasil mengunduh data merchant | P |  |
| 52.27 | Tab Tier | Klik tab Tier | Menampilkan report data tier | Berhasil Menampilkan report data tier | P |  |
| 52.28 | Mengunduh data Tier | Klik button export Tier | Berhasil mengunduh data tier | Berhasil mengunduh data tier | P |  |
| 52.29 | Tab Referal | Klik tab Referal | Menampilkan report data refreal | Berhasil Menampilkan report data refreal | P |  |
| 52.30 | Mengunduh data Referal | Klik button export Referal | Berhasil mengunduh data referal | Berhasil mengunduh data referal | P |  |
| 52.31 | Tab Presensi | Klik tab Presensi | Menampilkan report data absensi bisnis unit TAD | Berhasil Menampilkan report data absensi bisnis unit TAD | P |  |
| 52.32 | Mengunduh data Presensi | Klik button export presensi | Berhasil mengunduh data persensi | Berhasil mengunduh data persensi | P |  |

53. Modul Sales Force - Dashboard Sales Force

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 53.1 | Membuka menu dashboard sales code | Klik menu Sales force - Klik submenu dashboard | Menampilkan halaman Dashboard | Berhasil Menampilkan halaman Dashboard | P |  |
| 53.2 | Melakukan filter data berdasarkan bulan | Pilih bulan | Menampilkan data sesuai dengan bulan yang dipilih | Berhasil Menampilkan data sesuai dengan bulan yang dipilih | P |  |
| 53.3 | Melakukan filter data | Klik button filter – pilih – kantor wilayah, kantor cabang, kantor cabang pembantu, jobrole dan salescode - kemudian klik filter | Menampilkan data sesuai dengan filter yang dipilih | Berhasil Menampilkan data sesuai dengan filter yang dipilih | P |  |
| 53.4 | Melihat detail Card VoA Realization | Klik icon (tanda panah) pada Card VoA Realization | Menampilkan halaman detail Card VoA Realization | Berhasil Menampilkan halaman detail Card VoA Realization | P |  |
| 53.5 | Filter data Voa Realization | Pilih kantor wilayah, kantor cabang kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 53.6 | Mencari data Voa realization pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 53.7 | Melihat detail Voa Realization | Klik icon mata | Menampilkan detail Card VoA Realization | Berhasil Menampilkan detail Card VoA Realization | P |  |
| 53.8 | Melihat detail card Cif Kelolaan | Klik icon (tanda panah) pada card Cif Kelolaan | Menampilkan halaman detail Cif Kelolaan | Berhasil Menampilkan halaman detail Cif Kelolaan | P |  |
| 53.9 | Filter data Cif Kelolaan | Pilih kantor wilayah, kantor cabang kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 53.10 | mencari data Cif Kelolaan pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 53.11 | Melihat detail Cif Kelolaan | Klik icon mata | Menampilkan detail Cif Kelolaan | Berhasil Menampilkan detail Cif Kelolaan | P |  |
| 53.12 | Melihat detail card skor Produktivitas | Klik icon (tanda panah) pada card skor Produktivitas | Menampilkan halaman detail skor Produktivitas | Berhasil Menampilkan halaman detail skor Produktivitas | P |  |
| 53.13 | Filter data produktivitas | Pilih kantor wilayah, kantor cabang kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 53.14 | Melihat detail skor Produktivitas | Klik icon mata | Menampilkan detail skor Produktivitas | Berhasil Menampilkan detail skor Produktivitas | P |  |
| 53.15 | Melihat detail data card konek echannel | Klik icon (tanda panah) pada card konek echannel | Menampilkan halaman detail konek echannel | Berhasil Menampilkan halaman detail konek echannel | P |  |
| 53.16 | Filter data konek echannel | Pilih kantor wilayah, kantor cabang kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 53.17 | Mencari data konek echannel pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 53.18 | Melihat detail data konek echannel | Klik icon mata | Menampilkan detail konek echannel | Berhasil Menampilkan detail konek echannel | P |  |
| 53.19 | Melihat detail data card realisasi visit | Klik icon (tanda panah) pada card realisasi visit | Direct ke menu client visit list | Berhasil Direct ke menu client visit list | P |  |
| 53.20 | Melihat detail data card realisasi akuisisi merchant | Klik icon (tanda panah) pada card realisasi akuisisi merchant | Menampilkan halaman detail realisasi akuisisi merchant | Berhasil Menampilkan halaman detail realisasi akuisisi merchant | P |  |
| 53.21 | Filter data realisasi akuisisi merchant | Pilih kantor wilayah, kantor cabang kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 53.22 | Mencari data realisasi akuisisi merchant pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 53.23 | Melihat detail data realisasi merchant | Klik icon mata | Menampilkan detail realisasi akuisisi merchant | Berhasil Menampilkan detail realisasi akuisisi merchant | P |  |
| 53.24 | Melihat detail data card Eligible Upgrade to Prospera / Prioritas | Klik icon (tanda panah) pada card Eligible Upgrade to Prospera / Prioritas | Menampilkan halaman detail Eligible Upgrade to Prospera / Prioritas | Berhasil Menampilkan halaman detail Eligible Upgrade to Prospera / Prioritas | P |  |
| 53.25 | Filter data Eligible Upgrade to Prospera / Prioritas | Pilih kantor wilayah, kantor cabang kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 53.26 | Mencari data Eligible Upgrade to Prospera Prioritas pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 53.27 | Melihat detail data Eligible Upgrade to Prospera / Prioritas | Klik icon mata | Menampilkan detail Eligible Upgrade to Prospera / Prioritas | Berhasil Menampilkan detail Eligible Upgrade to Prospera / Prioritas | P |  |
| 53.28 | Melihat detail data card Referral to Prospera / Prioritas | Klik icon (tanda panah) card Referral to Prospera / Prioritas | Menampilkan halaman detail Referral to Prospera / Prioritas | Berhasil Menampilkan halaman detail Referral to Prospera / Prioritas | P |  |
| 53.29 | Filter data Referral to Prospera / Prioritas | Pilih kantor wilayah, kantor cabang kemudian klik button filter | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 53.30 | Mencari data Referral to Prospera / Prioritas pada kolom pencarian | Input data pada kolom pencarian | Menampilkan data sesuai kata kunci yang diinput | Berhasil Menampilkan data sesuai kata kunci yang diinput | P |  |
| 53.31 | Melihat detail data Referral to Prospera / Prioritas | Klik icon mata | Menampilkan detail Referral to Prospera / Prioritas | Berhasil Menampilkan detail Referral to Prospera / Prioritas | P |  |

54. Modul Sales Force - Pipeline - Setting Role Validate Pipeline

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 54.1 | Membuka menu setting Role validate Pipeline | Klik menu Sales Force - Klik Submenu Pipeline - Klik submenu Setting Role Validate Pipeline | Menampilkan halaman Setting role validate pipeline | Berhasil Menampilkan halaman Setting role validate pipeline | P |  |
| 54.2 | Melakukan filter tipe organisasi | Pilih tipe organisasi kemudian klik button filter data | Menampilkan data sesuai filter yang dipilih | Berhasil Menampilkan data sesuai filter yang dipilih | P |  |
| 54.3 | Menambahkan data setting role | Klik button tambah setting role - isi form - klik simpan | Menampilkan pesan berhasil menambahkan data setting role | Berhasil menambahkan data setting role | P |  |
| 54.4 | Melihat riwayat setting role | Klik button riwayat setting role | Menampilkan modal riwayat setting role | Berhasil Menampilkan modal riwayat setting role | P |  |
| 54.5 | Melihat ilustration alur validasi pipeline | Klik link alur validasi pipeline | Menampilkan modal ilustrasi alur validasi pipeline | Berhasil Menampilkan modal ilustrasi alur validasi pipeline | P |  |
| 54.6 | Mengubah data setting role | Klik icon edit pada salah satu data setting role - ubah data - simpan | Menampilkan pesan berhasil mengubah data setting role | Berhasil mengubah data setting role | P |  |
| 54.7 | Menghapus data setting role | Klik icon hapus pada salah satu data setting role - konfirmasi hapus | Menampilkan pesan berhasil menghapus data setting role | Berhasil menghapus data setting role | P |  |
| 54.8 | Mencari data pada kolom pencarian | Masukkan kata kunci valid pada kolom pencarian kemudian tekan enter | Menampilkan data sesuai kata kunci pencarian | Berhasil Menampilkan data sesuai kata kunci pencarian | P |  |
| 54.9 | Mencari data kata kunci tidak valid (Negative test) | Masukkan kata kunci tidak valid pada kolom pencarian kemudian tekan enter | Menampilkan informasi data tidak ditemukan | Berhasil Menampilkan informasi data tidak ditemukan | P |  |

55. Modul Sales Force - Pipeline - Setting Validate Pipeline

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 55.1 | Membuka menu setting validate pipeline | Klik menu Sales Force - Klik Submenu Pipeline - Klik submenu Setting Validate Pipeline | Menampilkan halaman Setting validate pipeline | Berhasil Menampilkan halaman Setting validate pipeline | P |  |
| 55.2 | input setting validate pipeline | Klik button +input setting validate pipeline - input data dengan mengisi (group produk role, segment, produk dan apakah lembaga) - klik button save | Berhasil menambahkan data dan data dan data akan tampil pada menu dahsboard tabel validate pipeline | Berhasil menambahkan data dan data dan data akan tampil pada menu dahsboard tabel validate pipeline | P |  |
| 55.3 | Mengubah data setting validate pipeline | Klik icon titik tiga(opsi) - klik edit - ubah data - klik button simpan | berhasil menyimpan perubahan data | berhasil menyimpan perubahan data | P |  |
| 55.4 | Menghapus data setting validate pipeline | Klik icon titik tiga(opsi) - klik button hapus | Berhasil menghapus data | Berhasil menghapus data | P |  |
| 55.5 | Melihat detail setting validate pipeline | Klik button detail | Menampilkan detail data | Menampilkan detail data | P |  |
| 55.6 | Mencari data pada kolom pencarian | Input kata kunci pada kolom pencarian | Menampilkan data sesuai kata kunci | Menampilkan data sesuai kata kunci | P |  |
| 55.7 | Mencari data kata kunci tidak valid (Negative test) | Input kata kunci tidak valid pada kolom pencarian | Data tidak ditemukan | Data tidak ditemukan | P |  |

56. Modul Sales Force - Pipeline - Input komitmen

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 56.1 | Membuka menu input komitmen | Klik menu Sales Force - Klik Submenu Pipeline - Klik submenu input komitmen | Menampilkan halaman Input komitmen | Berhasil Menampilkan halaman Input komitmen | P |  |
| 56.2 | Input komitmen | Klik button input komitmen - input data dengan mengisi (bulan, tahun,Tabungan ritel,deposito ritel, giro ritel, Tabungan Lembaga, deposito Lembaga, dan giro Lembaga) - kemudian klik button save untuk menyimpan data | Berhasil menambahkan komitmen baru | Berhasil menambahkan komitmen baru | P |  |
| 56.3 | Input komitmen menggunakan huruf (Negative test) | Klik button input komitmen - input huruf pada kolom penginputan nominal | Field tidak bisa di ketik | Berhasil Field tidak bisa di ketik | P |  |
| 56.4 | Mengubah nilai komitmen | Klik button edit pada table - ubah data - klik button save | Berhasil menyimpan perubahan | Berhasil menyimpan perubahan | P |  |
| 56.5 | Mengembalikan nilai komitment menjadi 0 | Klik button reset - klik “ya,reset” | Berhasil mengembalikan nilai komitmen menjadi 0 | Berhasil mengembalikan nilai komitmen menjadi 0 | P |  |
| 56.6 | Mengunduh data | Klik button export data | Berhasil mengunduh data komitmen | Berhasil mengunduh data komitmen | P |  |

57. Modul Kalender

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 57.1 | Membuka halaman Kalender | Masuk ke menu utama - Klik menu Kalender pada sidebar | Berhasil menampilkan halaman Kalender beserta ringkasan status dan grid kalender. | Berhasil menampilkan halaman Kalender beserta ringkasan status dan grid kalender. | P |  |
| 57.2 | Melakukan navigasi periode kalender | Pada halaman Kalender, klik tombol navigasi panah (< / >) atau tombol Hari ini | Berhasil mengubah tampilan periode kalender sesuai pilihan. | Berhasil mengubah tampilan periode kalender sesuai pilihan. | P |  |
| 57.3 | Mengubah mode tampilan kalender | Pada halaman Kalender, klik tombol mode tampilan (Bulan / Minggu / Hari / Daftar) | Berhasil menampilkan kalender berdasarkan mode tampilan yang dipilih. | Berhasil menampilkan kalender berdasarkan mode tampilan yang dipilih. | P |  |
| 57.4 | Memfilter entri kalender berdasarkan kategori | Centang atau uncentang checkbox kategori entri (Task / Acara / Hari Libur / Time Off / Pola Kerja) | Berhasil menampilkan entri kalender sesuai kategori yang dipilih. | Berhasil menampilkan entri kalender sesuai kategori yang dipilih. | P |  |
| 57.5 | Menambahkan task baru | Klik tombol Tambah - Pilih Tambah Task - Lengkapi formulir task - Klik Buat Task | Berhasil menambahkan task baru ke dalam kalender. | Berhasil menambahkan task baru ke dalam kalender. | P |  |
| 57.6 | Menambahkan acara baru | Klik tombol Tambah - Pilih Tambah Acara - Lengkapi formulir event - Klik Buat Event | Berhasil menambahkan acara baru ke dalam kalender. | Berhasil menambahkan acara baru ke dalam kalender. | P |  |
| 57.7 | Menambahkan label baru | Klik tombol Kelola Label - Masukkan Nama label - Pilih warna label - Klik Tambah Label | Berhasil menambahkan label baru dan menampilkan notifikasi sukses. | Berhasil menambahkan label baru dan menampilkan notifikasi sukses. | P |  |
| 57.8 | Menghapus label | Pada daftar label, klik icon Hapus pada label yang dipilih - Konfirmasi Hapus | Berhasil menghapus label dari sistem. | Berhasil menghapus label dari sistem. | P |  |
| 57.9 | Membuka halaman Daftar Task | Pada halaman Kalender, klik tombol Daftar Task | Berhasil menampilkan halaman Daftar Task. | Berhasil menampilkan halaman Daftar Task. | P |  |
| 57.10 | Melakukan filter Daftar Task | Pada halaman Daftar Task, pilih kriteria filter (Kepemilikan, Status, Prioritas, Label, atau Rentang Tenggat) | Berhasil menampilkan data task sesuai filter yang dipilih. | Berhasil menampilkan data task sesuai filter yang dipilih. | P |  |
| 57.11 | Mencari task dengan keyword valid | Pada halaman Daftar Task, masukkan kata kunci valid pada field Cari task | Berhasil menampilkan data task yang sesuai dengan kata kunci pencarian. | Berhasil menampilkan data task yang sesuai dengan kata kunci pencarian. | P |  |
| 57.12 | Mencari task dengan keyword tidak valid | Pada halaman Daftar Task, masukkan kata kunci yang tidak valid / tidak terdaftar pada field Cari task | Berhasil menampilkan informasi bahwa data task tidak ditemukan. | Berhasil menampilkan informasi bahwa data task tidak ditemukan. | P |  |
| 57.13 | Mereset filter Daftar Task | Pada halaman Daftar Task, klik tombol Reset Filter | Berhasil mereset filter dan menampilkan seluruh data task ke kondisi default. | Berhasil mereset filter dan menampilkan seluruh data task ke kondisi default. | P |  |
| 57.14 | Memulai pengerjaan task | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Terbuka - Pilih menu Mulai | Berhasil mengubah status task menjadi Berjalan. | Berhasil mengubah status task menjadi Berjalan. | P |  |
| 57.15 | Membuka kembali task yang telah selesai | Pada tabel Daftar Task, klik icon titik tiga pada task berstatus Selesai - Pilih menu Buka Kembali | Berhasil membuka kembali task. | Berhasil membuka kembali task. | P |  |
| 57.16 | Membatalkan task | Pada drawer Edit Task, klik button Batalkan - Klik button Ya, Batalkan pada pop-up konfirmasi aksi | Berhasil membatalkan task. | Berhasil membatalkan task. | P |  |
| 57.17 | Mengubah data task | Pada tabel Daftar Task, klik baris task atau icon titik tiga - Pilih menu Edit - Ubah data pada drawer Edit Task - Klik tombol Simpan | Berhasil mengubah data task. | Berhasil mengubah data task. | P |  |
| 57.18 | Menghapus task secara permanen | Pada drawer Edit Task atau menu titik tiga, klik menu Hapus - Klik button Hapus pada pop-up konfirmasi Hapus task ini secara permanen? | Berhasil menghapus task secara permanen. | Berhasil menghapus task secara permanen. | P |  |
| 57.19 | Membagikan task kepada user | Pada drawer Edit Task, klik button Bagikan - Pada pop-up Bagikan Task, pilih penerima dan role - Klik Tambahkan | Berhasil membagikan task kepada user. | Berhasil membagikan task kepada user. | P |  |
| 57.20 | Menghapus penugasan task kepada user | Pada pop-up Bagikan Task, klik icon Hapus (tempat sampah) pada user yang ditugaskan - Tutup pop-up | Berhasil menghapus penugasan task kepada user. | Berhasil menghapus penugasan task kepada user. | P |  |

58. Modul Report Funding - Personal Funnel

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 58.1 | Membuka halaman Personal Funnel | Klik menu Report Funding - Klik sub menu Personal Funnel | Berhasil menampilkan halaman Personal Funnel. | Berhasil menampilkan halaman Personal Funnel. | P |  |
| 58.2 | Melakukan filter data Personal Funnel | Mengisi semua field filter mandatory - Klik button Submit | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 58.3 | Melakukan filter data Personal Funnel tanpa mengisi field mandatory | Mengosongkan field filter mandatory - Klik button Submit | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | P |  |
| 58.4 | Mengekspor data Personal Funnel | Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

59. Modul Report Funding - Rekap Funnel

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 59.1 | Membuka halaman Rekap Funnel | Klik menu Report Funding - Klik sub menu Rekap Funnel | Berhasil menampilkan halaman Rekap Funnel. | Berhasil menampilkan halaman Rekap Funnel. | P |  |
| 59.2 | Melakukan filter data Rekap Funnel | Mengisi field filter mandatory beserta kriteria filter spesifik (seperti Kantor Cabang/Role) - Klik button Filter Data | Berhasil menampilkan data Rekap Funnel yang sesuai dengan kriteria filter yang dipilih. | Berhasil menampilkan data Rekap Funnel yang sesuai dengan kriteria filter yang dipilih. | P |  |
| 59.3 | Melakukan filter data Rekap Funnel tanpa mengisi field mandatory | Mengosongkan field filter mandatory - Klik button Filter Data | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | P |  |
| 59.4 | Mereset filter data Rekap Funnel | Klik button Reset Filter | Berhasil mengosongkan kriteria filter dan mengembalikan kondisi filter ke default. | Berhasil mengosongkan kriteria filter dan mengembalikan kondisi filter ke default. | P |  |
| 59.5 | Mengekspor data Rekap Funnel | Klik button Download Excel | Berhasil mendownload file Excel data Rekap Funnel. | Berhasil mendownload file Excel data Rekap Funnel. | P |  |

60. Modul Report Funding - Pengaturan Funnel

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 60.1 | Membuka halaman Pengaturan Funnel Funding | Klik menu Report Funding - Klik sub menu Pengaturan Funnel | Berhasil menampilkan halaman Pengaturan Funnel Funding. | Berhasil menampilkan halaman Pengaturan Funnel Funding. | P |  |
| 60.2 | Mengubah data Pengaturan Funnel Funding | Mengisi semua field mandatory Performance Percentage pada setiap tahapan funnel - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | P |  |
| 60.3 | Mengubah data Pengaturan Funnel Funding tanpa mengisi field mandatory | Mengosongkan field mandatory Performance Percentage - Klik button Submit | Berhasil menampilkan pesan validasi bahwa field mandatory harus diisi. | Berhasil menampilkan pesan validasi bahwa field mandatory harus diisi. | P |  |
| 60.4 | Menambahkan Kondisi pada Indikator Performa | Klik button Add Condition pada bagian Performance Indicator - Mengisi semua field mandatory pada condition baru - Klik button Submit | Berhasil menyimpan condition baru pada Performance Indicator. | Berhasil menyimpan condition baru pada Performance Indicator. | P |  |
| 60.5 | Menghapus Kondisi pada Indikator Performa | Klik button Remove pada salah satu condition di Performance Indicator - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | P |  |
| 60.6 | Menambahkan Operator pada Kondisi | Klik button Add Operator pada condition yang dipilih - Memilih operator - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | P |  |
| 60.7 | Menghapus Operator pada Kondisi | Klik button Remove pada salah satu operator di condition - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | Berhasil menyimpan perubahan data Pengaturan Funnel Funding. | P |  |

61. Modul Report Funding - Daily Sales Agenda

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 61.1 | Membuka halaman Daily Sales Agenda | Klik menu Report Funding - Klik sub menu Daily Sales Agenda | Berhasil menampilkan halaman Daily Sales Agenda. | Berhasil menampilkan halaman Daily Sales Agenda. | P |  |
| 61.2 | Melakukan filter data Daily Sales Agenda | Mengisi semua field filter mandatory - Klik button Filter Data | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 61.3 | Melakukan filter data Daily Sales Agenda tanpa mengisi field mandatory | Mengosongkan field filter mandatory - Klik button Filter Data | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | P |  |
| 61.4 | Menampilkan data tab Prospek Masuk | Klik tab Prospek Masuk | Berhasil menampilkan data pada tab Prospek Masuk. | Berhasil menampilkan data pada tab Prospek Masuk. | P |  |
| 61.5 | Mencari data Prospek Masuk dengan keyword valid | Klik tab Prospek Masuk - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 61.6 | Mencari data Prospek Masuk dengan keyword tidak valid | Klik tab Prospek Masuk - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 61.7 | Melihat detail Prospek Masuk | Klik tab Prospek Masuk - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 61.8 | Mengekspor data tab Prospek Masuk | Klik tab Prospek Masuk - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 61.9 | Menampilkan data tab Prospek Closing | Klik tab Prospek Closing | Berhasil menampilkan data pada tab Prospek Closing. | Berhasil menampilkan data pada tab Prospek Closing. | P |  |
| 61.10 | Mencari data Prospek Closing dengan keyword valid | Klik tab Prospek Closing - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 61.11 | Mencari data Prospek Closing dengan keyword tidak valid | Klik tab Prospek Closing - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 61.12 | Melihat detail Prospek Closing | Klik tab Prospek Closing - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 61.13 | Mengekspor data tab Prospek Closing | Klik tab Prospek Closing - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 61.14 | Menampilkan data tab Prospek Referal | Klik tab Prospek Referal | Berhasil menampilkan data pada tab Prospek Referal. | Berhasil menampilkan data pada tab Prospek Referal. | P |  |
| 61.15 | Mencari data Prospek Referal dengan keyword valid | Klik tab Prospek Referal - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 61.16 | Mencari data Prospek Referal dengan keyword tidak valid | Klik tab Prospek Referal - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 61.17 | Melihat detail Prospek Referal | Klik tab Prospek Referal - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 61.18 | Mengekspor data tab Prospek Referal | Klik tab Prospek Referal - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 61.19 | Menampilkan data tab Prospek Referal Closing | Klik tab Prospek Referal Closing | Berhasil menampilkan data pada tab Prospek Referal Closing. | Berhasil menampilkan data pada tab Prospek Referal Closing. | P |  |
| 61.20 | Mencari data Prospek Referal Closing dengan keyword valid | Klik tab Prospek Referal Closing - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 61.21 | Mencari data Prospek Referal Closing dengan keyword tidak valid | Klik tab Prospek Referal Closing - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 61.22 | Melihat detail Prospek Referal Closing | Klik tab Prospek Referal Closing - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 61.23 | Mengekspor data tab Prospek Referal Closing | Klik tab Prospek Referal Closing - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

62. Modul Report Lending - Personal Funnel

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 62.1 | Membuka halaman Personal Funnel | Klik menu Report Lending - Klik sub menu Personal Funnel | Berhasil menampilkan halaman Personal Funnel. | Berhasil menampilkan halaman Personal Funnel. | P |  |
| 62.2 | Menampilkan data Personal Funnel berdasarkan tab | Klik salah satu daftar tab (Semua, Non PKS, PKS) pada halaman Personal Funnel | Berhasil menampilkan data Personal Funnel pada tab Semua, Non PKS, dan PKS. | Berhasil menampilkan data Personal Funnel pada tab Semua, Non PKS, dan PKS. | P |  |
| 62.3 | Melakukan filter data Personal Funnel | Mengisi semua field filter mandatory - Klik button Submit | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 62.4 | Melakukan filter data Personal Funnel tanpa mengisi field mandatory | Mengosongkan field filter mandatory - Klik button Submit | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | P |  |

63. Modul Report Lending - Rekap Funnel

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 63.1 | Membuka halaman Rekap Funnel | Klik menu Report Lending - Klik sub menu Rekap Funnel | Berhasil menampilkan halaman Rekap Funnel. | Berhasil menampilkan halaman Rekap Funnel. | P |  |
| 63.2 | Melakukan filter data Rekap Funnel | Mengisi field filter mandatory beserta kriteria filter spesifik (seperti Kantor Cabang/Role) - Klik button Filter Data | Berhasil menampilkan data Rekap Funnel yang sesuai dengan kriteria filter yang dipilih. | Berhasil menampilkan data Rekap Funnel yang sesuai dengan kriteria filter yang dipilih. | P |  |
| 63.3 | Melakukan filter data Rekap Funnel tanpa mengisi field mandatory | Mengosongkan field filter mandatory - Klik button Filter Data | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | P |  |
| 63.4 | Mereset filter data Rekap Funnel | Klik button Reset Filter | Berhasil mengosongkan kriteria filter dan mengembalikan kondisi filter ke default. | Berhasil mengosongkan kriteria filter dan mengembalikan kondisi filter ke default. | P |  |
| 63.5 | Mengekspor data Rekap Funnel | Klik button Download Excel | Berhasil mendownload file Excel data Rekap Funnel. | Berhasil mendownload file Excel data Rekap Funnel. | P |  |

64. Modul Report Lending - Pengaturan Funnel

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 64.1 | Membuka halaman Pengaturan Funnel Lending | Klik menu Report Lending - Klik sub menu Pengaturan Funnel | Berhasil menampilkan halaman Pengaturan Funnel Lending. | Berhasil menampilkan halaman Pengaturan Funnel Lending. | P |  |
| 64.2 | Mengubah data Pengaturan Funnel Lending | Mengisi semua field mandatory Performance Percentage pada setiap tahapan funnel - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | P |  |
| 64.3 | Mengubah data Pengaturan Funnel Lending tanpa mengisi field mandatory | Mengosongkan field mandatory Performance Percentage - Klik button Submit | Berhasil menampilkan pesan validasi bahwa field mandatory harus diisi. | Berhasil menampilkan pesan validasi bahwa field mandatory harus diisi. | P |  |
| 64.4 | Menambahkan Kondisi pada Indikator Performa | Klik button Add Condition pada bagian Performance Indicator - Mengisi semua field mandatory pada condition baru - Klik button Submit | Berhasil menyimpan condition baru pada Performance Indicator. | Berhasil menyimpan condition baru pada Performance Indicator. | P |  |
| 64.5 | Menghapus Kondisi pada Indikator Performa | Klik button Remove pada salah satu condition di Performance Indicator - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | P |  |
| 64.6 | Menambahkan Operator pada Kondisi | Klik button Add Operator pada condition yang dipilih - Memilih operator - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | P |  |
| 64.7 | Menghapus Operator pada Kondisi | Klik button Remove pada salah satu operator di condition - Klik button Submit | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | Berhasil menyimpan perubahan data Pengaturan Funnel Lending. | P |  |

65. Modul Report Lending - Daily Sales Agenda

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 65.1 | Membuka halaman Daily Sales Agenda | Klik menu Report Lending - Klik sub menu Daily Sales Agenda | Berhasil menampilkan halaman Daily Sales Agenda. | Berhasil menampilkan halaman Daily Sales Agenda. | P |  |
| 65.2 | Melakukan filter data Daily Sales Agenda | Mengisi semua field filter mandatory - Klik button Filter Data | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 65.3 | Melakukan filter data Daily Sales Agenda tanpa mengisi field mandatory | Mengosongkan field filter mandatory - Klik button Filter Data | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. | P |  |
| 65.4 | Menampilkan data tab Prospek Masuk | Klik tab Prospek Masuk | Berhasil menampilkan data pada tab Prospek Masuk. | Berhasil menampilkan data pada tab Prospek Masuk. | P |  |
| 65.5 | Mencari data Prospek Masuk dengan keyword valid | Klik tab Prospek Masuk - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 65.6 | Mencari data Prospek Masuk dengan keyword tidak valid | Klik tab Prospek Masuk - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 65.7 | Melihat detail Prospek Masuk | Klik tab Prospek Masuk - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 65.8 | Mengekspor data tab Prospek Masuk | Klik tab Prospek Masuk - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 65.9 | Menampilkan data tab Prospek Closing | Klik tab Prospek Closing | Berhasil menampilkan data pada tab Prospek Closing. | Berhasil menampilkan data pada tab Prospek Closing. | P |  |
| 65.10 | Mencari data Prospek Closing dengan keyword valid | Klik tab Prospek Closing - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 65.11 | Mencari data Prospek Closing dengan keyword tidak valid | Klik tab Prospek Closing - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 65.12 | Melihat detail Prospek Closing | Klik tab Prospek Closing - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 65.13 | Mengekspor data tab Prospek Closing | Klik tab Prospek Closing - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 65.14 | Menampilkan data tab Prospek Referal | Klik tab Prospek Referal | Berhasil menampilkan data pada tab Prospek Referal. | Berhasil menampilkan data pada tab Prospek Referal. | P |  |
| 65.15 | Mencari data Prospek Referal dengan keyword valid | Klik tab Prospek Referal - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 65.16 | Mencari data Prospek Referal dengan keyword tidak valid | Klik tab Prospek Referal - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 65.17 | Melihat detail Prospek Referal | Klik tab Prospek Referal - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 65.18 | Mengekspor data tab Prospek Referal | Klik tab Prospek Referal - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 65.19 | Menampilkan data tab Prospek Referal Closing | Klik tab Prospek Referal Closing | Berhasil menampilkan data pada tab Prospek Referal Closing. | Berhasil menampilkan data pada tab Prospek Referal Closing. | P |  |
| 65.20 | Mencari data Prospek Referal Closing dengan keyword valid | Klik tab Prospek Referal Closing - Mengisi field Cari Data dengan keyword valid - Klik button Search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 65.21 | Mencari data Prospek Referal Closing dengan keyword tidak valid | Klik tab Prospek Referal Closing - Mengisi field Cari Data dengan keyword tidak valid - Klik button Search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 65.22 | Melihat detail Prospek Referal Closing | Klik tab Prospek Referal Closing - Klik salah satu nama prospek pada tabel | Berhasil menampilkan halaman detail prospek. | Berhasil menampilkan halaman detail prospek. | P |  |
| 65.23 | Mengekspor data tab Prospek Referal Closing | Klik tab Prospek Referal Closing - Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

66. Modul Re-Assign dan Approval - Approval Non Banking

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 66.1 | Membuka halaman Approval non Banking | Klik menu Re-Assign & Approval - Klik submenu Approval non banking | Menampilkan halaman Approval non banking | Berhasil menampilkan halaman Approval non banking | P |  |
| 66.2 | Melakukan filter data Approval non Banking | Pilih filter Sales, Produk, Bulan, Tahun - Klik button Submit | Menampilkan data approval non banking sesuai filter yang dipilih | Berhasil menampilkan data approval non banking sesuai filter yang dipilih | P |  |
| 66.3 | Mencari data dengan kata kunci valid | Masukkan kata kunci valid pada kolom Cari Data - Klik icon search | Menampilkan data approval non banking yang dicari | Berhasil menampilkan data approval non banking yang dicari | P |  |
| 66.4 | Mencari data dengan kata kunci tidak valid | Masukkan kata kunci tidak valid pada kolom Cari Data - Klik icon search | Menampilkan informasi data tidak ditemukan | Berhasil menampilkan informasi data tidak ditemukan | P |  |
| 66.5 | Melakukan approval data prospek | Klik titik tiga pada data status PENDING - Klik Setujui - Input Realisasi dan Remark - Klik button Setujui | Menampilkan konfirmasi berhasil menyetujui prospek | Berhasil menampilkan konfirmasi berhasil menyetujui prospek | P |  |
| 66.6 | Melakukan reject data prospek | Klik titik tiga pada data status PENDING - Klik Tolak - Input Remark - Klik button Tolak | Menampilkan konfirmasi berhasil menolak prospek | Berhasil menampilkan konfirmasi berhasil menolak prospek | P |  |
| 66.7 | Melihat detail data prospek | Klik titik tiga pada data - Klik opsi Detail | Menampilkan modal detail data prospek | Berhasil menampilkan modal detail data prospek | P |  |

67. Modul Re-Assign dan Approval - Re-Assign Prospek

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 67.1 | Membuka halaman Re-Assign Prospek | Klik menu Re-Assign & Approval - Klik submenu Re-Assign Prospek | Menampilkan halaman Re-Assign Prospek | Berhasil menampilkan halaman Re-Assign Prospek | P |  |
| 67.2 | Melakukan filter data Re-Assign Prospek | Klik button Filter - Pilih Produk dan Sales pada drawer Filter - Klik button Filter | Menampilkan data prospek sesuai filter yang dipilih | Berhasil menampilkan data prospek sesuai filter yang dipilih | P |  |
| 67.3 | Mencari data dengan kata kunci valid | Masukkan kata kunci valid pada kolom Cari Data - Klik icon search | Menampilkan data prospek yang dicari | Berhasil menampilkan data prospek yang dicari | P |  |
| 67.4 | Mencari data dengan kata kunci tidak valid | Masukkan kata kunci tidak valid pada kolom Cari Data - Klik icon search | Menampilkan informasi data tidak ditemukan | Berhasil menampilkan informasi data tidak ditemukan | P |  |
| 67.5 | Melakukan re-assign beberapa data prospek | Checklist beberapa data prospek - Klik button Reassign () data - Klik button Yes - Pilih Wilayah, Cabang, dan Sales baru - Klik button Submit | Menampilkan notifikasi berhasil melakukan Reassign Prospek | Berhasil menampilkan notifikasi berhasil melakukan Reassign Prospek | P |  |
| 67.6 | Melakukan re-assign semua data prospek | Klik button Reassign Semua data - Klik button Yes - Pilih Wilayah, Cabang, dan Sales baru - Klik button Submit | Menampilkan notifikasi berhasil melakukan Reassign Prospek | Berhasil menampilkan notifikasi berhasil melakukan Reassign Prospek | P |  |

68. Modul Re-Assign dan Approval - Re-Assign Management

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 68.1 | Membuka halaman Re-Assign Management | Klik menu Re-Assign & Approval - Klik submenu Re-Assign Management | Menampilkan halaman Re-Assign Management | Berhasil menampilkan halaman Re-Assign Management | P |  |
| 68.2 | Mencari data dengan kata kunci valid | Masukkan kata kunci valid pada kolom Cari Data - Klik icon search | Menampilkan data prospek yang dicari | Berhasil menampilkan data prospek yang dicari | P |  |
| 68.3 | Mencari data dengan kata kunci tidak valid | Masukkan kata kunci tidak valid pada kolom Cari Data - Klik icon search | Menampilkan informasi data tidak ditemukan | Berhasil menampilkan informasi data tidak ditemukan | P |  |
| 68.4 | Melakukan re-assign management | Checklist data prospek - Klik button Reassign () data - Klik button Yes - Pilih Sales tujuan pada modal - Klik button Submit | Menampilkan notifikasi berhasil melakukan re-assign data prospek | Berhasil menampilkan notifikasi berhasil melakukan re-assign data prospek | P |  |

69. Modul Export Center - Riwayat Export

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 69.1 | Membuka halaman Riwayat Export | Klik menu Export Center - Klik submenu Riwayat Export | Berhasil menampilkan halaman Riwayat Export. | Berhasil menampilkan halaman Riwayat Export. | P |  |
| 69.2 | Mencari data riwayat export dengan kata kunci valid | Masukkan kata kunci valid pada Search Bar - Klik button Cari | Berhasil menampilkan data riwayat export yang dicari. | Berhasil menampilkan data riwayat export yang dicari. | P |  |
| 69.3 | Mencari data riwayat export dengan kata kunci tidak valid | Masukkan kata kunci tidak valid pada Search Bar - Klik button Cari | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 69.4 | Melihat data riwayat export berdasarkan status | Pada halaman Riwayat Export, klik salah satu tab status | Berhasil menampilkan daftar data riwayat export sesuai status yang dipilih. | Berhasil menampilkan daftar data riwayat export sesuai status yang dipilih. | P |  |
| 69.5 | Melakukan filter data riwayat export | Klik button Filter - Pilih kriteria filter pada drawer - Klik button Terapkan Filter | Berhasil memfilter dan menampilkan data riwayat export sesuai kriteria filter. | Berhasil memfilter dan menampilkan data riwayat export sesuai kriteria filter. | P |  |
| 69.6 | Mereset filter data riwayat export | Klik button Filter - Klik button Reset pada drawer Filter | Berhasil mereset filter dan menampilkan seluruh data riwayat export. | Berhasil mereset filter dan menampilkan seluruh data riwayat export. | P |  |
| 69.7 | Melihat detail riwayat export | Klik icon Aksi (...) pada salah satu baris data - Klik opsi Detail | Berhasil menampilkan drawer Export Detail. | Berhasil menampilkan drawer Export Detail. | P |  |
| 69.8 | Mengunduh file data export yang tersedia | Klik icon Aksi (...) pada baris data dengan status Tersedia - Klik opsi Download | Berhasil mengunduh file data export. | Berhasil mengunduh file data export. | P |  |
| 69.9 | Mengunduh data yang sudah di approve | Klik button download pada data yang statusnya disetujui | Berhasil mengunduh data export. | Berhasil mengunduh data export. | P |  |
| 69.10 | Membuka dokumen hasil download | Extract file zip hasil download menggunakan password yang dikirim ke email user | Berhasil membuka file hasil download. | Berhasil membuka file hasil download. | P |  |
| 69.11 | Melakukan filter data pada tab Riwayat Export | Klik button filter - pilih modul, export status, dan rentang tanggal request - klik terapkan filter | Berhasil Menampilkan data sesuai filter yang dipilih. | Berhasil Menampilkan data sesuai filter yang dipilih. | P |  |
| 69.12 | Mencari data pada kolom pencarian | Input keyword valid pada kolom pencarian | Berhasil Menampilkan data sesuai kata kunci pencarian. | Berhasil Menampilkan data sesuai kata kunci pencarian. | P |  |
| 69.13 | Mencari data kata kunci salah | Input keyword tidak valid pada kolom pencarian | Berhasil Menampilkan keterangan data tidak ditemukan. | Berhasil Menampilkan keterangan data tidak ditemukan. | P |  |
| 69.14 | Melakukan filter data pada tab Semua Request | Buka tab Semua Request - Klik button filter - pilih filter - klik terapkan filter | Berhasil Menampilkan data sesuai filter yang dipilih pada tab Semua Request. | Berhasil Menampilkan data sesuai filter yang dipilih pada tab Semua Request. | P |  |
| 69.15 | Mencari data pada kolom pencarian tab Semua Request | Buka tab Semua Request - Input keyword pada kolom pencarian | Berhasil Menampilkan data sesuai kata kunci pada tab Semua Request. | Berhasil Menampilkan data sesuai kata kunci pada tab Semua Request. | P |  |
| 69.16 | Mencari data kata kunci salah tab Semua Request | Buka tab Semua Request - Input keyword tidak valid pada kolom pencarian | Berhasil Menampilkan keterangan data tidak ditemukan pada tab Semua Request. | Berhasil Menampilkan keterangan data tidak ditemukan pada tab Semua Request. | P |  |
| 69.17 | Validasi card menunggu approval dengan data table | Cocokkan jumlah data pada card menunggu approval dengan jumlah baris data di table | Berhasil Jumlah data pada card dan table sesuai. | Berhasil Jumlah data pada card dan table sesuai. | P |  |

70. Modul Export Center - Persetujuan Export

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 70.1 | Membuka halaman Persetujuan Export | Klik menu Export Center - Klik submenu Persetujuan Export | Berhasil menampilkan halaman Persetujuan Export. | Berhasil menampilkan halaman Persetujuan Export. | P |  |
| 70.2 | Mencari data persetujuan export dengan kata kunci valid | Masukkan kata kunci valid pada Search Bar - Klik button Cari | Berhasil menampilkan data persetujuan export yang dicari. | Berhasil menampilkan data persetujuan export yang dicari. | P |  |
| 70.3 | Mencari data persetujuan export dengan kata kunci tidak valid | Masukkan kata kunci tidak valid pada Search Bar - Klik button Cari | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 70.4 | Melihat data persetujuan export berdasarkan status | Pada halaman Persetujuan Export, klik salah satu tab status | Berhasil menampilkan daftar data persetujuan export sesuai status yang dipilih. | Berhasil menampilkan daftar data persetujuan export sesuai status yang dipilih. | P |  |

71. Modul Export Center - Aktivitas Export

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 71.1 | Membuka halaman Aktivitas Export | Klik menu Export Center - Klik submenu Aktivitas Export | Berhasil menampilkan halaman Aktivitas Export. | Berhasil menampilkan halaman Aktivitas Export. | P |  |
| 71.2 | Mencari data aktivitas export dengan kata kunci valid | Masukkan kata kunci valid pada Search Bar - Klik button Cari | Berhasil menampilkan data aktivitas export yang dicari. | Berhasil menampilkan data aktivitas export yang dicari. | P |  |
| 71.3 | Mencari data aktivitas export dengan kata kunci tidak valid | Masukkan kata kunci tidak valid pada Search Bar - Klik button Cari | Berhasil menampilkan informasi data tidak ditemukan. | Berhasil menampilkan informasi data tidak ditemukan. | P |  |
| 71.4 | Melihat data aktivitas export berdasarkan status | Pada halaman Aktivitas Export, klik salah satu tab status | Berhasil menampilkan daftar data aktivitas export sesuai status yang dipilih. | Berhasil menampilkan daftar data aktivitas export sesuai status yang dipilih. | P |  |

72. Modul Ticket Maintenance - Aktivitas Issue

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 72.1 | Membuka halaman Aktivitas Issue | Klik menu Ticket Maintenance - Klik sub menu Aktivitas Issue | Berhasil menampilkan halaman Aktivitas Issue. | Berhasil menampilkan halaman Aktivitas Issue. | P |  |
| 72.2 | Melakukan filter data Aktivitas Issue | Klik tab Filter 1 - Pilih Kategori, Status, dan Platform - Klik button Filter Data | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 72.3 | Mencari data Aktivitas Issue dengan keyword valid | Klik tab Filter 2 - Input keyword valid pada Search Bar - Klik button Cari | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 72.4 | Menambahkan pelaporan issue baru | Klik button + Registrasi Issue - Input seluruh field mandatory pada modal - Klik button Registrasi Issue | Berhasil menyimpan data pelaporan issue. | Berhasil menyimpan data pelaporan issue. | P |  |
| 72.5 | Melihat detail pelaporan issue | Klik icon Aksi (...) pada salah satu baris data - Klik opsi Detail | Berhasil menampilkan halaman detail issue. | Berhasil menampilkan halaman detail issue. | P |  |
| 72.6 | Mengubah data pelaporan issue | Klik icon Aksi (...) pada salah satu baris data - Klik opsi Edit - Ubah data issue - Klik button Simpan | Berhasil menyimpan perubahan data issue. | Berhasil menyimpan perubahan data issue. | P |  |
| 72.7 | Menambahkan komentar pada detail aktivitas issue | Buka halaman detail issue - Masukkan komentar pada kolom komentar - Klik button Kirim | Berhasil menambahkan komentar pada detail issue. | Berhasil menambahkan komentar pada detail issue. | P |  |
| 72.8 | Menghapus data pelaporan issue | Klik icon Aksi (...) pada salah satu baris data - Klik opsi Hapus - Klik button Konfirmasi | Berhasil menghapus data issue. | Berhasil menghapus data issue. | P |  |

73. Modul Ticket Maintenance - Kategori Aktivitas Issue

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 73.1 | Membuka halaman Master Kategori Issue | Klik menu Ticket Maintenance - Klik sub menu Kategori Aktivitas Issue | Berhasil menampilkan halaman Master Kategori Issue. | Berhasil menampilkan halaman Master Kategori Issue. | P |  |
| 73.2 | Menambahkan kategori lain melalui pelaporan issue | Buka form Buat Pelaporan Issue - Pilih Kategori Others - Masukkan Nama Kategori Lain dan Remark - Klik button Registrasi Issue | Berhasil menambahkan data kategori baru ke List Kategori Lain. | Berhasil menambahkan data kategori baru ke List Kategori Lain. | P |  |
| 73.3 | Menambahkan data master kategori | Klik button + Add Kategori - Input seluruh field mandatory pada modal - Klik button Save | Berhasil menyimpan data master kategori. | Berhasil menyimpan data master kategori. | P |  |
| 73.4 | Mencari data pada List Kategori Lain | Input kata kunci pada field Cari Data List Kategori Lain - Klik icon search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 73.5 | Melihat detail data kategori pada List Kategori Lain | Klik icon Aksi (...) pada baris data List Kategori Lain - Klik opsi Detail | Berhasil menampilkan modal detail kategori. | Berhasil menampilkan modal detail kategori. | P |  |
| 73.6 | Mengirim data kategori lain ke master kategori | Klik button Send to Master pada baris data - Pilih Role dan PIC - Klik button Save | Berhasil mengirim data kategori lain ke master kategori. | Berhasil mengirim data kategori lain ke master kategori. | P |  |
| 73.7 | Mengirim data kategori lain ke master kategori secara massal | Checklist data pada List Kategori Lain - Klik button Bulk Send to Master | Berhasil mengirim beberapa kategori lain terpilih ke master kategori. | Berhasil mengirim beberapa kategori lain terpilih ke master kategori. | P |  |
| 73.8 | Mencari data pada List Kategori | Input kata kunci pada field Cari Data List Kategori - Klik icon search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 73.9 | Melihat dan mengubah data master kategori | Klik icon Aksi (...) pada baris data List Kategori - Klik opsi Detail - Ubah data - Klik button Save | Berhasil menampilkan dan memperbarui data master kategori. | Berhasil menampilkan dan memperbarui data master kategori. | P |  |

74. Modul Ticket Maintenance - Dashboard Aktivitas Issue

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 74.1 | Membuka halaman Dashboard Aktivitas Issue | Klik menu Ticket Maintenance - Klik sub menu Dashboard Aktivitas Issue | Berhasil menampilkan halaman Dashboard Aktivitas Issue. | Berhasil menampilkan halaman Dashboard Aktivitas Issue. | P |  |
| 74.2 | Melakukan filter data Dashboard Aktivitas Issue | Pilih Bulan dan Tahun pada filter periode di pojok kanan atas halaman | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 74.3 | Melihat detail issue pada tabel 5 Newest Issue | Pada tabel 5 Newest Issue, klik icon Aksi (...) - Klik opsi Detail | Berhasil menampilkan halaman detail issue. | Berhasil menampilkan halaman detail issue. | P |  |

75. Modul Ticket Maintenance - Report Aktivitas Issue

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 75.1 | Membuka halaman Report Aktivitas Issue | Klik menu Ticket Maintenance - Klik sub menu Report Aktivitas Issue | Berhasil menampilkan halaman Report Aktivitas Issue. | Berhasil menampilkan halaman Report Aktivitas Issue. | P |  |
| 75.2 | Melakukan filter data Report Aktivitas Issue | Pilih Status dan Prioritas - Klik button Filter Data | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 75.3 | Mencari data Report Aktivitas Issue dengan keyword valid | Input keyword valid pada field Cari Data - Klik icon search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 75.4 | Melihat detail report aktivitas issue | Klik icon Aksi (...) pada salah satu baris data - Klik opsi Detail | Berhasil menampilkan halaman detail issue. | Berhasil menampilkan halaman detail issue. | P |  |
| 75.5 | Menghapus data report aktivitas issue secara massal | Checklist beberapa data pada tabel - Klik button Hapus data - Klik button Yes | Berhasil menghapus data report aktivitas issue. | Berhasil menghapus data report aktivitas issue. | P |  |
| 75.6 | Mengekspor data Report Aktivitas Issue | Klik button Export - Klik icon download pada panel Download Export | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

76. Modul Dashboard - Aktivitas Consumer Funding

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 76.1 | Membuka halaman Dashboard Aktivitas Consumer Funding | Klik menu Dashboard - Klik menu Aktivitas Consumer - Klik sub menu Aktivitas Consumer Funding | Berhasil menampilkan halaman Dashboard Aktivitas Consumer Funding. | Berhasil menampilkan halaman Dashboard Aktivitas Consumer Funding. | P |  |
| 76.2 | Melakukan filter data Dashboard Aktivitas Consumer Funding | Pilih filter Kantor, Bulan, dan Tahun - Klik button Filter | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 76.3 | Mencari data pada tabel Aktivitas Sales dengan keyword valid | Input keyword valid pada field Cari Data tabel Aktivitas Sales - Klik icon search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 76.4 | Mencari data pada tabel Aktivitas Sales dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data tabel Aktivitas Sales - Klik icon search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 76.5 | Mengekspor data tabel Aktivitas Sales | Klik button Export pada tabel Aktivitas Sales | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 76.6 | Mencari data pada tabel Aktivitas Referral dengan keyword valid | Input keyword valid pada field Cari Data tabel Aktivitas Referral - Klik icon search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 76.7 | Mencari data pada tabel Aktivitas Referral dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data tabel Aktivitas Referral - Klik icon search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 76.8 | Mengekspor data tabel Aktivitas Referral | Klik button Export pada tabel Aktivitas Referral | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

77. Modul Dashboard - Aktivitas Consumer Lending

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 77.1 | Membuka halaman Dashboard Aktivitas Consumer Lending | Klik menu Dashboard - Klik menu Aktivitas Consumer - Klik sub menu Aktivitas Consumer Lending | Berhasil menampilkan halaman Dashboard Aktivitas Consumer Lending. | Berhasil menampilkan halaman Dashboard Aktivitas Consumer Lending. | P |  |
| 77.2 | Melakukan filter data Dashboard Aktivitas Consumer Lending | Pilih filter Kantor dan rentang Start - End Date - Klik button Filter | Berhasil menampilkan data sesuai dengan filter yang dipilih. | Berhasil menampilkan data sesuai dengan filter yang dipilih. | P |  |
| 77.3 | Mencari data pada tabel Aktivitas Sales dengan keyword valid | Input keyword valid pada field Cari Data tabel Aktivitas Sales - Klik icon search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 77.4 | Mencari data pada tabel Aktivitas Sales dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data tabel Aktivitas Sales - Klik icon search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 77.5 | Mengekspor data tabel Aktivitas Sales | Klik button Export pada tabel Aktivitas Sales | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |
| 77.6 | Mencari data pada tabel Aktivitas Referral dengan keyword valid | Input keyword valid pada field Cari Data tabel Aktivitas Referral - Klik icon search | Berhasil menampilkan data yang dicari. | Berhasil menampilkan data yang dicari. | P |  |
| 77.7 | Mencari data pada tabel Aktivitas Referral dengan keyword tidak valid | Input keyword tidak valid pada field Cari Data tabel Aktivitas Referral - Klik icon search | Berhasil menampilkan informasi bahwa data tidak ditemukan. | Berhasil menampilkan informasi bahwa data tidak ditemukan. | P |  |
| 77.8 | Mengekspor data tabel Aktivitas Referral | Klik button Export pada tabel Aktivitas Referral | Berhasil mendownload file export. | Berhasil mendownload file export. | P |  |

78. Modul Dashboard - Pengaturan Aktivitas Consumer

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 78.1 | Membuka halaman Pengaturan Aktivitas Consumer | Klik menu Dashboard - Klik menu Aktivitas Consumer - Klik sub menu Pengaturan Aktivitas Consumer | Berhasil menampilkan halaman Pengaturan Aktivitas Consumer. | Berhasil menampilkan halaman Pengaturan Aktivitas Consumer. | P |  |
| 78.2 | Mengubah role pada Pengaturan Aktivitas Consumer Funding | Pilih atau sesuaikan data pada field Role Pengaturan Aktivitas Consumer Funding - Klik button Simpan | Berhasil menyimpan perubahan role pada Pengaturan Aktivitas Consumer Funding. | Berhasil menyimpan perubahan role pada Pengaturan Aktivitas Consumer Funding. | P |  |
| 78.3 | Mengubah role pada Pengaturan Aktivitas Consumer Lending | Pilih atau sesuaikan data pada field Role Pengaturan Aktivitas Consumer Lending - Klik button Simpan | Berhasil menyimpan perubahan role pada Pengaturan Aktivitas Consumer Lending. | Berhasil menyimpan perubahan role pada Pengaturan Aktivitas Consumer Lending. | P |  |

79. Modul Dashboard - Optimalisasi Database

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed**  **, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 79.1 | Membuka halaman Dashboard Optimalisasi Database | Klik menu Dashboard - Klik sub menu Optimalisasi | Berhasil menampilkan halaman Dashboard Optimalisasi Database. | Berhasil menampilkan halaman Dashboard Optimalisasi Database. | P |  |
| 79.2 | Melakukan filter data Dashboard Optimalisasi Database | Pilih Kantor Wilayah, Kantor Cabang, Sales, Produk, Source Debitur, Info Bulan, dan Info Tahun - Klik button Submit | Berhasil menampilkan data dashboard dan bagan alur optimalisasi sesuai filter yang dipilih. | Berhasil menampilkan data dashboard dan bagan alur optimalisasi sesuai filter yang dipilih. | P |  |
| 79.3 | Mencari data pada tabel dengan keyword valid | Masukkan keyword valid pada kolom Cari Data - Klik button Cari | Berhasil menampilkan data yang sesuai dengan keyword pencarian. | Berhasil menampilkan data yang sesuai dengan keyword pencarian. | P |  |
| 79.4 | Mencari data pada tabel dengan keyword tidak valid | Masukkan keyword tidak valid pada kolom Cari Data - Klik button Cari | Menampilkan keterangan data tidak ditemukan / tabel kosong. | Menampilkan keterangan data tidak ditemukan / tabel kosong. | P |  |
| 79.5 | Mengekspor data tabel Optimalisasi Database | Klik button Export | Berhasil mengunduh file data tabel dalam format Excel (.xlsx). | Berhasil mengunduh file data tabel dalam format Excel (.xlsx). | P |  |