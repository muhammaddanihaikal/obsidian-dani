---
tags:
  - UAT
  - HasilUji
  - BTN
  - Mobile
  - QA
date: 2026-10-22
project: BTN Smart
platform: Mobile
source_file: Dokumen_Hasil_Uji_Mobile_fixed.docx
total_tc: 204
converter: markitdown
---

![](data:image/png;base64...)![A blue and red logo  Description automatically generated](data:image/jpeg;base64...)

Dokumen Hasil Uji - Unit Testing (UT)

BTN SMART v3

PT Bank Tabungan Negara Persero Tbk

![](data:image/png;base64...)

Nama File : Dokumen Hasil UT - BTN SMART Mobile Redesain

**Informasi Dokumen**

|  |  |
| --- | --- |
| **Informasi Dokumen** | |
| **Nama Proyek** | BTN SMART Mobile Redesain |
| **Nama Aplikasi** | BTN SMART v3 |
| **Hasil Uji** | Unit Testing (UT) |
| **Versi** | 1.0 |
| **Nama File** | Dokumen Hasil Uji Unit Testing - BTN SMART Mobile Redesain |

|  |  |  |  |
| --- | --- | --- | --- |
| **Pelaksana Unit Testing (Pihak Penyedia Jasa TI)** | | | |
| Tanggal: Maret 2025 | Tanggal: Maret 2025 | Tanggal: Maret 2025 | Tanggal Maret 2025 |
| Catatan: | Catatan: | Catatan: | Catatan: |
| **Developer**  ![A signature on a white background  Description automatically generated](data:image/jpeg;base64...) | **Business Analyst**  ![A close-up of a signature  Description automatically generated](data:image/png;base64...) | **Software Tester**  ![A close-up of a signature  Description automatically generated](data:image/jpeg;base64...) | **Project Manager**  ![A black background with a white object in the middle  Description automatically generated](data:image/png;base64...) |
| (Muhamad Ahrul Syamil Ulum) | (Herry Setiawan) | (Fujianingsih) | (Henry Daudi) |

|  |
| --- |
| **Diketahui Oleh (Pihak BTN)** |
| Tanggal: |
| Catatan: |
| **IT Project Manager**  ................................. ( )  Nama Jabatan |

Daftar Isi

[**Histori Perbaikan** 4](#_Toc242794552)

[**1. Modul Login** 5](#_Toc242794553)

[**2. Modul Profile** 19](#_Toc242794554)

[**3. Modul Sales Tracking Activity - Visit In** 51](#_Toc242794555)

[**4. Modul Sales Tracking Activity - Visit Out** 57](#_Toc242794556)

[**5. Modul Absent - Clock In** 63](#_Toc242794557)

[**6. Modul Absent - Clock Out** 70](#_Toc242794558)

[**7. Modul Log Absensi** 77](#_Toc242794559)

[**8. Modul Personal Funnel** 81](#_Toc242794560)

[**9. Modul Cuti & Izin** 111](#_Toc242794561)

[**10. Modul Kalender** 119](#_Toc242794562)

[**11. Modul Prospek & Nasabah - Aktifitas Prospek** 162](#_Toc242794563)

[**12. Modul Prospek & Nasabah - Input Prospek** 188](#_Toc242794564)

[**13. Modul Prospek & Nasabah - List Nasabah ETB** 205](#_Toc242794565)

[**14. Modul Prospek & Nasabah - Nasabah Referal** 213](#_Toc242794566)

[**15. Modul Agenda - Pengingat** 217](#_Toc242794567)

[**16. Modul Agenda - Daily Sales Agenda** 231](#_Toc242794568)

[**17. Modul Fitur - Marketing Toolkit** 238](#_Toc242794569)

[**18. Modul Sales Force - Dashboard Sales Code** 246](#_Toc242794570)

[**19. Modul Kunjungan** 253](#_Toc242794571)

[**20. Modul Notifikasi** 262](#_Toc242794572)

# **Histori Perbaikan**

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **No** | **Dibuat Oleh** | **Tangal** | **Modifikasi** | **Deskripsi** |
| *1.0* | Zegen Solusi Mandiri | 18 April 2024 |  |  |

# **1. Modul Login**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 1.1 | Membuka halaman Login |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka aplikasi dan menampilkan halaman login. - [Success] |

|  |  |
| --- | --- |
| 1.2 | Melakukan login dengan email dan password valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan login dan diarahkan ke halaman 2 Factor Authentication. - [Success] |

|  |  |
| --- | --- |
| 1.3 | Melakukan login dengan email tidak terdaftar |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error email tidak terdaftar. - [Success] |

|  |  |
| --- | --- |
| 1.4 | Melakukan login dengan password salah |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error autentikasi. - [Success] |

|  |  |
| --- | --- |
| 1.5 | Melakukan login tanpa mengisi email |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error field mandatory. - [Success] |

|  |  |
| --- | --- |
| 1.6 | Melakukan login tanpa mengisi password |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error field mandatory. - [Success] |

|  |  |
| --- | --- |
| 1.7 | Melakukan login tanpa mengisi email dan password |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error field mandatory. - [Success] |

|  |  |
| --- | --- |
| 1.8 | Melakukan verifikasi Email OTP |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan verifikasi dan diarahkan ke halaman utama. - [Success] |

|  |  |
| --- | --- |
| 1.9 | Melakukan verifikasi Email OTP dengan kode tidak valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error OTP tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.10 | Melakukan verifikasi TOTP |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan verifikasi dan diarahkan ke halaman utama. - [Success] |

|  |  |
| --- | --- |
| 1.11 | Melakukan verifikasi TOTP dengan kode tidak valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error TOTP tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.12 | Melakukan login menggunakan perangkat terpercaya |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil login kembali dan langsung diarahkan ke halaman utama tanpa melalui 2 Factor Authentication. - [Success] |

|  |  |
| --- | --- |
| 1.13 | Menggunakan Kode Pemulihan |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menggunakan kode pemulihan dan diarahkan ke halaman utama. - [Success] |

|  |  |
| --- | --- |
| 1.14 | Menggunakan Kode Pemulihan yang tidak valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error kode pemulihan tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.15 | Mengajukan Reset MFA |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengajukan reset MFA. - [Success] |

# **2. Modul Profile**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 2.1 | Membuka halaman profile |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman profile. - [Success] |

|  |  |
| --- | --- |
| 2.2 | Membuka halaman Informasi Pribadi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Informasi Pribadi dan menampilkan form Informasi Pribadi. - [Success] |

|  |  |
| --- | --- |
| 2.3 | Mengubah foto profil |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah foto profil dan memperbaruinya di halaman Informasi Pribadi. - [Success] |

|  |  |
| --- | --- |
| 2.4 | Mengubah data Informasi Pribadi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan dan menampilkan notifikasi sukses. - [Success] |

|  |  |
| --- | --- |
| 2.5 | Mengubah data Informasi Pribadi tanpa mengisi field mandatory |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Gagal menyimpan data dan menampilkan pesan validasi field mandatory. - [Success] |

|  |  |
| --- | --- |
| 2.6 | Membatalkan perubahan data Informasi Pribadi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Perubahan dibatalkan dan kembali ke halaman Profile utama tanpa menyimpan data. - [Success] |

|  |  |
| --- | --- |
| 2.7 | Membuka halaman Perangkat Tertaut |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Perangkat Tertaut dan menampilkan daftar data perangkat. - [Success] |

|  |  |
| --- | --- |
| 2.8 | Melihat opsi Perangkat Tertaut |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan menu opsi perangkat (Detail, Jangan Percayai Perangkat, Ganti Nama, Hapus). - [Success] |

|  |  |
| --- | --- |
| 2.9 | Melihat detail Perangkat Tertaut |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi detail dari perangkat tersebut. - [Success] |

|  |  |
| --- | --- |
| 2.10 | Mengubah status perangkat menjadi tidak dipercayai |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah status perangkat menjadi tidak dipercayai. - [Success] |

|  |  |
| --- | --- |
| 2.11 | Mengubah data nama Perangkat Tertaut |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah nama perangkat tertaut. - [Success] |

|  |  |
| --- | --- |
| 2.12 | Menghapus data Perangkat Tertaut |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus perangkat dari daftar perangkat tertaut. - [Success] |

|  |  |
| --- | --- |
| 2.13 | Memutuskan semua Perangkat Tertaut |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memutuskan semua perangkat yang terhubung (kecuali perangkat saat ini). - [Success] |

|  |  |
| --- | --- |
| 2.14 | Membuka halaman Ganti Kata Sandi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Ganti Kata Sandi dan menampilkan form ganti kata sandi beserta persyaratannya. - [Success] |

|  |  |
| --- | --- |
| 2.15 | Mengubah data Kata Sandi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah kata sandi dan menampilkan notifikasi sukses. - [Success] |

|  |  |
| --- | --- |
| 2.16 | Mengubah data Kata Sandi dengan kata sandi lama yang salah |
|  |  |
| **Hasil yang diharapkan [STATUS]:**  Gagal mengubah kata sandi dan menampilkan notifikasi pesan error kata sandi lama salah. - [Success] |

|  |  |
| --- | --- |
| 2.17 | Mengubah data Kata Sandi tanpa memenuhi kriteria persyaratan |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Gagal mengubah kata sandi dan menampilkan pesan validasi tidak memenuhi kriteria. - [Success] |

|  |  |
| --- | --- |
| 2.18 | Mengubah data Kata Sandi dengan konfirmasi kata sandi tidak cocok |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Gagal mengubah kata sandi dan menampilkan notifikasi pesan error konfirmasi kata sandi tidak cocok. - [Success] |

|  |  |
| --- | --- |
| 2.19 | Menampilkan dan menyembunyikan input Kata Sandi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyembunyikan kembali teks kata sandi tersebut. - [Success] |

|  |  |
| --- | --- |
| 2.20 | Membuka halaman Atur MFA |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Atur MFA dan menampilkan Setup Autentikasi Dua Faktor (2FA). - [Success] |

|  |  |
| --- | --- |
| 2.21 | Mengaktifkan MFA menggunakan metode TOTP via scan barcode |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA menggunakan metode TOTP dan mendapatkan kode Cadangan (Recovery Code). - [Success] |

|  |  |
| --- | --- |
| 2.22 | Mengaktifkan MFA menggunakan metode TOTP via kode manual |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA menggunakan metode TOTP dan mendapatkan kode Cadangan (Recovery Code). - [Success] |

|  |  |
| --- | --- |
| 2.23 | Mengaktifkan MFA menggunakan metode TOTP dengan kode OTP salah (Negative test) |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa kode OTP tidak sesuai. - [Success] |

|  |  |
| --- | --- |
| 2.24 | Mengaktifkan MFA menggunakan metode Email OTP |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA menggunakan metode Email OTP dan mendapatkan kode Cadangan (Recovery Code). - [Success] |

|  |  |
| --- | --- |
| 2.25 | Mengaktifkan MFA menggunakan metode Email OTP dengan kirim ulang kode OTP |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengirim ulang kode OTP dan berhasil mengaktifkan MFA menggunakan kode baru. - [Success] |

|  |  |
| --- | --- |
| 2.26 | Setup MFA menggunakan metode Email OTP dengan kode OTP kadaluarsa (lebih dari 5 menit) (Negative test) |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa kode OTP sudah kadaluarsa dan tidak bisa digunakan. - [Success] |

|  |  |
| --- | --- |
| 2.27 | Mengubah metode MFA |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah metode MFA ke metode yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 2.28 | Mengubah metode MFA dengan password tidak valid (Negative test) |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi password tidak valid. - [Success] |

|  |  |
| --- | --- |
| 2.29 | Melihat data Recovery Code dengan password valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memvalidasi password dan menampilkan data Recovery Code. - [Success] |

|  |  |
| --- | --- |
| 2.30 | Memvalidasi akses Recovery Code dengan password salah (Negative test) |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi password tidak valid. - [Success] |

|  |  |
| --- | --- |
| 2.31 | Melakukan generate ulang Recovery Code |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuat dan menampilkan daftar Recovery Code baru. - [Success] |

|  |  |
| --- | --- |
| 2.32 | Menyalin semua Recovery Code |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyalin seluruh Recovery Code ke clipboard. - [Success] |

|  |  |
| --- | --- |
| 2.33 | Mengunduh file data Recovery Code |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data Recovery Code ke penyimpanan perangkat. - [Success] |

|  |  |
| --- | --- |
| 2.34 | Membuka halaman Riwayat Login |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Riwayat Login dan menampilkan daftar data riwayat login (berisi IP, perangkat, lokasi). - [Success] |

|  |  |
| --- | --- |
| 2.35 | Mencari data Riwayat Login dengan keyword valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mencari dan menampilkan daftar riwayat login yang memuat data sesuai dengan keyword tersebut. - [Success] |

|  |  |
| --- | --- |
| 2.36 | Mencari data Riwayat Login dengan keyword tidak valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mencari namun tidak menampilkan data apapun (state data tidak ditemukan). - [Success] |

|  |  |
| --- | --- |
| 2.37 | Melakukan filter data Riwayat Login |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memfilter dan menampilkan daftar riwayat aktivitas sesuai dengan tipe filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 2.38 | Membersihkan cache aplikasi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membersihkan cache aplikasi dan menampilkan notifikasi sukses. - [Success] |

|  |  |
| --- | --- |
| 2.39 | Logout dari aplikasi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memproses logout dan kembali ke halaman Login awal aplikasi. - [Success] |

# **3. Modul Sales Tracking Activity - Visit In**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 3.1 | Melakukan Visit in menggunakan sales Funding |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan Visit In. - [Success] |

|  |  |
| --- | --- |
| 3.2 | Melakukan Visit in menggunakan sales Funding |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menginput data visit in. - [Success] |

|  |  |
| --- | --- |
| 3.3 | Melakukan Visit in menggunakan sales Funding |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan visit in dan buttton otomatis berubah menjadi visit out. - [Success] |

|  |  |
| --- | --- |
| 3.4 | Melakukan Visit in menggunakan sales Lending |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan visit in. - [Success] |

|  |  |
| --- | --- |
| 3.5 | Melakukan Visit in menggunakan sales Lending |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menginput data visit in. - [Success] |

|  |  |
| --- | --- |
| 3.6 | Melakukan Visit in menggunakan sales Lending |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan visit in dan buttton otomatis berubah menjadi visit out. - [Success] |

# **4. Modul Sales Tracking Activity - Visit Out**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 4.1 | Melakukan Visit out menggunakan sales Funding |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan Visit out. - [Success] |

|  |  |
| --- | --- |
| 4.2 | Melakukan Visit out menggunakan sales Funding |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menginput data visit out. - [Success] |

|  |  |
| --- | --- |
| 4.3 | Melakukan Visit out menggunakan sales Funding |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan visit out dan buttton otomatis berubah menjadi visit in. - [Success] |

|  |  |
| --- | --- |
| 4.4 | Melakukan Visit out menggunakan sales Lending |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan visit out. - [Success] |

|  |  |
| --- | --- |
| 4.5 | Melakukan Visit out menggunakan sales Lending |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menginput data visit out. - [Success] |

|  |  |
| --- | --- |
| 4.6 | Melakukan Visit out menggunakan sales Lending |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan visit out dan buttton otomatis berubah menjadi visit in. - [Success] |

# **5. Modul Absent - Clock In**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 5.1 | Melakukan Clock In |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan clock in. - [Success] |

|  |  |
| --- | --- |
| 5.2 | Melakukan Clock In |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengambil gambar dan menginput desckripsi. - [Success] |

|  |  |
| --- | --- |
| 5.3 | Melakukan Clock In |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan clock in dan button berubah otomatis menjadi button clock out. - [Success] |

|  |  |
| --- | --- |
| 5.4 | Melakukan Clock In diluar kantor |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan clock in. - [Success] |

|  |  |
| --- | --- |
| 5.5 | Melakukan Clock In diluar kantor |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah Lokasi dan menginput data clock in. - [Success] |

|  |  |
| --- | --- |
| 5.6 | Melakukan Clock In diluar kantor |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan clock in dan button berubah otomatis menjadi button clock out. - [Success] |

|  |  |
| --- | --- |
| 5.7 | Tidak menginput data mandatory (negative test) |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert bahwa data mandatory dan wajib diisi. - [Success] |

# **6. Modul Absent - Clock Out**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 6.1 | Melakukan Clock Out |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan clock out. - [Success] |

|  |  |
| --- | --- |
| 6.2 | Melakukan Clock Out |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengambil gambar dan menginput desckripsi. - [Success] |

|  |  |
| --- | --- |
| 6.3 | Melakukan Clock Out |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan clock out dan button berubah otomatis menjadi button clock in. - [Success] |

|  |  |
| --- | --- |
| 6.4 | Melakukan Clock out diluar kantor |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman/ form inputan clock out. - [Success] |

|  |  |
| --- | --- |
| 6.5 | Melakukan Clock out diluar kantor |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah Lokasi dan menginput data clock out. - [Success] |

|  |  |
| --- | --- |
| 6.6 | Melakukan Clock out diluar kantor |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan clock out dan button berubah otomatis menjadi button clock in. - [Success] |

|  |  |
| --- | --- |
| 6.7 | Tidak menginput data mandatory (negative test) |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert bahwa data mandatory dan wajib diisi. - [Success] |

# **7. Modul Log Absensi**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 7.1 | Membuka halaman Log Absensi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Log Absensi. - [Success] |

|  |  |
| --- | --- |
| 7.2 | Melakukan filter data log absensi |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar log absensi sesuai Bulan dan Tahun yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 7.3 | Melihat detail log absensi Clock In |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi Clock In yang mencakup peta lokasi, tanggal, waktu Clock In, deskripsi, lokasi, dan akurasi. - [Success] |

|  |  |
| --- | --- |
| 7.4 | Melihat detail log absensi Clock Out |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail log absensi Clock Out yang mencakup peta lokasi, tanggal, waktu Clock Out, deskripsi, lokasi, dan akurasi. - [Success] |

# **8. Modul Personal Funnel**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 8.1 | Membuka halaman Personal Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Personal Funnel. - [Success] |

|  |  |
| --- | --- |
| 8.2 | Melakukan filter data Personal Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data grafik Personal Funnel sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 8.3 | Melakukan filter data Personal Funnel tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi field mandatory. - [Success] |

|  |  |
| --- | --- |
| 8.4 | Menampilkan grafik Prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang Prospek dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.5 | Menampilkan grafik Call |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang Call dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.6 | Menampilkan grafik Visit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang Visit dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.7 | Menampilkan grafik Volume of Account |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang Volume of Account dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.8 | Menampilkan grafik Pemberian Referral |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang Pemberian Referral dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.9 | Menampilkan grafik Posisi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang Posisi dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.10 | Menampilkan grafik NOA Open Account |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang NOA Open Account dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.11 | Menampilkan grafik NOA Top Up |
|  |  |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan grafik batang NOA Top Up dengan data Target dan Actual. - [Success] |

|  |  |
| --- | --- |
| 8.12 | Melihat detail tabel Prospek |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel Prospek yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

|  |  |
| --- | --- |
| 8.13 | Melihat detail tabel Call |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel Call yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

|  |  |
| --- | --- |
| 8.14 | Melihat detail tabel Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel Visit yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

|  |  |
| --- | --- |
| 8.15 | Melihat detail tabel Volume of Account |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel Volume of Account yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

|  |  |
| --- | --- |
| 8.16 | Melihat detail tabel Pemberian Referral |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel Pemberian Referral yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

|  |  |
| --- | --- |
| 8.17 | Melihat detail tabel Posisi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel Posisi yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

|  |  |
| --- | --- |
| 8.18 | Melihat detail tabel NOA Open Account |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel NOA Open Account yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

|  |  |
| --- | --- |
| 8.19 | Melihat detail tabel NOA Top Up |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail tabel NOA Top Up yang menampilkan data Target (NTB & ETB) dan Actual (NTB & ETB). - [Success] |

# **9. Modul Cuti & Izin**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 9.1 | Membuka halaman Cuti & Izin |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Cuti & Izin. - [Success] |

|  |  |
| --- | --- |
| 9.2 | Mencari data pengajuan cuti dengan keyword valid |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pengajuan cuti sesuai keyword yang dicari. - [Success] |

|  |  |
| --- | --- |
| 9.3 | Mencari data pengajuan cuti dengan keyword tidak valid |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 9.4 | Melakukan filter data pengajuan cuti |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pengajuan cuti sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 9.5 | Menampilkan data pengajuan cuti berdasarkan jenis cuti |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pengajuan cuti sesuai jenis cuti yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 9.6 | Menampilkan data pengajuan cuti berdasarkan status |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pengajuan cuti sesuai status yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 9.7 | Mengajukan cuti |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengajukan cuti. - [Success] |

|  |  |
| --- | --- |
| 9.8 | Mengajukan cuti tanpa mengisi field mandatory |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi field mandatory. - [Success] |

# **10. Modul Kalender**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 10.1 | Membuka halaman Kalender |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Kalender. - [Success] |

|  |  |
| --- | --- |
| 10.2 | Melakukan navigasi bulan pada Kalender |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan navigasi bulan pada kalender. - [Success] |

|  |  |
| --- | --- |
| 10.3 | Memilih tanggal tertentu pada Kalender |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memilih tanggal dan menampilkan agenda harian. - [Success] |

|  |  |
| --- | --- |
| 10.4 | Melihat detail agenda kerja pada Kalender |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail agenda kerja. - [Success] |

|  |  |
| --- | --- |
| 10.5 | Melakukan filter agenda Kalender |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan agenda kalender sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 10.6 | Mereset filter agenda Kalender |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan seluruh agenda kalender. - [Success] |

|  |  |
| --- | --- |
| 10.7 | Menambahkan task baru dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan dan menyimpan task baru. - [Success] |

|  |  |
| --- | --- |
| 10.8 | Menambahkan task baru tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Judul wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 10.9 | Menambahkan acara baru dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan dan menyimpan acara baru. - [Success] |

|  |  |
| --- | --- |
| 10.10 | Menambahkan acara baru tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Judul wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 10.11 | Membuka halaman Daftar Task |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Daftar Task. - [Success] |

|  |  |
| --- | --- |
| 10.12 | Mencari task dengan kata kunci valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data task sesuai kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 10.13 | Mencari task dengan kata kunci tidak valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan data task tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 10.14 | Melakukan filter Daftar Task |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data task sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 10.15 | Mereset filter Daftar Task |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan seluruh data task. - [Success] |

|  |  |
| --- | --- |
| 10.16 | Melihat detail task |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail task. - [Success] |

|  |  |
| --- | --- |
| 10.17 | Mengubah data task dengan data valid |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah data task. - [Success] |

|  |  |
| --- | --- |
| 10.18 | Mengubah data task tanpa mengisi field mandatory |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Judul wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 10.19 | Membagikan task kepada user |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membagikan task kepada user. - [Success] |

|  |  |
| --- | --- |
| 10.20 | Menghapus penugasan task kepada user |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus penugasan task. - [Success] |

|  |  |
| --- | --- |
| 10.21 | Menambahkan komentar pada task |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan komentar pada task. - [Success] |

|  |  |
| --- | --- |
| 10.22 | Menghapus komentar pada task |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus komentar pada task. - [Success] |

|  |  |
| --- | --- |
| 10.23 | Memulai pengerjaan task |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah status task menjadi 'Sedang Dikerjakan'. - [Success] |

|  |  |
| --- | --- |
| 10.24 | Menyelesaikan task |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah status task menjadi 'Selesai'. - [Success] |

|  |  |
| --- | --- |
| 10.25 | Membatalkan task |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan task. - [Success] |

|  |  |
| --- | --- |
| 10.26 | Membuka kembali task yang telah selesai |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka kembali task. - [Success] |

|  |  |
| --- | --- |
| 10.27 | Menghapus task secara permanen |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus task secara permanen. - [Success] |

|  |  |
| --- | --- |
| 10.28 | Membuka halaman Daftar Acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Daftar Acara. - [Success] |

|  |  |
| --- | --- |
| 10.29 | Mencari acara dengan kata kunci valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data acara sesuai kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 10.30 | Mencari acara dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan data acara tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 10.31 | Melakukan filter Daftar Acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data acara sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 10.32 | Mereset filter Daftar Acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan seluruh data acara. - [Success] |

|  |  |
| --- | --- |
| 10.33 | Melihat detail acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail acara. - [Success] |

|  |  |
| --- | --- |
| 10.34 | Mengubah data acara dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah data acara. - [Success] |

|  |  |
| --- | --- |
| 10.35 | Mengubah data acara tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Judul wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 10.36 | Membagikan acara kepada user |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membagikan acara kepada user. - [Success] |

|  |  |
| --- | --- |
| 10.37 | Menghapus penugasan acara kepada user |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus penugasan acara. - [Success] |

|  |  |
| --- | --- |
| 10.38 | Membatalkan acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan acara. - [Success] |

|  |  |
| --- | --- |
| 10.39 | Menghapus acara secara permanen |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus acara secara permanen. - [Success] |

|  |  |
| --- | --- |
| 10.40 | Membuka halaman Kelola Label |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Kelola Label. - [Success] |

|  |  |
| --- | --- |
| 10.41 | Menambahkan label baru dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan label baru. - [Success] |

|  |  |
| --- | --- |
| 10.42 | Menambahkan label baru tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Nama label wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 10.43 | Menghapus label |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus label. - [Success] |

# **11. Modul Prospek & Nasabah - Aktifitas Prospek**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 11.1 | Membuka halaman Aktifitas Prospek |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Aktifitas Prospek. - [Success] |

|  |  |
| --- | --- |
| 11.2 | Mencari prospek menggunakan Search Bar |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data prospek yang sesuai dengan kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 11.3 | Mencari prospek dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 11.4 | Melakukan filter data prospek |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar prospek yang sesuai dengan kriteria filter. - [Success] |

|  |  |
| --- | --- |
| 11.5 | Melihat Detail Prospek |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data prospek. - [Success] |

|  |  |
| --- | --- |
| 11.6 | Melihat Riwayat Prospek |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Riwayat dan menampilkan daftar log riwayat. - [Success] |

|  |  |
| --- | --- |
| 11.7 | Mencari data pada halaman Riwayat |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memfilter data riwayat sesuai kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 11.8 | Mencari data dengan keyword tidak valid pada halaman Riwayat |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 11.9 | Membuka form Input Aktifitas |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Aktifitas Marketing dan menampilkan tab Prospek, Call, Visit, dan NOA Open Account. - [Success] |

|  |  |
| --- | --- |
| 11.10 | Membuka tab Prospek pada halaman Aktifitas Marketing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil berpindah ke tab Prospek dan menampilkan form informasi prospek. - [Success] |

|  |  |
| --- | --- |
| 11.11 | Mengedit data pada tab Prospek |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan dan melanjutkan ke tahap berikutnya. - [Success] |

|  |  |
| --- | --- |
| 11.12 | Membuka tab Call pada halaman Aktifitas Marketing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil berpindah ke tab Call dan menampilkan form input Call serta Log Staging Call. - [Success] |

|  |  |
| --- | --- |
| 11.13 | Melakukan panggilan langsung melalui tombol Call |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengarahkan ke aplikasi telepon bawaan perangkat (dialer). - [Success] |

|  |  |
| --- | --- |
| 11.14 | Menyimpan log Call dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan aktifitas Call dan menambahkannya ke Log Staging Call. - [Success] |

|  |  |
| --- | --- |
| 11.15 | Menyimpan log Call tanpa field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Status Call dan Keterangan wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.16 | Membuka tab Visit pada halaman Aktifitas Marketing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil berpindah ke tab Visit dan menampilkan button Visit In serta Log Staging Visit. - [Success] |

|  |  |
| --- | --- |
| 11.17 | Melakukan Visit In |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengarahkan ke halaman Kunjungan dan menampilkan pop up pilihan tipe Visit. - [Success] |

|  |  |
| --- | --- |
| 11.18 | Membuka tab NOA Open Account pada halaman Aktifitas Marketing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil berpindah ke tab NOA Open Account dan menampilkan form NOA Open Account. - [Success] |

|  |  |
| --- | --- |
| 11.19 | Melakukan Submit NOA Open Account dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil men-submit form dan menyimpan data Open Account. - [Success] |

|  |  |
| --- | --- |
| 11.20 | Melakukan Submit NOA Open Account tanpa field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.21 | Membuka tab Top Up data pada halaman aktifitas Marketing prospek ETB |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil berpindah ke tab Top Up dana dan menampilkan form Top Up dana. - [Success] |

|  |  |
| --- | --- |
| 11.22 | Melakukan Submit Top Up dana dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil men-submit form dan menyimpan data Top Up dana. - [Success] |

|  |  |
| --- | --- |
| 11.23 | Melakukan Submit Top Up dana tanpa field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.24 | Membatalkan prospek melalui menu titik tiga |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan prospek dan prospek tidak dapat dilanjutkan kembali. - [Success] |

# **12. Modul Prospek & Nasabah - Input Prospek**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 12.1 | Membuka halaman Input Prospek melalui navigation bar bawah |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Input Prospek dan menampilkan pop up tipe prospek. - [Success] |

|  |  |
| --- | --- |
| 12.2 | Membuka halaman Input Prospek melalui menu Lainnya |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Input Prospek dan menampilkan pop up tipe prospek. - [Success] |

|  |  |
| --- | --- |
| 12.3 | Memilih tipe Prospek Individu |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan form Step 1 Informasi. - [Success] |

|  |  |
| --- | --- |
| 12.4 | Mengisi form Step 1 (Informasi) dengan data valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Step 1 dan berpindah ke Step 2 Data Pribadi. - [Success] |

|  |  |
| --- | --- |
| 12.5 | Mengisi form Step 1 (Informasi) tanpa field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Nama Lengkap dan No. Telepon wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 12.6 | Melakukan Check CIF pada form Step 1 |
|  |  |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan hasil Check CIF berdasarkan No KTP. - [Success] |

|  |  |
| --- | --- |
| 12.7 | Mengisi form Step 2 (Data Pribadi) dengan data valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Step 2 dan berpindah ke Step 3 Pekerjaan. - [Success] |

|  |  |
| --- | --- |
| 12.8 | Mengisi form Step 3 (Pekerjaan) dengan data valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Step 3 dan berpindah ke Step 4 Prospek. - [Success] |

|  |  |
| --- | --- |
| 12.9 | Mengisi form Step 4 (Prospek) NTB dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data prospek Individu NTB dan menampilkan layar konfirmasi Prospek Berhasil Dibuat. - [Success] |

|  |  |
| --- | --- |
| 12.10 | Mengisi form Step 4 (Prospek) ETB dengan mengubah status NTB |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data prospek Individu ETB dan menampilkan layar konfirmasi Prospek Berhasil Dibuat. - [Success] |

|  |  |
| --- | --- |
| 12.11 | Mengisi form Step 4 (Prospek) tanpa field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 12.12 | Navigasi ke halaman Aktifitas dari layar konfirmasi Prospek Berhasil Dibuat |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengarahkan pengguna ke halaman Lead Qualification Aktifitas. - [Success] |

|  |  |
| --- | --- |
| 12.13 | Kembali ke halaman utama dari layar konfirmasi Prospek Berhasil Dibuat |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengarahkan pengguna kembali ke halaman utama / form input. - [Success] |

|  |  |
| --- | --- |
| 12.14 | Memilih tipe Prospek Lembaga |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan form Step 1 Informasi Lembaga. - [Success] |

|  |  |
| --- | --- |
| 12.15 | Mengisi form Step 1 (Informasi Lembaga) dengan data valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Step 1 dan berpindah ke Step 2 Data Lembaga. - [Success] |

|  |  |
| --- | --- |
| 12.16 | Mengisi form Step 2 (Data Lembaga) dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Step 2 dan berpindah ke Step 3 Prospek. - [Success] |

|  |  |
| --- | --- |
| 12.17 | Mengisi form Step 2 (Data Lembaga) tanpa field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field Nama Perusahaan dan Telepon Perusahaan wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 12.18 | Mengisi form Step 3 (Prospek Lembaga) NTB dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data prospek Lembaga NTB dan menampilkan layar konfirmasi Prospek Berhasil Dibuat. - [Success] |

|  |  |
| --- | --- |
| 12.19 | Mengisi form Step 3 (Prospek Lembaga) ETB dengan mengubah status NTB |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data prospek Lembaga ETB dan menampilkan layar konfirmasi Prospek Berhasil Dibuat. - [Success] |

|  |  |
| --- | --- |
| 12.20 | Mengisi form Step 3 (Prospek Lembaga) tanpa field mandatory |
|  |  |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field mandatory wajib diisi. - [Success] |

# **13. Modul Prospek & Nasabah - List Nasabah ETB**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 13.1 | Membuka halaman List Nasabah ETB |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman List Nasabah ETB. - [Success] |

|  |  |
| --- | --- |
| 13.2 | Mencari nasabah menggunakan Search Bar |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data nasabah yang sesuai dengan kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 13.3 | Mencari nasabah dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 13.4 | Melakukan filter data nasabah |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar nasabah yang sesuai dengan kriteria filter. - [Success] |

|  |  |
| --- | --- |
| 13.5 | Melihat Detail Prospek Nasabah ETB |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Detail Prospek dan menampilkan informasi nasabah secara lengkap. - [Success] |

|  |  |
| --- | --- |
| 13.6 | Membuka form Prospek Ulang |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka form Prospek Ulang. - [Success] |

|  |  |
| --- | --- |
| 13.7 | Melakukan Prospek Ulang dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil men-submit form dan memperbarui data prospek. - [Success] |

|  |  |
| --- | --- |
| 13.8 | Melakukan Prospek Ulang tanpa field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi bahwa field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 13.9 | Melihat Informasi Rekening |
|  |  |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail rekening nasabah (nomor rekening dan saldo). - [Success] |

|  |  |
| --- | --- |
| 13.10 | Menghapus data nasabah |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data nasabah dari daftar List Nasabah ETB. - [Success] |

# **14. Modul Prospek & Nasabah - Nasabah Referal**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 14.1 | Membuka halaman Nasabah Referal |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Nasabah Referal. - [Success] |

|  |  |
| --- | --- |
| 14.2 | Mencari nasabah referal menggunakan Search Bar |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data nasabah referal yang sesuai dengan kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 14.3 | Mencari nasabah referal dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 14.4 | Melihat Detail Prospek nasabah referal |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail nasabah referal. - [Success] |

# **15. Modul Agenda - Pengingat**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 15.1 | Membuka halaman Pengingat |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Pengingat beserta daftar tugas pada tab default (Task). - [Success] |

|  |  |
| --- | --- |
| 15.2 | Melihat daftar agenda pada tab Acara |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar acara yang terdaftar pada tab Acara. - [Success] |

|  |  |
| --- | --- |
| 15.3 | Melihat detail task |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Detail Task yang memuat seluruh informasi task. - [Success] |

|  |  |
| --- | --- |
| 15.4 | Mengubah data task dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data task dengan data yang valid. - [Success] |

|  |  |
| --- | --- |
| 15.5 | Membagikan task kepada user |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membagikan task kepada user dan menampilkan pesan konfirmasi Task berhasil dibagikan. - [Success] |

|  |  |
| --- | --- |
| 15.6 | Menghapus penugasan task kepada user |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus penugasan task kepada user dari daftar pembagian task. - [Success] |

|  |  |
| --- | --- |
| 15.7 | Menambahkan komentar pada task |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengirimkan komentar dan menampilkan komentar baru pada daftar riwayat aktivitas task. - [Success] |

|  |  |
| --- | --- |
| 15.8 | Menghapus komentar pada task |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus komentar dari daftar aktivitas dan percakapan task. - [Success] |

|  |  |
| --- | --- |
| 15.9 | Melihat detail acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Detail Acara yang memuat seluruh informasi acara. - [Success] |

|  |  |
| --- | --- |
| 15.10 | Mengubah data acara dengan data valid |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data acara dengan data yang valid. - [Success] |

|  |  |
| --- | --- |
| 15.11 | Membagikan acara kepada user |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membagikan acara kepada user dan memicu notifikasi kepada penerima. - [Success] |

|  |  |
| --- | --- |
| 15.12 | Menghapus penugasan acara kepada user |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus penugasan acara kepada user dari daftar pembagian acara. - [Success] |

|  |  |
| --- | --- |
| 15.13 | Menambahkan komentar pada acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengirimkan komentar dan menampilkan komentar baru pada daftar riwayat aktivitas acara. - [Success] |

|  |  |
| --- | --- |
| 15.14 | Menghapus komentar pada acara |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus komentar dari daftar aktivitas dan percakapan acara. - [Success] |

# **16. Modul Agenda - Daily Sales Agenda**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 16.1 | Membuka halaman Daily Sales Agenda |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Daily Sales Agenda. - [Success] |

|  |  |
| --- | --- |
| 16.2 | Melihat daftar agenda pada tab Closing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar nasabah yang closing pada Daily Sales Agenda. - [Success] |

|  |  |
| --- | --- |
| 16.3 | Melihat daftar agenda pada tab Referral |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar nasabah referral pada Daily Sales Agenda. - [Success] |

|  |  |
| --- | --- |
| 16.4 | Melihat daftar agenda pada tab Ref. Closing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar nasabah referral yang closing pada Daily Sales Agenda. - [Success] |

|  |  |
| --- | --- |
| 16.5 | Mencari agenda menggunakan Search Bar |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data agenda yang sesuai dengan kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 16.6 | Mencari agenda dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 16.7 | Melakukan filter data Daily Sales Agenda |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Daily Sales Agenda sesuai filter yang dipilih. - [Success] |

# **17. Modul Fitur - Marketing Toolkit**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 17.1 | Membuka halaman Marketing Toolkit |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Marketing Toolkit. - [Success] |

|  |  |
| --- | --- |
| 17.2 | Mengubah tampilan folder menjadi List View |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah tampilan folder menjadi List View. - [Success] |

|  |  |
| --- | --- |
| 17.3 | Mengubah tampilan folder menjadi Grid View |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah tampilan folder menjadi Grid View. - [Success] |

|  |  |
| --- | --- |
| 17.4 | Membuka folder pada Marketing Toolkit |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka folder Marketing Toolkit. - [Success] |

|  |  |
| --- | --- |
| 17.5 | Mencari konten di dalam folder menggunakan Search Bar |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang sesuai dengan kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 17.6 | Mencari konten di dalam folder dengan keyword tidak valid |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 17.7 | Melihat detail konten Marketing Toolkit |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail konten Marketing Toolkit. - [Success] |

|  |  |
| --- | --- |
| 17.8 | Mengunduh lampiran pada konten Marketing Toolkit |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh lampiran ke perangkat. - [Success] |

|  |  |
| --- | --- |
| 17.9 | Berbagi lampiran pada konten Marketing Toolkit |
|  | ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pilihan aplikasi berbagi. - [Success] |

# **18. Modul Sales Force - Dashboard Sales Code**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 18.1 | Membuka halaman Dashboard Sales Code |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Dashboard Sales Code. - [Success] |

|  |  |
| --- | --- |
| 18.2 | Melihat detail Voa Realization |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail Voa Realization. - [Success] |

|  |  |
| --- | --- |
| 18.3 | Melihat Daftar Pipeline pada Voa Realization |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Daftar Pipeline. - [Success] |

|  |  |
| --- | --- |
| 18.4 | Melihat detail CIF Kelolaan |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail CIF Kelolaan. - [Success] |

|  |  |
| --- | --- |
| 18.5 | Melihat detail Realisasi Konek E-Channel |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail Realisasi Konek E-Channel. - [Success] |

|  |  |
| --- | --- |
| 18.6 | Melihat detail Realisasi Akuisisi Merchant |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail Realisasi Akuisisi Merchant. - [Success] |

|  |  |
| --- | --- |
| 18.7 | Melihat detail Eligible Upgrade to Prospera/Prioritas |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail Eligible Upgrade to Prospera & Prioritas. - [Success] |

# **19. Modul Kunjungan**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 19.1 | Membuka halaman Kunjungan |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Kunjungan beserta informasi Periode, ringkasan Realisasi & Target Visit, serta daftar riwayat kunjungan. - [Success] |

|  |  |
| --- | --- |
| 19.2 | Melakukan filter periode tanggal kunjungan |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memfilter dan menampilkan daftar data kunjungan sesuai rentang periode tanggal yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 19.3 | Melihat detail kunjungan |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Detail Kunjungan yang memuat peta lokasi, waktu, tipe kunjungan, dan nama nasabah pada tab Mulai Kunjungan maupun Selesai Kunjungan. - [Success] |

# **20. Modul Notifikasi**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 20.1 | Membuka halaman Notifikasi |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Notifikasi. - [Success] |

|  |  |
| --- | --- |
| 20.2 | Mencari notifikasi dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data notifikasi yang dicari. - [Success] |

|  |  |
| --- | --- |
| 20.3 | Mencari notifikasi dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 20.4 | Melihat data notifikasi Belum Dibaca |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data notifikasi belum dibaca. - [Success] |

|  |  |
| --- | --- |
| 20.5 | Melihat data notifikasi Diarsipkan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data notifikasi diarsipkan. - [Success] |

|  |  |
| --- | --- |
| 20.6 | Melihat detail notifikasi |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail notifikasi. - [Success] |

|  |  |
| --- | --- |
| 20.7 | Mengarsipkan notifikasi |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengarsipkan notifikasi. - [Success] |

|  |  |
| --- | --- |
| 20.8 | Membatalkan arsip notifikasi |
|  | ![](data:image/png;base64...) ![](data:image/png;base64...) ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan arsip notifikasi. - [Success] |