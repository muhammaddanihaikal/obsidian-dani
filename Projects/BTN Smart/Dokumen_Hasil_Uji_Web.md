---
tags:
  - UAT
  - HasilUji
  - BTN
  - Web
  - QA
date: 2026-10-22
project: BTN Smart
platform: Web
source_file: Dokumen_Hasil_Uji_Web_fixed2.docx
total_tc: 864
converter: markitdown
---

![](data:image/png;base64...)![A blue and red logo  Description automatically generated](data:image/jpeg;base64...)

Dokumen Hasil Uji - Unit Testing (UT)

BTN SMART v3

PT Bank Tabungan Negara Persero Tbk

Nama File : Dokumen Hasil UT - BTN SMART Corporate Banking CBD

**Informasi Dokumen**

|  |  |
| --- | --- |
| **Informasi Dokumen** | |
| **Nama Proyek** | BTN SMART Corporate Banking CBD |
| **Nama Aplikasi** | BTN SMART v3 |
| **Hasil Uji** | Unit Testing (UT) |
| **Versi** | 1.0 |
| **Nama File** | Dokumen Hasil Uji Unit Testing - BTN SMART Corporate Banking CBD |

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

[**Histori Perbaikan** 4](#_Toc242691263)

[**1. Modul Login** 6](#_Toc242691264)

[**2. Modul Profile** 21](#_Toc242691265)

[**3. Modul Notifikasi** 76](#_Toc242691266)

[**4. Modul Overview - Overview Fund** 86](#_Toc242691267)

[**5. Modul Overview - Overview Lend** 94](#_Toc242691268)

[**6. Modul Overview - Pengaturan Overview** 103](#_Toc242691269)

[**7. Modul User Authority - User** 105](#_Toc242691270)

[**8. Modul User Authority - Group Role** 116](#_Toc242691271)

[**9. Modul User Authority - Tipe Karyawan** 125](#_Toc242691272)

[**10. Modul User Authority - Hak Akses Role** 133](#_Toc242691273)

[**11. Modul User Authority - Keamanan Akun** 139](#_Toc242691274)

[**12. Modul Profile Nasabah & Sales - Sales** 176](#_Toc242691275)

[**13. Modul Profile Nasabah & Sales - Nasabah Perorangan** 185](#_Toc242691276)

[**14. Modul Bisnis dan Produk - Unit Bisnis** 200](#_Toc242691277)

[**15. Modul Bisnis dan Produk - Produk** 207](#_Toc242691278)

[**16. Modul Bisnis dan Produk - Program Produk** 222](#_Toc242691280)

[**17. Modul Kantor - Tipe Kantor** 230](#_Toc242691284)

[**18. Modul Kantor - Data Kantor** 235](#_Toc242691285)

[**19. Modul Menu Target** 242](#_Toc242691286)

[**20. Modul Upload Bulk - Upload Target Bulk** 245](#_Toc242691287)

[**21. Modul Upload Bulk - Bulk Import User** 259](#_Toc242691288)

[**22. Modul Upload Bulk - Bulk Import Prospek - Prospek Personal** 293](#_Toc242691289)

[**23. Modul Upload Bulk - Bulk Import Prospek - Prospek Lembaga** 296](#_Toc242691290)

[**24. Modul Lead Generation - Prospek Individu** 305](#_Toc242691291)

[**25. Modul Lead Generation - Prospek Lembaga** 312](#_Toc242691292)

[**26. Modul Lead Qualification - Aktifitas** 315](#_Toc242691293)

[**27. Modul Lead Qualification - Aktifitas Referal** 328](#_Toc242691294)

[**28. Modul List Prospek ETB** 335](#_Toc242691295)

[**29. Modul Menu Absent - Dashboard Absent** 345](#_Toc242691296)

[**30. Modul Menu Absent - Daily Absent** 355](#_Toc242691297)

[**31. Modul Menu Absent - Rekap Absent** 371](#_Toc242691298)

[**32. Modul Menu Absent - Approval Absent** 388](#_Toc242691299)

[**33. Modul Sales Tracking Activity - Dashboard Visit** 394](#_Toc242691300)

[**34. Modul Sales Tracking Activity - Client Visit List** 403](#_Toc242691301)

[**35. Modul Sales Tracking Activity - Rekap Visit** 414](#_Toc242691302)

[**36. Modul Sales Tracking Activity - Rekap Monthly Visit** 420](#_Toc242691303)

[**37. Modul Setting Absent - Attendance Spot** 423](#_Toc242691304)

[**38. Modul Setting Absent - Work Pattern** 442](#_Toc242691305)

[**39. Modul Setting Absent - Holiday** 466](#_Toc242691306)

[**40. Modul Sales Force - Sales code** 474](#_Toc242691307)

[**41. Modul Sales Force - Pipeline - Dashboard Validate Pipeline** 492](#_Toc242691308)

[**42. Modul Sales Force - Pipeline - Input Pipeline** 521](#_Toc242691309)

[**43. Modul Sales Force - Approval Target Growth** 536](#_Toc242691310)

[**44. Modul Sales Force - Approval Sales Code** 548](#_Toc242691311)

[**45. Modul Sales Force - CIF Kelolaan** 556](#_Toc242691312)

[**46. Modul Sales Force - Approval Cif Kelolaan** 571](#_Toc242691313)

[**47. Modul Sales Force - Produktivitas - Target Growth** 574](#_Toc242691314)

[**48. Modul Sales Force - Produktivitas - Target Produktivitas** 584](#_Toc242691315)

[**49. Modul Sales Force - Produktivitas - Bobot Produktivitas** 591](#_Toc242691316)

[**50. Modul Sales Force - Produktivitas - Realisasi Merchant** 598](#_Toc242691317)

[**51. Modul Sales Force - CIF Rebase** 604](#_Toc242691318)

[**52. Modul Sales Force - Report - Report Produktivitas** 611](#_Toc242691319)

[**53. Modul Sales Force - Dashboard Sales Force** 640](#_Toc242691320)

[**54. Modul Sales Force - Pipeline - Setting Role Validate Pipeline** 663](#_Toc242691321)

[**55. Modul Sales Force - Pipeline - Setting Validate Pipeline** 672](#_Toc242691322)

[**56. Modul Sales Force - Pipeline - Input komitmen** 678](#_Toc242691323)

[**57. Modul Kalender** 686](#_Toc242691324)

[**58. Modul Report Funding - Personal Funnel** 705](#_Toc242691325)

[**59. Modul Report Funding - Rekap Funnel** 709](#_Toc242691326)

[**60. Modul Report Funding - Pengaturan Funnel** 718](#_Toc242691328)

[**61. Modul Report Funding - Daily Sales Agenda** 728](#_Toc242691329)

[**62. Modul Report Lending - Personal Funnel** 747](#_Toc242691330)

[**63. Modul Report Lending - Rekap Funnel** 753](#_Toc242691331)

[**64. Modul Report Lending - Pengaturan Funnel** 760](#_Toc242691333)

[**65. Modul Report Lending - Daily Sales Agenda** 768](#_Toc242691334)

[**66. Modul Re-Assign dan Approval - Approval Non Banking** 788](#_Toc242691335)

[**67. Modul Re-Assign dan Approval - Re-Assign Prospek** 794](#_Toc242691336)

[**68. Modul Re-Assign dan Approval - Re-Assign Management** 801](#_Toc242691337)

[**69. Modul Export Center - Riwayat Export** 808](#_Toc242691338)

[**70. Modul Export Center - Persetujuan Export** 814](#_Toc242691339)

[**71. Modul Export Center - Aktivitas Export** 823](#_Toc242691340)

# **Histori Perbaikan**

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **No** | **Dibuat Oleh** | **Tangal** | **Modifikasi** | **Deskripsi** |
| 1.0 | Zegen Solusi Mandiri | 18 April 2024 |  |  |

# **1. Modul Login**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 1.1 | Membuka halaman Login |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan form Login Non Employee. - [Success] |

|  |  |
| --- | --- |
| 1.2 | Melakukan login dengan email dan password valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Verifikasi OTP. - [Success] |

|  |  |
| --- | --- |
| 1.3 | Melakukan login dengan email tidak terdaftar |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan email atau password tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.4 | Melakukan login dengan password salah |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan email atau password tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.5 | Melakukan login tanpa mengisi email |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi email wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 1.6 | Melakukan login tanpa mengisi password |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi password wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 1.7 | Melakukan login tanpa mengisi email dan password |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 1.8 | Melakukan verifikasi Email OTP |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil login ke Dashboard. - [Success] |

|  |  |
| --- | --- |
| 1.9 | Melakukan verifikasi Email OTP dengan kode tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan kode OTP tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.10 | Melakukan verifikasi TOTP |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil login ke Dashboard. - [Success] |

|  |  |
| --- | --- |
| 1.11 | Melakukan verifikasi TOTP dengan kode tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan kode TOTP tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.12 | Melakukan login menggunakan perangkat terpercaya |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil login tanpa verifikasi OTP. - [Success] |

|  |  |
| --- | --- |
| 1.13 | Menggunakan kode pemulihan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil login ke Dashboard. - [Success] |

|  |  |
| --- | --- |
| 1.14 | Menggunakan kode pemulihan yang tidak valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan Recovery Code tidak valid. - [Success] |

|  |  |
| --- | --- |
| 1.15 | Mengajukan Reset MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengajukan permintaan Reset MFA. - [Success] |

|  |  |
| --- | --- |
| 1.16 | Mengajukan Reset MFA tanpa mengisi alasan reset |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi alasan reset wajib diisi. - [Success] |

# **2. Modul Profile**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 2.1 | Membuka halaman profile |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman profile. - [Success] |

|  |  |
| --- | --- |
| 2.2 | Mengubah informasi pribadi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah data informasi pribadi. - [Success] |

|  |  |
| --- | --- |
| 2.3 | Mengubah informasi pribadi dengan tidak menginput data mandatory (negative test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert mandatory/wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 2.4 | Mengubah foto profile |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah foto profile. - [Success] |

|  |  |
| --- | --- |
| 2.5 | Mengubah profile dengan format yang tidak sesuai (Negative test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert format tidak sesuai. - [Success] |

|  |  |
| --- | --- |
| 2.6 | Mengubah kata sandi dengan data valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah kata sand. - [Success] |

|  |  |
| --- | --- |
| 2.7 | Menginput konfirmasi kata sandi berbeda dengan kata sandi baru (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi kata sandi tidak cocok. - [Success] |

|  |  |
| --- | --- |
| 2.8 | Menginput kata sandi dengan huruf kecil saja |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi persyaratan kata sandi. - [Success] |

|  |  |
| --- | --- |
| 2.9 | Menginput kata sandi dengan huruf kapital saja |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi persyaratan kata sandi. - [Success] |

|  |  |
| --- | --- |
| 2.10 | Menginput kata sandi kurang dari 8 karakter |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi persyaratan kata sandi. - [Success] |

|  |  |
| --- | --- |
| 2.11 | Menginput kata sandi tidak menggunakan angka |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi persyaratan kata sandi. - [Success] |

|  |  |
| --- | --- |
| 2.12 | Menginput kata sandi baru sama dengan kata sandi yang lama |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Gagal update password. - [Success] |

|  |  |
| --- | --- |
| 2.13 | Membuka halaman keamanan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Keamanan. - [Success] |

|  |  |
| --- | --- |
| 2.14 | Mengaktifkan MFA menggunakan metode TOTP scan barcode |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA menggunakan metode TOTP. - [Success] |

|  |  |
| --- | --- |
| 2.15 | Mengaktifkan MFA menggunakan metode TOTP menggunakan kode manual |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA menggunakan metode TOTP. - [Success] |

|  |  |
| --- | --- |
| 2.16 | Mengaktifkan MFA menggunakan metode TOTP dengan menginput kode OTP salah |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi kode OTP tidak sesuai. - [Success] |

|  |  |
| --- | --- |
| 2.17 | Mangaktifkan MFA menggunakan metode email OTP |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA menggunakan metode email OTP dan mendapatkan kode Cadangan. - [Success] |

|  |  |
| --- | --- |
| 2.18 | Mengaktifkan MFA menggunakan metode email OTP dengan mengirim ulang kode OTP |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  berhasil mengaktifkan MFA menggunakan kode yang dikirim ulang. - [Success] |

|  |  |
| --- | --- |
| 2.19 | Mengaktifkan MFA menggunakan metode email OTP dengan menginput kode otp yang salah |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi kode OTP tidak sesuai. - [Success] |

|  |  |
| --- | --- |
| 2.20 | Mengganti metode MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah metode MFA. - [Success] |

|  |  |
| --- | --- |
| 2.21 | Mengganti metode MFA dengan input password yang salah |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi password tidak valid. - [Success] |

|  |  |
| --- | --- |
| 2.22 | Melakukan recovery code |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data recovery code. - [Success] |

|  |  |
| --- | --- |
| 2.23 | Melakukan recovery code dengan input password yang salah |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi password tidak valid. - [Success] |

|  |  |
| --- | --- |
| 2.24 | Generate ulang recovery code |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendapatkan kode recovery baru. - [Success] |

|  |  |
| --- | --- |
| 2.25 | Menyalin semua recovery code |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyalin kode di halaman lain seperti note/word. - [Success] |

|  |  |
| --- | --- |
| 2.26 | mengunduh data Recovery code |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data recovery code. - [Success] |

|  |  |
| --- | --- |
| 2.27 | Melihat riwayat login |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data riwayat login. - [Success] |

|  |  |
| --- | --- |
| 2.28 | Data login berhasil |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data di riwayat login sebagai login berhasil. - [Success] |

|  |  |
| --- | --- |
| 2.29 | Data gagal login |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data di riwayat login sebagai login gagal. - [Success] |

|  |  |
| --- | --- |
| 2.30 | Lihat semua riwayat aktifitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan seluruh riwayat login. - [Success] |

|  |  |
| --- | --- |
| 2.31 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 2.32 | Melakukan search data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai yang di cari. - [Success] |

|  |  |
| --- | --- |
| 2.33 | Pengecekan Riwayat login sebelum mengaktifkan MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data riwayat login non aktif MFA. - [Success] |

|  |  |
| --- | --- |
| 2.34 | Pengecekan Riwayat login sesudah mengaktifkan MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data riwayat login MFA. - [Success] |

|  |  |
| --- | --- |
| 2.35 | pengecekan data logout |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data logout pada riwayat login. - [Success] |

|  |  |
| --- | --- |
| 2.36 | pengecekan data logout karena sesi habis |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data Riwayat login dengan label “sesi tidak aktif selama 15 menit”. - [Success] |

|  |  |
| --- | --- |
| 2.37 | Melihat perangkat terhubung |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan list data perangkat terhubung. - [Success] |

|  |  |
| --- | --- |
| 2.38 | Melihat detail perangkat terhubung |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail peraangkat terhubung. - [Success] |

|  |  |
| --- | --- |
| 2.39 | Percayai perangkat terhubung |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mempercayai perangkat dan menampilkan indikator perangkat terpercaya. - [Success] |

|  |  |
| --- | --- |
| 2.40 | Ganti nama perangkat |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah nama label perangkat pada perangkat terhubung dan Riwayat login. - [Success] |

|  |  |
| --- | --- |
| 2.41 | Putuskan perangkat terhubung |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memutuskan perangkat terhubung dan auto logout. - [Success] |

|  |  |
| --- | --- |
| 2.42 | Menghapus perangkat terhubung |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus perangkat yang terhubung. - [Success] |

|  |  |
| --- | --- |
| 2.43 | Putuskan semua perangkat terhubung |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Semua perangkat terhubung akan auto logout kecuali “perangkat ini”. - [Success] |

|  |  |
| --- | --- |
| 2.44 | Pengecekan masa berlaku percayai perangkat |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Perangkat yang dipercayai hanya berlaku 30 hari. - [Success] |

|  |  |
| --- | --- |
| 2.45 | Pengecekan perangkat terhubung sebelum mengaktifkan MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data perangkat terhubung non aktif MFA. - [Success] |

|  |  |
| --- | --- |
| 2.46 | Pengecekan perangkat terhubung sesudah mengaktifkan MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  menampilkan data perangkat terhubung user MFA. - [Success] |

|  |  |
| --- | --- |
| 2.47 | Pengecekan perangkat terhubung berbagai browser (chrome, edge, mozila, dll) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data perangkat terhubung berbagai browser. - [Success] |

# **3. Modul Notifikasi**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 3.1 | Membuka notifikasi pada header |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar notifikasi terbaru. - [Success] |

|  |  |
| --- | --- |
| 3.2 | Mencari notifikasi dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data notifikasi yang dicari. - [Success] |

|  |  |
| --- | --- |
| 3.3 | Mencari notifikasi dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 3.4 | Melihat data notifikasi Belum Dibaca |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data notifikasi belum dibaca. - [Success] |

|  |  |
| --- | --- |
| 3.5 | Menandai semua notifikasi telah dibaca |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menandai seluruh notifikasi telah dibaca. - [Success] |

|  |  |
| --- | --- |
| 3.6 | Melihat semua notifikasi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan seluruh daftar notifikasi. - [Success] |

|  |  |
| --- | --- |
| 3.7 | Melihat data notifikasi Diarsipkan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data notifikasi diarsipkan. - [Success] |

|  |  |
| --- | --- |
| 3.8 | Melihat detail notifikasi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Detail Notifikasi. - [Success] |

|  |  |
| --- | --- |
| 3.9 | Mengarsipkan notifikasi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengarsipkan notifikasi. - [Success] |

|  |  |
| --- | --- |
| 3.10 | Membatalkan arsip notifikasi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
|  | **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan arsip notifikasi. - [Success] |

# **4. Modul Overview - Overview Fund**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 4.1 | Membuka halaman Overview Funding |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Overview Funding. - [Success] |

|  |  |
| --- | --- |
| 4.2 | Melakukan filter data Overview Funding |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Overview Funding yang sesuai dengan filter. - [Success] |

|  |  |
| --- | --- |
| 4.3 | Melakukan filter data Overview Funding tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Tampil pesan peringatan bahwa field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 4.4 | Mengubah ukuran (perbesar/perkecil) tampilan widget pada Overview Funding |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memperbesar atau memperkecil ukuran tampilan widget. - [Success] |

|  |  |
| --- | --- |
| 4.5 | Me-refresh data pada halaman Overview Funding |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memuat ulang (refresh) data terbaru pada seluruh widget. - [Success] |

# **5. Modul Overview - Overview Lend**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 5.1 | Membuka halaman Overview Lending |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Overview Lending. - [Success] |

|  |  |
| --- | --- |
| 5.2 | Melakukan filter data Overview Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Overview Lending yang sesuai dengan filter. - [Success] |

|  |  |
| --- | --- |
| 5.3 | Melakukan filter data Overview Lending tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Tampil pesan peringatan bahwa field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 5.4 | Mengubah ukuran (perbesar/perkecil) tampilan widget pada Overview Lending |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memperbesar atau memperkecil ukuran tampilan widget. - [Success] |

|  |  |
| --- | --- |
| 5.5 | Me-refresh data pada halaman Overview Lending |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memuat ulang (refresh) data terbaru pada seluruh widget. - [Success] |

# **6. Modul Overview - Pengaturan Overview**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 6.1 | Membuka halaman Pengaturan Overview |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Pengaturan Overview. - [Success] |

|  |  |
| --- | --- |
| 6.2 | Mengubah Role pada Pengaturan Overview |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan Role pada Pengaturan Overview. - [Success] |

|  |  |
| --- | --- |
| 6.3 | Mengubah Role pada Pengaturan Overview tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field Role wajib diisi. - [Success] |

# **7. Modul User Authority - User**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 7.1 | Membuka halaman User |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman User. - [Success] |

|  |  |
| --- | --- |
| 7.2 | Mencari data User dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 7.3 | Mencari data User dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 7.4 | Menambahkan data User |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data user. - [Success] |

|  |  |
| --- | --- |
| 7.5 | Menambahkan data User tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 7.6 | Mengubah data User |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data user. - [Success] |

|  |  |
| --- | --- |
| 7.7 | Mengubah data User tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 7.8 | Menghapus data User |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data user. - [Success] |

|  |  |
| --- | --- |
| 7.9 | Mengekspor data User |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export data user. - [Success] |

# **8. Modul User Authority - Group Role**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 8.1 | Membuka halaman Group Role |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Group Role. - [Success] |

|  |  |
| --- | --- |
| 8.2 | Mencari data Group Role dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 8.3 | Mencari data Group Role dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 8.4 | Menambahkan data Group Role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data group role. - [Success] |

|  |  |
| --- | --- |
| 8.5 | Menambahkan data Group Role tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 8.6 | Mengubah data Group Role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data group role. - [Success] |

|  |  |
| --- | --- |
| 8.7 | Mengubah data Group Role tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 8.8 | Menghapus data Group Role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data group role. - [Success] |

|  |  |
| --- | --- |
| 8.9 | Mengekspor data Group Role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export data group role. - [Success] |

# **9. Modul User Authority - Tipe Karyawan**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 9.1 | Membuka halaman Tipe Karyawan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Tipe Karyawan. - [Success] |

|  |  |
| --- | --- |
| 9.2 | Mencari data Tipe Karyawan dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 9.3 | Mencari data Tipe Karyawan dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 9.4 | Menambahkan data Tipe Karyawan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data tipe karyawan. - [Success] |

|  |  |
| --- | --- |
| 9.5 | Menambahkan data Tipe Karyawan tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 9.6 | Mengubah data Tipe Karyawan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data tipe karyawan. - [Success] |

|  |  |
| --- | --- |
| 9.7 | Mengubah data Tipe Karyawan tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 9.8 | Menghapus data Tipe Karyawan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data tipe karyawan. - [Success] |

# **10. Modul User Authority - Hak Akses Role**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 10.1 | Membuka halaman Hak Akses Role |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Hak Akses Role beserta daftar data role. - [Success] |

|  |  |
| --- | --- |
| 10.2 | Mencari data Role dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 10.3 | Mencari data Role dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 10.4 | Mengubah Hak Akses Role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan hak akses role. - [Success] |

|  |  |
| --- | --- |
| 10.5 | Mengubah Hak Akses Role tanpa memilih hak akses |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi hak akses wajib dipilih. - [Success] |

|  |  |
| --- | --- |
| 10.6 | Mencari data Hak Akses dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan hak akses sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 10.7 | Mencari data Hak Akses dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

# **11. Modul User Authority - Keamanan Akun**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 11.1 | Membuka halaman Keamanan Akun |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Keamanan Akun beserta informasi ringkasan dan daftar akun. - [Success] |

|  |  |
| --- | --- |
| 11.2 | Melihat informasi Total Pengguna |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan jumlah total pengguna. - [Success] |

|  |  |
| --- | --- |
| 11.3 | Melihat informasi MFA Aktif |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan jumlah dan persentase MFA aktif. - [Success] |

|  |  |
| --- | --- |
| 11.4 | Melihat informasi Permintaan Reset |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan jumlah permintaan reset MFA. - [Success] |

|  |  |
| --- | --- |
| 11.5 | Melihat informasi User Aktif |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan jumlah user aktif. - [Success] |

|  |  |
| --- | --- |
| 11.6 | Melihat informasi Login Gagal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan jumlah login gagal dalam 24 jam. - [Success] |

|  |  |
| --- | --- |
| 11.7 | Melihat informasi Perangkat Terpercaya |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan persentase perangkat terpercaya. - [Success] |

|  |  |
| --- | --- |
| 11.8 | Mencari akun dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 11.9 | Mencari akun dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 11.10 | Melihat detail akun |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail akun. - [Success] |

|  |  |
| --- | --- |
| 11.11 | Mereset MFA pengguna |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset MFA pengguna. - [Success] |

|  |  |
| --- | --- |
| 11.12 | Mereset MFA tanpa mengisi alasan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.13 | Mengaktifkan MFA Email |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA Email. - [Success] |

|  |  |
| --- | --- |
| 11.14 | Mengaktifkan MFA Email tanpa mengisi alasan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.15 | Mengaktifkan MFA TOTP |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengaktifkan MFA TOTP. - [Success] |

|  |  |
| --- | --- |
| 11.16 | Mengaktifkan MFA TOTP tanpa mengisi alasan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.17 | Mengekspor data akun |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 11.18 | Membuka halaman Permintaan Reset MFA |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar Permintaan Reset MFA di dalam tabel. - [Success] |

|  |  |
| --- | --- |
| 11.19 | Mencari permintaan reset MFA dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 11.20 | Mencari permintaan reset MFA dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 11.21 | Melakukan filter data permintaan reset MFA |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data permintaan reset MFA sesuai kriteria filter. - [Success] |

|  |  |
| --- | --- |
| 11.22 | Mereset filter data permintaan reset MFA |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengembalikan filter ke kondisi default dan menampilkan seluruh data. - [Success] |

|  |  |
| --- | --- |
| 11.23 | Melihat detail permintaan reset MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail permintaan reset MFA. - [Success] |

|  |  |
| --- | --- |
| 11.24 | Menyetujui permintaan reset MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyetujui permintaan reset MFA. - [Success] |

|  |  |
| --- | --- |
| 11.25 | Menyetujui permintaan reset MFA tanpa mengisi remark |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.26 | Menolak permintaan reset MFA |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menolak permintaan reset MFA. - [Success] |

|  |  |
| --- | --- |
| 11.27 | Menolak permintaan reset MFA tanpa mengisi remark |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 11.28 | Membuka halaman Perangkat & Sesi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar Perangkat & Sesi di dalam tabel. - [Success] |

|  |  |
| --- | --- |
| 11.29 | Mencari perangkat dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 11.30 | Mencari perangkat dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 11.31 | Melakukan filter data perangkat & sesi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data perangkat & sesi sesuai filter. - [Success] |

|  |  |
| --- | --- |
| 11.32 | Mereset filter data perangkat & sesi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengembalikan filter ke kondisi default. - [Success] |

|  |  |
| --- | --- |
| 11.33 | Melihat detail perangkat |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail perangkat. - [Success] |

|  |  |
| --- | --- |
| 11.34 | Mengekspor data perangkat |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 11.35 | Membuka halaman Log Aktivitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Log Aktivitas. - [Success] |

|  |  |
| --- | --- |
| 11.36 | Mencari log aktivitas dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 11.37 | Mencari log aktivitas dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 11.38 | Melakukan filter log aktivitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter. - [Success] |

|  |  |
| --- | --- |
| 11.39 | Mereset filter log aktivitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengembalikan filter ke nilai default. - [Success] |

|  |  |
| --- | --- |
| 11.40 | Melihat detail log aktivitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail log aktivitas. - [Success] |

# **12. Modul Profile Nasabah & Sales - Sales**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 12.1 | Membuka halaman Profile Sales |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Profile Sales. - [Success] |

|  |  |
| --- | --- |
| 12.2 | Mencari data Sales dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 12.3 | Mencari data Sales dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 12.4 | Melakukan filter data Sales dengan mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Sales yang difilter sesuai dengan Kategori dan Role yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 12.5 | Melakukan filter data Sales tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan error validasi 'Kategori dibutuhkan!' dan 'Role dibutuhkan!'. - [Success] |

|  |  |
| --- | --- |
| 12.6 | Mengekspor (Export) data Sales |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 12.7 | Melihat detail Profile Sales |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Detail Sales yang memuat informasi Performa, Staging Prospek, Product Ownership, dan Aktivitas Terakhir. - [Success] |

|  |  |
| --- | --- |
| 12.8 | Mengubah periode filter (Bulan/Tahun) pada grafik Staging Prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah dropdown periode dan data pada container Staging Prospek berhasil difilter menyesuaikan periode yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 12.9 | Melihat histori Aktivitas Terakhir secara keseluruhan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan histori Aktivitas Terakhir secara keseluruhan. - [Success] |

# **13. Modul Profile Nasabah & Sales - Nasabah Perorangan**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 13.1 | Membuka halaman Nasabah Perorangan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Nasabah Perorangan. - [Success] |

|  |  |
| --- | --- |
| 13.2 | Mencari data Nasabah dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword pencarian. - [Success] |

|  |  |
| --- | --- |
| 13.3 | Mencari data Nasabah dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 13.4 | Melihat detail Nasabah Perorangan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Detail Nasabah yang memuat informasi detail nasabah serta tab Produk terpilih secara default. - [Success] |

|  |  |
| --- | --- |
| 13.5 | Mencari data pada tab Produk dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Produk sesuai keyword pencarian. - [Success] |

|  |  |
| --- | --- |
| 13.6 | Mencari data pada tab Produk dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan pada tab Produk. - [Success] |

|  |  |
| --- | --- |
| 13.7 | Mengekspor (Export) data Produk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export data Produk. - [Success] |

|  |  |
| --- | --- |
| 13.8 | Membuka tab Aktivitas Sales |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka tab Aktivitas Sales dan menampilkan tabel histori Aktivitas Sales. - [Success] |

|  |  |
| --- | --- |
| 13.9 | Mencari data pada tab Aktivitas Sales dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Aktivitas Sales sesuai keyword pencarian. - [Success] |

|  |  |
| --- | --- |
| 13.10 | Mencari data pada tab Aktivitas Sales dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan pada tab Aktivitas Sales. - [Success] |

|  |  |
| --- | --- |
| 13.11 | Mengekspor (Export) data Aktivitas Sales |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export Aktivitas Sales. - [Success] |

|  |  |
| --- | --- |
| 13.12 | Melihat detail Aktivitas Sales pada kolom Action |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data pribadi nasabah. - [Success] |

|  |  |
| --- | --- |
| 13.13 | Membuka tab Daftar Rekening |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka tab Daftar Rekening dan menampilkan tabel Daftar Rekening nasabah. - [Success] |

|  |  |
| --- | --- |
| 13.14 | Mencari data pada tab Daftar Rekening dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Daftar Rekening sesuai keyword pencarian. - [Success] |

|  |  |
| --- | --- |
| 13.15 | Mencari data pada tab Daftar Rekening dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan pada tab Daftar Rekening. - [Success] |

|  |  |
| --- | --- |
| 13.16 | Melihat detail load saldo rekening |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pop-up modal 'Detail Load Saldo' yang memuat grafik pergerakan saldo serta rincian nominal saldo per bulan. - [Success] |

|  |  |
| --- | --- |
| 13.17 | Mengekspor (Export) data Daftar Rekening |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export Daftar Rekening. - [Success] |

# **14. Modul Bisnis dan Produk - Unit Bisnis**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 14.1 | Membuka halaman Unit Bisnis |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Unit Bisnis. - [Success] |

|  |  |
| --- | --- |
| 14.2 | Mencari data Unit Bisnis dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai pencarian. - [Success] |

|  |  |
| --- | --- |
| 14.3 | Mencari data Unit Bisnis dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data kosong. - [Success] |

|  |  |
| --- | --- |
| 14.4 | Menambahkan data Unit Bisnis |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan unit bisnis baru. - [Success] |

|  |  |
| --- | --- |
| 14.5 | Menambahkan data Unit Bisnis tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 14.6 | Mengubah data Unit Bisnis |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan. - [Success] |

|  |  |
| --- | --- |
| 14.7 | Mengubah data Unit Bisnis tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 14.8 | Menghapus data Unit Bisnis |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus unit bisnis. - [Success] |

|  |  |
| --- | --- |
| 14.9 | Mengekspor data Unit Bisnis |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **15. Modul Bisnis dan Produk - Produk**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 15.1 | Membuka halaman Produk |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Produk. - [Success] |

|  |  |
| --- | --- |
| 15.2 | Mencari data Produk dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai pencarian. - [Success] |

|  |  |
| --- | --- |
| 15.3 | Mencari data Produk dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data kosong. - [Success] |

|  |  |
| --- | --- |
| 15.4 | Menambahkan data Produk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Produk baru. - [Success] |

|  |  |
| --- | --- |
| 15.5 | Menambahkan data Produk tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 15.6 | Mengubah data Produk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan. - [Success] |

|  |  |
| --- | --- |
| 15.7 | Mengubah data Produk tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 15.8 | Menghapus data Produk secara massal (Bulk Delete) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data Produk yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 15.9 | Mengekspor data Produk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **16. Modul Bisnis dan Produk - Program Produk**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 16.1 | Membuka halaman Program Produk |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Program Produk. - [Success] |

|  |  |
| --- | --- |
| 16.2 | Mencari data Program Produk dengan keyword valid |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai pencarian. - [Success] |

|  |  |
| --- | --- |
| 16.3 | Mencari data Program Produk dengan keyword tidak valid |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data kosong. - [Success] |

|  |  |
| --- | --- |
| 16.4 | Menambahkan data Program Produk |
| ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Program Produk baru. - [Success] |

|  |  |
| --- | --- |
| 16.5 | Menambahkan data Program Produk tanpa mengisi field mandatory |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 16.6 | Mengubah data Program Produk |
| ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan. - [Success] |

|  |  |
| --- | --- |
| 16.7 | Mengubah data Program Produk tanpa mengisi field mandatory |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 16.8 | Menghapus data Program Produk secara massal (Bulk Delete) |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data Program Produk yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 16.9 | Mengekspor data Program Produk |
| ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 16.10 | Melakukan validasi data hasil export |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data pada excel sesuai dengan data pada tabel. - [Success] |

# **17. Modul Kantor - Tipe Kantor**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 17.1 | Membuka halaman Tipe Kantor |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Tipe Kantor. - [Success] |

|  |  |
| --- | --- |
| 17.2 | Mencari data Tipe Kantor dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar data Tipe Kantor. - [Success] |

|  |  |
| --- | --- |
| 17.3 | Mencari data Tipe Kantor dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Tipe Kantor sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 17.4 | Menambahkan data Tipe Kantor |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 17.5 | Menambahkan data Tipe Kantor tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan data Tipe Kantor. - [Success] |

|  |  |
| --- | --- |
| 17.6 | Mengubah data Tipe Kantor |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan error validasi mandatory. - [Success] |

|  |  |
| --- | --- |
| 17.7 | Mengubah data Tipe Kantor tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah data Tipe Kantor. - [Success] |

|  |  |
| --- | --- |
| 17.8 | Menghapus data Tipe Kantor secara massal (Bulk Delete) |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data Tipe Kantor. - [Success] |

# **18. Modul Kantor - Data Kantor**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 18.1 | Membuka halaman Data Kantor |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Data Kantor. - [Success] |

|  |  |
| --- | --- |
| 18.2 | Mencari data kantor dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar Data Kantor. - [Success] |

|  |  |
| --- | --- |
| 18.3 | Mencari data kantor dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai pencarian. - [Success] |

|  |  |
| --- | --- |
| 18.4 | Menambahkan data kantor |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data kosong. - [Success] |

|  |  |
| --- | --- |
| 18.5 | Menambahkan data kantor tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data kantor baru. - [Success] |

|  |  |
| --- | --- |
| 18.6 | Mengubah data kantor |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 18.7 | Mengubah data kantor tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan. - [Success] |

|  |  |
| --- | --- |
| 18.8 | Menghapus data kantor secara massal (Bulk Delete) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan validasi wajib diisi dan data tidak disimpan. - [Success] |

|  |  |
| --- | --- |
| 18.9 | Mengekspor data kantor |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **19. Modul Menu Target**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 19.1 | Membuka halaman menu target |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman menu target. - [Success] |

|  |  |
| --- | --- |
| 19.2 | Filter data |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data target sesuai dengan filter yang di pilih. - [Success] |

|  |  |
| --- | --- |
| 19.3 | Mengosongkan semua filter mandatory |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert pada setiap filter mandatory dengan informasi 'dibutuhkan'. - [Success] |

|  |  |
| --- | --- |
| 19.4 | Set data target untuk semua sales dalam satu kantor cabang |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan dan mengatur data target semua sales di kc tersebut sesuai dengan bisnis unit dan produk yang di pilih, menampilkan popup 'Sukses menyimpan data target'. - [Success] |

|  |  |
| --- | --- |
| 19.5 | Set data target tanpa klik button Simpan |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil set ke semua sales tetapi data nya tidak tersimpan. - [Success] |

|  |  |
| --- | --- |
| 19.6 | Set data target untuk satu sales |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan dan mengatur data target sales tersebut, menampilkan popup 'Sukses menyimpan data target' - [Success] |

# **20. Modul Upload Bulk - Upload Target Bulk**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 20.1 | Membuka halaman Upload Target Bulk |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Upload target bulk. - [Success] |

|  |  |
| --- | --- |
| 20.2 | Download Template upload target bulk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  File excel dapat di buka. - [Success] |

|  |  |
| --- | --- |
| 20.3 | Download Template upload bulk tanpa memilih bisnis unit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Tidak bisa mengunduh dan menampilkan alert 'Bisnis Unit wajib dipilih sebelum download template'. - [Success] |

|  |  |
| --- | --- |
| 20.4 | Upload Target bulk dengan data yang valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload data target secara bulk, dan status nya Selesai. - [Success] |

|  |  |
| --- | --- |
| 20.5 | Upload Target bulk dengan template yang tidak sesuai |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan status Template Tidak Valid dan gagal upload bulk data tidak tersimpan atau terupdate. - [Success] |

|  |  |
| --- | --- |
| 20.6 | Menampilkan detail batch |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data detail. - [Success] |

|  |  |
| --- | --- |
| 20.7 | Download source File |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data source berhasil didownload. - [Success] |

|  |  |
| --- | --- |
| 20.8 | Menampilkan preview data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data hasil upload dan penjelasan jika terdapat validasi error pada file yang diupload. - [Success] |

|  |  |
| --- | --- |
| 20.9 | Menghapus batch data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data berhasil dihapus. - [Success] |

|  |  |
| --- | --- |
| 20.10 | Download error file |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload error file. - [Success] |

|  |  |
| --- | --- |
| 20.11 | Batalkan batch |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan batch. - [Success] |

|  |  |
| --- | --- |
| 20.12 | Upload ulang file gagal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload ulang file. - [Success] |

|  |  |
| --- | --- |
| 20.13 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 20.14 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data seuai filter yang dipilih. - [Success] |

# **21. Modul Upload Bulk - Bulk Import User**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 21.1 | Membuka halaman Bulk Import User |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Bulk Import User. - [Success] |

|  |  |
| --- | --- |
| 21.2 | Download Template upload bulk User |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  File excel dapat di buka. - [Success] |

|  |  |
| --- | --- |
| 21.3 | Upload file data upload bulk user dengan data yang valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload data user secara bulk dengan status Selesai, kemudian data akan masuk pada menu user. - [Success] |

|  |  |
| --- | --- |
| 21.4 | Upload file dengan no telepon bukan berupa angka |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi error 'nomor telepon harus berupa angka'. - [Success] |

|  |  |
| --- | --- |
| 21.5 | Upload file dengan email yang sudah terdaftar |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan validasi error 'email sudah terdaftar'. - [Success] |

|  |  |
| --- | --- |
| 21.6 | Menginput email tanpa spesial karakter |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Indikator One special character tidak terpenuhi dan button Save Password tetap disabled. - [Success] |

# **22. Modul Upload Bulk - Bulk Import Prospek - Prospek Personal**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 22.1 | Membuka halaman upload bulk prospek personal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan halaman bulk import prospek personal - - [Success] |

|  |  |
| --- | --- |
| 22.2 | Download Template upload bulk prospek personal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil File excel dapat di buka - - [Success] |

|  |  |
| --- | --- |
| 22.3 | Upload file prospek personal dengan data yang valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload data prospek personal secara bulk, dan status nya Selesai - - [Success] |

|  |  |
| --- | --- |
| 22.4 | Validasi data yang berhasil di upload |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan semua informasi data prospek yang sesuai dengan yang di upload di menu Bulk Import Prospek Personal dengan keterangan 'Registered based on excel' - - [Success] |

|  |  |
| --- | --- |
| 22.5 | Upload file prospek dengan template yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil upload dengan status 'Template Tidak Valid' dan data tidak tersimpan - - [Success] |

|  |  |
| --- | --- |
| 22.6 | Tidak menginput kolom data mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'Wajid diisi' pada halaman preview data dan dokumen error. data prospek tidak tersimpan - - [Success] |

|  |  |
| --- | --- |
| 22.7 | Menginput email yang tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil upload file dengan status 'Validasi Gagal' dan menampilkan informasi validation error 'Format email tidak valid' pada halaman preview data dan dokumen error. data prospek tidak tersimpan - - [Success] |

|  |  |
| --- | --- |
| 22.8 | Menginput no CIF yang tidak valid untuk nasabah ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'no CIF tidak ditemukan' pada halaman preview data dan dokumen error. data prospek tidak tersimpan - - [Success] |

|  |  |
| --- | --- |
| 22.9 | Menginput tanggal aktivitas (call, open account, dan top up) sebelum tanggal prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan informasi 'Tanggal call tidak boleh sebelum tanggal prospek', 'Tanggal Open Account tidak boleh sebelum tanggal prospek' , 'Tanggal Top up tidak boleh sebelum tanggal prospek' pada masing masing kolom - - [Success] |

|  |  |
| --- | --- |
| 22.10 | Validasi Format tanggal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan informasi 'Format tanggal harus DD-MM-YYYY' - - [Success] |

|  |  |
| --- | --- |
| 22.11 | Validasi input Potensi dan Jumlah Dana Masuk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan informasi 'Jumlah dana masuk (Top Up) harus angka' - - [Success] |

|  |  |
| --- | --- |
| 22.12 | Membatalkan upload data prospek personal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan upload bulk data prospek personal, status nya menjadi 'Dibatalkan' - - [Success] |

|  |  |
| --- | --- |
| 22.13 | Pagination di Preview Data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan pagination yang di pilih - - [Success] |

|  |  |
| --- | --- |
| 22.14 | Pindah Halaman di Preview Data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman sesuai dengan angka halaman yang di input - - [Success] |

|  |  |
| --- | --- |
| 22.15 | Mencari data berdasarkan batch id upload bulk prospek personal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data upload bulk prospek personal sesuai dengan batch id yang di cari - - [Success] |

|  |  |
| --- | --- |
| 22.16 | Filter status upload bulk prospek personal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data upload bulk prospek personal sesuai dengan status yang di pilih - - [Success] |

|  |  |
| --- | --- |
| 22.17 | Validasi data yang berhasil di upload |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan semua informasi data prospek yang sesuai dengan yang di upload di menu Bulk Import Prospek lembaga dengan keterangan 'Registered based on excel' - - [Success] |

|  |  |
| --- | --- |
| 22.18 | Upload file prospek dengan template yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan status Template Tidak Valid dan gagal upload bulk data tidak tersimpan - - [Success] |

# **23. Modul Upload Bulk - Bulk Import Prospek - Prospek Lembaga**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 23.1 | Membuka halaman upload bulk Prospek Lembaga |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan halaman bulk import prospek lembaga - - [Success] |

|  |  |
| --- | --- |
| 23.2 | Download Template upload bulk Prospek Lembaga |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil File excel dapat di buka - - [Success] |

|  |  |
| --- | --- |
| 23.3 | Upload file Prospek Lembaga dengan data yang valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload data prospek lembaga secara bulk, dan status nya Selesai - - [Success] |

|  |  |
| --- | --- |
| 23.4 | Menginput no CIF yang tidak valid untuk nasabah lembaga ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil upload file dengan status 'Validasi gagal', menampilkan informasi validation error 'no CIF tidak ditemukan' pada halaman preview data dan dokumen error. data prospek tidak tersimpan - - [Success] |

|  |  |
| --- | --- |
| 23.5 | Membatalkan upload data Prospek Lembaga |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan upload bulk data prospek lembaga, status nya menjadi 'Dibatalkan' - - [Success] |

|  |  |
| --- | --- |
| 23.6 | Mencari data berdasarkan batch id upload bulk Prospek Lembaga |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data upload bulk prospek lembaga sesuai dengan batch id yang di cari - - [Success] |

|  |  |
| --- | --- |
| 23.7 | Filter status upload bulk Prospek Lembaga |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data upload bulk prospek lembaga sesuai dengan status yang di pilih - - [Success] |

# **24. Modul Lead Generation - Prospek Individu**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 24.1 | Membuka halaman prospek individu |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman input prospek individu Step 1. - [Success] |

|  |  |
| --- | --- |
| 24.2 | Menginput data prospek individu step 1 |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan form inputan prospek individu step 2. - [Success] |

|  |  |
| --- | --- |
| 24.3 | Menginput huruf di field nomor telepon |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan informasi 'Nomor telepon tidak valid'. - [Success] |

|  |  |
| --- | --- |
| 24.4 | Menginput nomor telepon kurang dari 10 digit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan informasi 'Panjang nomor telepon minimal 10 digit angka'. - [Success] |

|  |  |
| --- | --- |
| 24.5 | Menginput huruf di field nomor KTP |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan informasi 'Nomor KTP tidak valid, harus berupa angka'. - [Success] |

|  |  |
| --- | --- |
| 24.6 | Menginput angka di field nomor KTP kurang dari 16 digit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan informasi ' Panjang nomor KTP minimal 16'. - [Success] |

|  |  |
| --- | --- |
| 24.7 | Tidak menginput field mandatory step 1 (nama nasabah dan nomor telepon) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert 'nama nasabah / lembaga belum di masukkan' dan 'Nomor telepon belum dimasukkan'. - [Success] |

|  |  |
| --- | --- |
| 24.8 | Menginput data prospek step 2 |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman step 3 (Pekerjaan Nasabah). - [Success] |

|  |  |
| --- | --- |
| 24.9 | Menginput data prospek step 3 |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman step 3 (Pekerjaan Nasabah). - [Success] |

|  |  |
| --- | --- |
| 24.10 | Menginput data step 4 |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data pekerjaan dan menampilkan form input data step 4. - [Success] |

|  |  |
| --- | --- |
| 24.11 | Melakukan reset data prospek yang sudah di input |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengosongkan semua field yang sudah di input dari step 1 sampai 4. - [Success] |

# **25. Modul Lead Generation - Prospek Lembaga**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 25.1 | Membuka halaman prospek lembaga |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman input prospek lembaga step 1. - [Success] |

|  |  |
| --- | --- |
| 25.2 | Menginput data prospek lembaga step 1 |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman input data step 2. - [Success] |

|  |  |
| --- | --- |
| 25.3 | Menginput data prospek lembaga step 2 |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman input data prospek lembaga step 3. - [Success] |

|  |  |
| --- | --- |
| 25.4 | Menginput data step 3 |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menginput prospek dan data akan tampil pada menu lead qualification aktifitas. - [Success] |

# **26. Modul Lead Qualification - Aktifitas**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 26.1 | Membuka halaman Aktifitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Aktifitas. - [Success] |

|  |  |
| --- | --- |
| 26.2 | Filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data aktifitas prospek sesuai dengan filter yang telah di pilih. - [Success] |

|  |  |
| --- | --- |
| 26.3 | Melihat detail prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 26.4 | Mengubah data prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data nasabah. - [Success] |

|  |  |
| --- | --- |
| 26.5 | Melakukan aktifitas marketing (Call) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data aktifitas marketing call. menampilkan popup 'Sukses update call nasabah'. informasi masuk pada log staging call dan log aktifitas kemudian staging berubah dari registered menjadi call. - [Success] |

|  |  |
| --- | --- |
| 26.6 | Melakukan aktifitas marketing prospek (Call) dengan status 'nasabah menolak' |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan popup alert 'Anda tidak dapat memindahkan dari stage Ditolak ke Call'. - [Success] |

|  |  |
| --- | --- |
| 26.7 | Melakukan call dengan menambahkan pengingat |
| ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data aktivitas call nasabah dan sistem otomatis membuat pengingat (tugas) pada section Tugas Terkait / Kalender. - [Success] |

|  |  |
| --- | --- |
| 26.8 | Validasi data visit in prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail data yang sesuai dengan status dan deskripsi visit yang di input sales. - [Success] |

|  |  |
| --- | --- |
| 26.9 | Melakukan aktifitas marketing open account |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data NOA Open Account, menampilkan popup 'berhasil melakukan input data open account sukses' dan status prospek atau staging berubah menjadi Pembukaan. - [Success] |

|  |  |
| --- | --- |
| 26.10 | Menginput huruf pada field nomor rekening di form Input data NOA Open Account |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Karakter huruf tidak dapat diinput ke field Nomor Rekening. Field tetap kosong atau hanya menerima karakter numerik. - [Success] |

|  |  |
| --- | --- |
| 26.11 | Melakukan aktifitas marketing ETB (Top up Dana ) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menginput remark. - [Success] |

|  |  |
| --- | --- |
| 26.12 | Tidak menginput field mandatory pada halaman Dana Top Up |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert pada setiap field mandatory bahwa field tersebut dibutuhkan untuk diisi. - [Success] |

|  |  |
| --- | --- |
| 26.13 | Membatalkan prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan prospek, muncul popup 'Prospek telah dibatalkan' dan staging berubah menjadi Batal. - [Success] |

|  |  |
| --- | --- |
| 26.14 | Membuka halaman Aktifitas Marketing prospek Lending |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Aktifitas Marketing prospek Lending. - [Success] |

|  |  |
| --- | --- |
| 26.15 | Melakukan aktifitas marketing prospek Lending (Call) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data aktifitas call nasabah Lending. - [Success] |

|  |  |
| --- | --- |
| 26.16 | Validasi data visit prospek Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data visit nasabah Lending yang sesuai. - [Success] |

|  |  |
| --- | --- |
| 26.17 | Validasi data Proses Pemeriksaan prospek Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data proses pemeriksaan prospek Lending. - [Success] |

|  |  |
| --- | --- |
| 26.18 | Validasi data Proses Verifikasi dan Analisa prospek Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data proses verifikasi dan analisa prospek Lending. - [Success] |

|  |  |
| --- | --- |
| 26.19 | Validasi data Persetujuan Kredit prospek Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data persetujuan kredit prospek Lending. - [Success] |

|  |  |
| --- | --- |
| 26.20 | Validasi data Realisasi/Pencairan Kredit prospek Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data realisasi/pencairan kredit prospek Lending. - [Success] |

|  |  |
| --- | --- |
| 26.21 | Validasi data Batal prospek Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data pembatalan prospek Lending. - [Success] |

|  |  |
| --- | --- |
| 26.22 | Validasi data Ditolak prospek Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data penolakan prospek Lending. - [Success] |

# **27. Modul Lead Qualification - Aktifitas Referal**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 27.1 | Membuka halaman Aktifitas Referal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Aktifitas Referal. - [Success] |

|  |  |
| --- | --- |
| 27.2 | Melakukan filter data Aktifitas Referal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 27.3 | Melihat data tab Prospek yang saya referalkan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek yang saya referalkan. - [Success] |

|  |  |
| --- | --- |
| 27.4 | Mencari data tab Prospek yang saya referalkan dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 27.5 | Mencari data tab Prospek yang saya referalkan dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 27.6 | Melihat detail tab Prospek yang saya referalkan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail prospek. - [Success] |

|  |  |
| --- | --- |
| 27.7 | Melihat data tab Prospek yang direferalkan ke saya |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek yang direferalkan ke saya. - [Success] |

|  |  |
| --- | --- |
| 27.8 | Mencari data tab Prospek yang direferalkan ke saya dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

# **28. Modul List Prospek ETB**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 28.1 | Membuka halaman List Prospek ETB |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman list prospek ETB. - [Success] |

|  |  |
| --- | --- |
| 28.2 | Filter data list prospek ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data list prospek ETB sesuai dengan filter yang di pilih. - [Success] |

|  |  |
| --- | --- |
| 28.3 | Mencari data list prospek ETB |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data list prospek ETB sesuai dengan keyword yang dai cari. - [Success] |

|  |  |
| --- | --- |
| 28.4 | Menghapus data list prospek ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data list prospek ETB yang telah di pilih. - [Success] |

|  |  |
| --- | --- |
| 28.5 | Menghapus semua data list prospek ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus semua data list prospek ETB dan data tabel menjadi kosong. - [Success] |

|  |  |
| --- | --- |
| 28.6 | Mengunduh data list prospek ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data list prospek ETB dalam bentuk file Excel. - [Success] |

|  |  |
| --- | --- |
| 28.7 | Menampilkan detail list prospek ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail prospek ETB. - [Success] |

|  |  |
| --- | --- |
| 28.8 | Melakukan Prospek Ulang |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan prospek ulang dengan popup 'Prospek Ulang Berhasil' dan data prospek tersebut akan masuk ke halaman aktifitas. - [Success] |

|  |  |
| --- | --- |
| 28.9 | Menampilkan informasi rekening |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Modal informasi rekening tertutup dan tetap di halaman list prospek ETB. - [Success] |

# **29. Modul Menu Absent - Dashboard Absent**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 29.1 | Membuka halaman Dashboard Absent |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Dashboard Absent. - [Success] |

|  |  |
| --- | --- |
| 29.2 | Melakukan filter data Dashboard Absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data dashboard sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 29.3 | Mereset filter Dashboard Absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset seluruh filter ke nilai default. - [Success] |

|  |  |
| --- | --- |
| 29.4 | Melihat detail daftar absensi Kantor Wilayah |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan modal detail daftar absensi Kantor Wilayah. - [Success] |

|  |  |
| --- | --- |
| 29.5 | Mencari data pada detail Kantor Wilayah dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil data absensi ditampilkan sesuai kata kunci yang dicari. - [Success] |

|  |  |
| --- | --- |
| 29.6 | Mencari data pada detail Kantor Wilayah dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan tabel kosong atau pesan data tidak ditemukan. - [Success] |

# **30. Modul Menu Absent - Daily Absent**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 30.1 | Membuka halaman Daily Absent |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Daily Absent. - [Success] |

|  |  |
| --- | --- |
| 30.2 | Menampilkan data berdasarkan status absent |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data berdasarkan status absent yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 30.3 | Melakukan filter Daily Absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Daily Absent sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 30.4 | Mereset filter |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan data default. - [Success] |

|  |  |
| --- | --- |
| 30.5 | Mengubah status absensi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah status absensi karyawan. - [Success] |

|  |  |
| --- | --- |
| 30.6 | Melihat Note Clock In |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Attendance Detail. - [Success] |

|  |  |
| --- | --- |
| 30.7 | Melihat Attachment Clock In |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Note Clock In. - [Success] |

|  |  |
| --- | --- |
| 30.8 | Melihat Lokasi Clock In |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Attachment Clock In. - [Success] |

|  |  |
| --- | --- |
| 30.9 | Melihat Note Clock Out |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan lokasi Clock In pada peta. - [Success] |

|  |  |
| --- | --- |
| 30.10 | Melihat Attachment Clock Out |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Note Clock Out. - [Success] |

|  |  |
| --- | --- |
| 30.11 | Melihat Lokasi Clock Out |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Attachment Clock Out. - [Success] |

|  |  |
| --- | --- |
| 30.12 | Membuka Settings |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka drawer Settings. - [Success] |

|  |  |
| --- | --- |
| 30.13 | Mencari data pada Settings |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Settings sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 30.14 | Mencari data Settings dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan pada Settings. - [Success] |

|  |  |
| --- | --- |
| 30.15 | Mengubah status Requires Approval |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah status Requires Approval. - [Success] |

|  |  |
| --- | --- |
| 30.16 | Mengekspor data Daily Absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan lokasi Clock Out pada peta. - [Success] |

# **31. Modul Menu Absent - Rekap Absent**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 31.1 | Membuka halaman Rekap Absent |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Rekap Absent. - [Success] |

|  |  |
| --- | --- |
| 31.2 | Mencari data rekap absent dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar data Rekap Absent di dalam tabel. - [Success] |

|  |  |
| --- | --- |
| 31.3 | Mencari data rekap absent dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Rekap Absent sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 31.4 | Melakukan filter rekap absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter Rekap Absent ke nilai default. - [Success] |

|  |  |
| --- | --- |
| 31.5 | Mereset filter rekap absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mencari data Rekap Absent sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 31.6 | Mengekspor data rekap absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export data Rekap Absent. - [Success] |

# **32. Modul Menu Absent - Approval Absent**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 32.1 | Membuka halaman Approval Absent |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Approval Absent. - [Success] |

|  |  |
| --- | --- |
| 32.2 | Mencari data dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Approval Absent sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 32.3 | Mencari data dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter Approval Absent. - [Success] |

|  |  |
| --- | --- |
| 32.4 | Melakukan filter approval absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mencari data Approval Absent sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 32.5 | Melihat Attendance detail |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 32.6 | Melihat Note |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Note absent. - [Success] |

|  |  |
| --- | --- |
| 32.7 | Melihat Attachment |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan Attachment absent. - [Success] |

|  |  |
| --- | --- |
| 32.8 | Melihat Lokasi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan lokasi absent pada peta. - [Success] |

|  |  |
| --- | --- |
| 32.9 | Menyetujui approval absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyetujui (approve) data absent. - [Success] |

|  |  |
| --- | --- |
| 32.10 | Menyetujui approval absent tanpa mengisi Comments |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi Comments wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 32.11 | Menolak approval absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menolak (reject) data absent. - [Success] |

|  |  |
| --- | --- |
| 32.12 | Menolak approval absent tanpa mengisi Comments |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi Comments wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 32.13 | Membatalkan approval yang sudah disetujui |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan approval yang sudah disetujui. - [Success] |

|  |  |
| --- | --- |
| 32.14 | Membatalkan approval yang sudah di reject |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan approval yang sudah di-reject. - [Success] |

|  |  |
| --- | --- |
| 32.15 | Mengekspor data approval absent |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengekspor data approval absent. - [Success] |

# **33. Modul Sales Tracking Activity - Dashboard Visit**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 33.1 | Membuka halaman Dashboard Visit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Dashboard Visit. - [Success] |

|  |  |
| --- | --- |
| 33.2 | Melakukan filter data Dashboard Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan filter data Dashboard Visit. - [Success] |

|  |  |
| --- | --- |
| 33.3 | Melakukan filter data Dashboard Visit dengan data yang tidak ada |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 33.4 | Mereset filter Dashboard Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter Dashboard Visit. - [Success] |

|  |  |
| --- | --- |
| 33.5 | Melihat detail cabang |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan popup detail cabang. - [Success] |

|  |  |
| --- | --- |
| 33.6 | Mencari data detail cabang dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 33.7 | Mencari data detail cabang dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 33.8 | Mengekspor data detail cabang |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **34. Modul Sales Tracking Activity - Client Visit List**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 34.1 | Membuka halaman Client Visit List |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka sub menu Client Visit List. - [Success] |

|  |  |
| --- | --- |
| 34.2 | Menampilkan daftar data Client Visit List |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar data Client Visit List beserta informasi Total Visit. - [Success] |

|  |  |
| --- | --- |
| 34.3 | Memvalidasi pembaruan data Total Visit setelah menerapkan filter |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Angka pada card Total Visit ter-update secara otomatis sesuai dengan jumlah baris data hasil filter. - [Success] |

|  |  |
| --- | --- |
| 34.4 | Mencari data Client Visit List dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai pencarian. - [Success] |

|  |  |
| --- | --- |
| 34.5 | Mencari data Client Visit List dengan keyword tidak valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data kosong. - [Success] |

|  |  |
| --- | --- |
| 34.6 | Melakukan filter data Client Visit List |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 34.7 | Mereset filter data Client Visit List |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset seluruh parameter filter dan menampilkan seluruh data. - [Success] |

|  |  |
| --- | --- |
| 34.8 | Melihat detail profil Sales Name |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman detail profil Sales. - [Success] |

|  |  |
| --- | --- |
| 34.9 | Melihat lokasi Tag Location Visit In pada peta |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan popup peta Visit In Location beserta informasi Visit Activity dan Client Name. - [Success] |

|  |  |
| --- | --- |
| 34.10 | Melihat lokasi Tag Location Visit Out pada peta |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan popup peta Visit Out Location beserta informasi Visit Activity dan Client Name. - [Success] |

|  |  |
| --- | --- |
| 34.11 | Melihat detail aktivitas Visit In |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan popup Activity Visit Detail yang berisi foto, Visit In Date & Time, Visit In Location, dan Visit In Description. - [Success] |

|  |  |
| --- | --- |
| 34.12 | Melihat detail aktivitas Visit Out |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan popup Activity Visit Detail yang berisi foto, Visit Out Date & Time, Visit Out Location, dan Visit Out Description. - [Success] |

|  |  |
| --- | --- |
| 34.13 | Mengekspor data Client Visit List |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export data Client Visit List. - [Success] |

# **35. Modul Sales Tracking Activity - Rekap Visit**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 35.1 | Membuka halaman Rekap Visit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Rekap Visit. - [Success] |

|  |  |
| --- | --- |
| 35.2 | Menampilkan daftar data Rekap Visit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar data Rekap Visit. - [Success] |

|  |  |
| --- | --- |
| 35.3 | Mencari data Rekap Visit dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Rekap Visit sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 35.4 | Mencari data Rekap Visit dengan keyword tidak valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 35.5 | Melakukan filter data Rekap Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Rekap Visit sesuai filter. - [Success] |

|  |  |
| --- | --- |
| 35.6 | Mereset filter Rekap Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan seluruh data Rekap Visit. - [Success] |

|  |  |
| --- | --- |
| 35.7 | Mengekspor data Rekap Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **36. Modul Sales Tracking Activity - Rekap Monthly Visit**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 36.1 | Membuka halaman Rekap Monthly Visit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka halaman Rekap Monthly Visit. - [Success] |

|  |  |
| --- | --- |
| 36.2 | Mencari data Rekap Monthly Visit dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Rekap Monthly Visit sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 36.3 | Mencari data Rekap Monthly Visit dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan pesan bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 36.4 | Melakukan filter data Rekap Monthly Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Rekap Monthly Visit sesuai filter. - [Success] |

|  |  |
| --- | --- |
| 36.5 | Mereset filter Rekap Monthly Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan seluruh data Rekap Monthly Visit. - [Success] |

|  |  |
| --- | --- |
| 36.6 | Mengekspor data Rekap Monthly Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **37. Modul Setting Absent - Attendance Spot**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 37.1 | Membuka halaman Attendance Spot |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Attendance Spot. - [Success] |

|  |  |
| --- | --- |
| 37.2 | Mencari data Attendance Spot dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 37.3 | Mencari data Attendance Spot dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 37.4 | Menambahkan data Attendance Spot |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Attendance Spot. - [Success] |

|  |  |
| --- | --- |
| 37.5 | Menambahkan data Attendance Spot tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 37.6 | Mencari lokasi spesifik melalui pencarian peta dengan keyword valid |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil peta berhasil menampilkan titik lokasi yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 37.7 | Mencari lokasi spesifik melalui pencarian peta dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Peta tidak menemukan lokasi yang dimaksud (menampilkan pesan tidak ditemukan). - [Success] |

|  |  |
| --- | --- |
| 37.8 | Mengubah data Attendance Spot |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Attendance Spot. - [Success] |

|  |  |
| --- | --- |
| 37.9 | Mengubah data Attendance Spot tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 37.10 | Melihat detail lokasi pada peta |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan popup peta lokasi Attendance Spot. - [Success] |

|  |  |
| --- | --- |
| 37.11 | Menghapus data Attendance Spot |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data Attendance Spot. - [Success] |

|  |  |
| --- | --- |
| 37.12 | Membuka halaman Setting Attendance Spot Personnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Setting Attendance Spot Personnel. - [Success] |

|  |  |
| --- | --- |
| 37.13 | Melakukan filter data Personnel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Personnel sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 37.14 | Mencari data Personnel dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Personnel sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 37.15 | Mencari data Personnel dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 37.16 | Menambahkan data Personnel secara single |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan/mengaktifkan personnel ke Attendance Spot secara single. - [Success] |

|  |  |
| --- | --- |
| 37.17 | Menghapus data Personnel secara single |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus/menonaktifkan personnel dari Attendance Spot secara single. - [Success] |

|  |  |
| --- | --- |
| 37.18 | Menambahkan data Personnel secara bulk (Add Personnel) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan/mengaktifkan seluruh personnel yang dipilih ke Attendance Spot secara bulk. - [Success] |

|  |  |
| --- | --- |
| 37.19 | Menghapus data Personnel secara bulk (Remove Personnel) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus/menonaktifkan seluruh personnel yang dipilih dari Attendance Spot secara bulk. - [Success] |

# **38. Modul Setting Absent - Work Pattern**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 38.1 | Membuka halaman Work Pattern |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Work Pattern. - [Success] |

|  |  |
| --- | --- |
| 38.2 | Mencari data Work Pattern dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 38.3 | Mencari data Work Pattern dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 38.4 | Menambahkan data Work Pattern |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Work Pattern. - [Success] |

|  |  |
| --- | --- |
| 38.5 | Menambahkan data Work Pattern tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 38.6 | Menerapkan jadwal ke beberapa hari secara sekaligus (Terapkan ke Semua) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menerapkan jadwal yang diinput ke seluruh hari yang dicentang secara bersamaan. - [Success] |

|  |  |
| --- | --- |
| 38.7 | Mereset jadwal pada beberapa hari secara sekaligus (Reset) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengosongkan kembali (reset) jadwal pada seluruh hari yang dicentang secara bersamaan. - [Success] |

|  |  |
| --- | --- |
| 38.8 | Mengubah data Work Pattern |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Work Pattern. - [Success] |

|  |  |
| --- | --- |
| 38.9 | Mengubah data Work Pattern tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 38.10 | Melihat detail Work Pattern |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan popup Work Pattern Details yang berisi jadwal kerja. - [Success] |

|  |  |
| --- | --- |
| 38.11 | Menghapus data Work Pattern |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data Work Pattern. - [Success] |

|  |  |
| --- | --- |
| 38.12 | Membuka halaman Setting Work Pattern Personnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Setting Work Pattern Personnel. - [Success] |

|  |  |
| --- | --- |
| 38.13 | Melakukan filter data Personnel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Personnel sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 38.14 | Mencari data Personnel dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Personnel sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 38.15 | Mencari data Personnel dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 38.16 | Meng-assign data Personnel ke Work Pattern secara single |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil meng-assign personnel tersebut ke Work Pattern. - [Success] |

|  |  |
| --- | --- |
| 38.17 | Meng-assign data Personnel ke Work Pattern secara bulk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil meng-assign seluruh personnel yang dipilih secara bulk ke Work Pattern. - [Success] |

|  |  |
| --- | --- |
| 38.18 | Meng-unassign data Personnel dari Work Pattern secara single |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus (unassign) personnel tersebut dari Work Pattern. - [Success] |

|  |  |
| --- | --- |
| 38.19 | Meng-unassign data Personnel dari Work Pattern secara bulk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus (unassign) seluruh personnel yang dipilih secara bulk dari Work Pattern. - [Success] |

# **39. Modul Setting Absent - Holiday**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 39.1 | Membuka halaman Holiday |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Holiday. - [Success] |

|  |  |
| --- | --- |
| 39.2 | Mencari data Holiday dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai keyword. - [Success] |

|  |  |
| --- | --- |
| 39.3 | Mencari data Holiday dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 39.4 | Menambahkan data Holiday |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data Holiday. - [Success] |

|  |  |
| --- | --- |
| 39.5 | Menambahkan data Holiday tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 39.6 | Mengubah data Holiday |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Holiday. - [Success] |

|  |  |
| --- | --- |
| 39.7 | Mengubah data Holiday tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan validasi field mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 39.8 | Menghapus data Holiday |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data Holiday. - [Success] |

# **40. Modul Sales Force - Sales code**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 40.1 | Membuka menu sales code |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan halaman sales code. - [Success] |

|  |  |
| --- | --- |
| 40.2 | Melakukan filter data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 40.3 | Melakukan filter dengan tidak mengisi filter mandatory (Negative case) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan alert "filter mandatory dibutuhkan". - [Success] |

|  |  |
| --- | --- |
| 40.4 | Menambahkan sales code |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  berhasil menambahkan sales code. - [Success] |

|  |  |
| --- | --- |
| 40.5 | Menambahkan sales people |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menginput sales people. - [Success] |

|  |  |
| --- | --- |
| 40.6 | menambahkan sales people dengan nip yang tidak ada (Negative case) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan alert "Nip tidak ditemukan". - [Success] |

|  |  |
| --- | --- |
| 40.7 | Menambahkan sales code dan sales people secara bersamaan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil create salescode dan input nip. - [Success] |

|  |  |
| --- | --- |
| 40.8 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 40.9 | Mencari data kata kunci yang tidak sesuai (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 40.10 | Menghapus sales people |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  berhasil menghapus/ melepaskan nip dari sales code. - [Success] |

|  |  |
| --- | --- |
| 40.11 | Menghapus sales code |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  berhasil menghapus data sales code. - [Success] |

|  |  |
| --- | --- |
| 40.12 | Melihat detail |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan detail data sales code. - [Success] |

|  |  |
| --- | --- |
| 40.13 | Mengubah sales people |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil update data sales people. - [Success] |

|  |  |
| --- | --- |
| 40.14 | mengunduh data sales code |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data sales code. - [Success] |

|  |  |
| --- | --- |
| 40.15 | Membuka tab sales code assign |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan list data sales code yang belum memiliki sales people. - [Success] |

|  |  |
| --- | --- |
| 40.16 | Membuka tab sales code not assign |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan list data sales code yang sudah memiliki sales people. - [Success] |

|  |  |
| --- | --- |
| 40.17 | Membuka tab sales people not assign |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan list data sales yang belum memiliki sales code. - [Success] |

# **41. Modul Sales Force - Pipeline - Dashboard Validate Pipeline**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 41.1 | Membuka menu dashboard validate pipeline |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Dashboard Validate Pipeline. - [Success] |

|  |  |
| --- | --- |
| 41.2 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan bulan yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 41.3 | Melakukan filter data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 41.4 | Membuka detail Chart total pipeline DPK |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail pipeline data kantor cabang. - [Success] |

|  |  |
| --- | --- |
| 41.5 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 41.6 | Membuka detail list pipeline DPK |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Validate pipeline DPK. - [Success] |

|  |  |
| --- | --- |
| 41.7 | Membuka detail Chart pipeline data kantor cabang |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail pipeline data kantor cabang. - [Success] |

|  |  |
| --- | --- |
| 41.8 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 41.9 | Membuka detail list pipeline kantor cabang |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Validate pipeline kantor cabang. - [Success] |

|  |  |
| --- | --- |
| 41.10 | Membuka detail Chart Sales Input Pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Sales Input Pipeline. - [Success] |

|  |  |
| --- | --- |
| 41.11 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 41.12 | Membuka detail list Sales Input Pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Validate pipeline Sales Input Pipeline. - [Success] |

|  |  |
| --- | --- |
| 41.13 | Membuka detail Chart Pipeline Category |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Pipeline Category. - [Success] |

|  |  |
| --- | --- |
| 41.14 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 41.15 | Membuka detail list Pipeline Category |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Validate Pipeline Category. - [Success] |

|  |  |
| --- | --- |
| 41.16 | List validate Pipeline - mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 41.17 | Membuka detail list validate pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail validate pipeline. - [Success] |

|  |  |
| --- | --- |
| 41.18 | Detail Validate Pipeline - Melakukan Filter data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 41.19 | Detail Validate pipeline - mengunduh data validate pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data. - [Success] |

|  |  |
| --- | --- |
| 41.20 | Melakukan Validate data menggunakan user BM |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan validate pipeline dan data akan tampil pada user RO Head. - [Success] |

|  |  |
| --- | --- |
| 41.21 | Melakukan validate all data menggunakan user BM |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan validate data secara bersamaan dan data akan tampil pada user RO Head. - [Success] |

|  |  |
| --- | --- |
| 41.22 | Melakukan unvalidate data menggunakan user BM |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil unvalidate pipeline. - [Success] |

|  |  |
| --- | --- |
| 41.23 | Melakukan Validate data menggunakan user RO Head |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan validate pipeline. - [Success] |

|  |  |
| --- | --- |
| 41.24 | Melakukan validate all data menggunakan user RO Head |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan validate data secara bersamaan. - [Success] |

|  |  |
| --- | --- |
| 41.25 | Melakukan unvalidate data menggunakan user RO Head |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil unvalidate pipeline. - [Success] |

# **42. Modul Sales Force - Pipeline - Input Pipeline**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 42.1 | Membuka menu input Pipeline |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Input pipeline. - [Success] |

|  |  |
| --- | --- |
| 42.2 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan filter yang dipilih – [Success] |

|  |  |
| --- | --- |
| 42.3 | Melakukan filter data dengan tidak menginput filter mandatory (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert filter dibutuhkan. - [Success] |

|  |  |
| --- | --- |
| 42.4 | Menambahkan data pipeline NTB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Pipeline berhasil di submit – [Success] |

|  |  |
| --- | --- |
| 42.5 | Menambahkan data pipeline NTB tidak menginput data mandatory (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan alert data dibutuhkan – [Success] |

|  |  |
| --- | --- |
| 42.6 | Menambahkan data pipeline ETB |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Pipeline berhasil di submit – [Success] |

|  |  |
| --- | --- |
| 42.7 | Menambahkan data ETB dengan menginput nomor cif tidak sesuai (Negative Test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan alert cif & no rekening tidak di temukan – [Success] |

|  |  |
| --- | --- |
| 42.8 | Menambahkan data ETB dengan menginput nomor no rekening tidak sesuai (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan alert cif & no rekening tidak di temukan – [Success] |

|  |  |
| --- | --- |
| 42.9 | Melihat detail pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan detail pipeline – [Success] |

|  |  |
| --- | --- |
| 42.10 | Mengubah tanggal potensi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah tanggal potensi – [Success] |

|  |  |
| --- | --- |
| 42.11 | Melihat potensi perubahan tanggal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan list data perubahan tanggal potensi – [Success] |

# **43. Modul Sales Force - Approval Target Growth**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 43.1 | Melihat detail |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail data Approval Target Growth. - [Success] |

|  |  |
| --- | --- |
| 43.2 | Melakukan approval data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan approval data sales code. - [Success] |

|  |  |
| --- | --- |
| 43.3 | Melakukan reject data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan reject data sales code. - [Success] |

|  |  |
| --- | --- |
| 43.4 | Membuka tab status ( pending request/approved/Rejected/expired) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan list data sesuai status yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 43.5 | Melihat detail data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail data sales code. - [Success] |

|  |  |
| --- | --- |
| 43.6 | Melakukan approval data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan approval data sales code. - [Success] |

|  |  |
| --- | --- |
| 43.7 | Melakukan reject data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan reject data sales code. - [Success] |

|  |  |
| --- | --- |
| 43.8 | Membuka tab status ( pending request/approved/Rejected/expired) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan list data sesuai status yang dipilih. - [Success] |

# **44. Modul Sales Force - Approval Sales Code**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 44.1 | Membuka menu approval sales code |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Approval Sales Code. - [Success] |

|  |  |
| --- | --- |
| 44.2 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 44.3 | Melakukan approval data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan approval data sales code. - [Success] |

|  |  |
| --- | --- |
| 44.4 | Melakukan reject data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan reject data sales code. - [Success] |

|  |  |
| --- | --- |
| 44.5 | Membuka tab status ( pending request/approved/Rejected/expired) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan list data sesuai status yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 44.6 | Melihat detail data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data. - [Success] |

|  |  |
| --- | --- |
| 44.7 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 44.8 | Mencari data kata kunci invalid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

# **45. Modul Sales Force - CIF Kelolaan**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 45.1 | Membuka menu cif kelolaan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman CIF Kelolaan. - [Success] |

|  |  |
| --- | --- |
| 45.2 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 45.3 | Assign cif kelolaan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload data Cif Kelolaan. - [Success] |

|  |  |
| --- | --- |
| 45.4 | Assign cif kelolaan menginput data template tidak sesuai (Negative test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data terupload dengan status failed. - [Success] |

|  |  |
| --- | --- |
| 45.5 | Assign cif kelolaan - Download souce file |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data source file. - [Success] |

|  |  |
| --- | --- |
| 45.6 | Assign cif kelolaan - preview data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan preview data hasil upload. - [Success] |

|  |  |
| --- | --- |
| 45.7 | Assign cif kelolaan - download error file |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data error untuk mengetahui informasi letak error saat upload file template. - [Success] |

|  |  |
| --- | --- |
| 45.8 | Mengunduh data cif kelolaan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data cif kelolaan. - [Success] |

|  |  |
| --- | --- |
| 45.9 | Menambahkan data cif kelolaan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan data cif kelolaan. - [Success] |

|  |  |
| --- | --- |
| 45.10 | Menambahkan data cif kelolaan dengan menginput format nip yang tidak sesuai (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Gagal menambahkan data cif kelolaan. - [Success] |

|  |  |
| --- | --- |
| 45.11 | Menghapus data cif kelolaan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data cif kelolaan. - [Success] |

|  |  |
| --- | --- |
| 45.12 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 45.13 | Membuka tab status ( pending request/approved/Rejected/expired) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan list data sesuai status yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 45.14 | Melihat detail data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data. - [Success] |

|  |  |
| --- | --- |
| 45.15 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 45.16 | Mencari data kata kunci yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

# **46. Modul Sales Force - Approval Cif Kelolaan**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 46.1 | Membuka menu approval cif kelolaan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman target produktivitas. - [Success] |

|  |  |
| --- | --- |
| 46.2 | Melakukan Filter data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 46.3 | Melakukan approval data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan approval data CIF Kelolaan - [Success] |

|  |  |
| --- | --- |
| 46.4 | Melakukan reject data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan reject data CIF Kelolaan - [Success] |

|  |  |
| --- | --- |
| 46.5 | Membuka tab status ( pending request/approved/Rejected/expired) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan list data sesuai status yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 46.6 | Melihat detail data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data - [Success] |

|  |  |
| --- | --- |
| 46.7 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 46.8 | Mencari data kata kunci yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

# **47. Modul Sales Force - Produktivitas - Target Growth**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 47.1 | Membuka menu Target Growth |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman bobot produktivitas. - [Success] |

|  |  |
| --- | --- |
| 47.2 | Import data Target growth |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload data target growth. - [Success] |

|  |  |
| --- | --- |
| 47.3 | Import data target growth dengan ngisi data template yang tidak sesuai (Negative Test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data terupload dengan status failed. - [Success] |

|  |  |
| --- | --- |
| 47.4 | Melakukan Import data tagert growth menggunakan user sales |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data Bobot Produktivitas. - [Success] |

|  |  |
| --- | --- |
| 47.5 | Mengunduh data target growth |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data target growth. - [Success] |

|  |  |
| --- | --- |
| 47.6 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 47.7 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 47.8 | Mencari data kata kunci yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

# **48. Modul Sales Force - Produktivitas - Target Produktivitas**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 48.1 | Membuka menu Target Produktivitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Realisasi Merchant. - [Success] |

|  |  |
| --- | --- |
| 48.2 | Import data Target Produktivitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengupload data Realisasi Merchant. - [Success] |

|  |  |
| --- | --- |
| 48.3 | Import data target produktivitas dengan mengisi data template yang tidak sesuai (Negative Test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data terupload dengan status failed. - [Success] |

|  |  |
| --- | --- |
| 48.4 | Mengunduh data target produktivitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data Realisasi Merchant. - [Success] |

|  |  |
| --- | --- |
| 48.5 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 48.6 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 48.7 | Mencari data kata kunci yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

# **49. Modul Sales Force - Produktivitas - Bobot Produktivitas**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 49.1 | Membuka menu Bobot Produktivitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Bobot Produktivitas. - [Success] |

|  |  |
| --- | --- |
| 49.2 | Import data Bobot Produktivitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan import data Bobot Produktivitas. - [Success] |

|  |  |
| --- | --- |
| 49.3 | Import data Bobot Produktivitas dengan ngisi data template yang tidak sesuai (Negative Test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data berhasil di arsipkan. - [Success] |

|  |  |
| --- | --- |
| 49.4 | Mengunduh data Bobot Produktivitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload data Bobot Produktivitas. - [Success] |

|  |  |
| --- | --- |
| 49.5 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 49.6 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 49.7 | Mencari data kata kunci yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

# **50. Modul Sales Force - Produktivitas - Realisasi Merchant**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 50.1 | Membuka menu realisasi merchant |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Realisasi Merchant. - [Success] |

|  |  |
| --- | --- |
| 50.2 | Import data realisasi merchant |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan import data Realisasi Merchant. - [Success] |

|  |  |
| --- | --- |
| 50.3 | Import data realisasi merchant dengan ngisi data template yang tidak sesuai (Negative Test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data. - [Success] |

|  |  |
| --- | --- |
| 50.4 | Mengunduh data realisasi merchant |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data sales force. - [Success] |

|  |  |
| --- | --- |
| 50.5 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 50.6 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 50.7 | Mencari data kata kunci yang tidak sesuai |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data tidak ditemukan. - [Success] |

# **51. Modul Sales Force - CIF Rebase**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 51.1 | Membuka halaman CIF Rebase |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman cif rebase. - [Success] |

|  |  |
| --- | --- |
| 51.2 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 51.3 | Melakukan rebase |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan rebase cif. - [Success] |

|  |  |
| --- | --- |
| 51.4 | Melakukan Archive |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data berhasil di arsipkan. - [Success] |

|  |  |
| --- | --- |
| 51.5 | Melihat tab CIF Rebase History |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan list data cif rebase history. - [Success] |

|  |  |
| --- | --- |
| 51.6 | Melihat tab CIF Rebase Archive |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan list data cif rebase yang di arsipkan. - [Success] |

|  |  |
| --- | --- |
| 51.7 | Melakukan Unarchive cif |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Cif berhasil di unarchive. - [Success] |

|  |  |
| --- | --- |
| 51.8 | Mengunduh data cif rebase history |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data. - [Success] |

|  |  |
| --- | --- |
| 51.9 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

# **52. Modul Sales Force - Report - Report Produktivitas**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 52.1 | Membuka menu Report produktivitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Report Produktivitas. - [Success] |

|  |  |
| --- | --- |
| 52.2 | Melakukan filter data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 52.3 | Mengunduh seluruh data report produktifitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh all data report produktivitas. - [Success] |

|  |  |
| --- | --- |
| 52.4 | Mengunduh data resume |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data. - [Success] |

|  |  |
| --- | --- |
| 52.5 | Tab sforce |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data Target Growth. - [Success] |

|  |  |
| --- | --- |
| 52.6 | mengunduh data sforce |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data Target Growth. - [Success] |

|  |  |
| --- | --- |
| 52.7 | Tab Calculate |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data kalkulasi nilai produktifitas berdasarkan tipe kantor. - [Success] |

|  |  |
| --- | --- |
| 52.8 | Mengunduh data calculate |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data calculate. - [Success] |

|  |  |
| --- | --- |
| 52.9 | Tab Realisasi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data nilai realisasi setiap daftar Target Growth. - [Success] |

|  |  |
| --- | --- |
| 52.10 | Mengunduh data realisasi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data realisasi. - [Success] |

|  |  |
| --- | --- |
| 52.11 | Tab Target |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data target. - [Success] |

|  |  |
| --- | --- |
| 52.12 | Mengunduh data Target |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data target. - [Success] |

|  |  |
| --- | --- |
| 52.13 | Tab Target DPK |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data nilai akumulasi target growth atau voa. - [Success] |

|  |  |
| --- | --- |
| 52.14 | Mengunduh data target DPK |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data target dpk. - [Success] |

|  |  |
| --- | --- |
| 52.15 | Tab DPK port |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data berdasarakan nilai voa atau growth secara aktual. - [Success] |

|  |  |
| --- | --- |
| 52.16 | Mengunduh data Target DPK port |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data dpk port. - [Success] |

|  |  |
| --- | --- |
| 52.17 | Tab konek Echannel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data secara konektifitas mobile banking. - [Success] |

|  |  |
| --- | --- |
| 52.18 | Mengunduh data konek echannel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data konek echanel. - [Success] |

|  |  |
| --- | --- |
| 52.19 | Tab All CIF |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data seluruh cif pada Target Growth. - [Success] |

|  |  |
| --- | --- |
| 52.20 | Mengunduh data all cif |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data all cif. - [Success] |

|  |  |
| --- | --- |
| 52.21 | Tab SegMove |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan informasi data voa pada bulan berjalan dan perbandingan nilai voa pada akhir tahun lalu. - [Success] |

|  |  |
| --- | --- |
| 52.22 | Mengunduh data Segmove |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data segmove. - [Success] |

|  |  |
| --- | --- |
| 52.23 | Tab Visit |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data visit. - [Success] |

|  |  |
| --- | --- |
| 52.24 | Mengunduh data Visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data visit. - [Success] |

|  |  |
| --- | --- |
| 52.25 | Tab Merchant |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data merchant. - [Success] |

|  |  |
| --- | --- |
| 52.26 | Mengunduh data Merchant |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data merchant. - [Success] |

|  |  |
| --- | --- |
| 52.27 | Tab Tier |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data tier. - [Success] |

|  |  |
| --- | --- |
| 52.28 | Mengunduh data Tier |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data tier. - [Success] |

|  |  |
| --- | --- |
| 52.29 | Tab Referal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data refreal. - [Success] |

|  |  |
| --- | --- |
| 52.30 | Mengunduh data Referal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data referal. - [Success] |

|  |  |
| --- | --- |
| 52.31 | Tab Presensi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan report data absensi bisnis unit TAD. - [Success] |

|  |  |
| --- | --- |
| 52.32 | Mengunduh data Presensi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data persensi. - [Success] |

# **53. Modul Sales Force - Dashboard Sales Force**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 53.1 | Membuka menu dashboard sales code |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Dashboard. - [Success] |

|  |  |
| --- | --- |
| 53.2 | Melakukan filter data berdasarkan bulan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan bulan yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.3 | Melakukan filter data |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.4 | Melihat detail Card VoA Realization |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Card VoA Realization. - [Success] |

|  |  |
| --- | --- |
| 53.5 | Filter data Voa Realization |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.6 | Mencari data Voa realization pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 53.7 | Melihat detail Voa Realization |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail Card VoA Realization. - [Success] |

|  |  |
| --- | --- |
| 53.8 | Melihat detail card Cif Kelolaan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Cif Kelolaan. - [Success] |

|  |  |
| --- | --- |
| 53.9 | Filter data Cif Kelolaan |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.10 | mencari data Cif Kelolaan pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 53.11 | Melihat detail Cif Kelolaan |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail Cif Kelolaan. - [Success] |

|  |  |
| --- | --- |
| 53.12 | Melihat detail card skor Produktivitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail skor Produktivitas. - [Success] |

|  |  |
| --- | --- |
| 53.13 | Filter data produktivitas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.14 | Melihat detail skor Produktivitas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail skor Produktivitas. - [Success] |

|  |  |
| --- | --- |
| 53.15 | Melihat detail data card konek echannel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail konek echannel. - [Success] |

|  |  |
| --- | --- |
| 53.16 | Filter data konek echannel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.17 | Mencari data konek echannel pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 53.18 | Melihat detail data konek echannel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail konek echannel. - [Success] |

|  |  |
| --- | --- |
| 53.19 | Melihat detail data card realisasi visit |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Direct ke menu client visit list. - [Success] |

|  |  |
| --- | --- |
| 53.20 | Melihat detail data card realisasi akuisisi merchant |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail realisasi akuisisi merchant. - [Success] |

|  |  |
| --- | --- |
| 53.21 | Filter data realisasi akuisisi merchant |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.22 | Mencari data realisasi akuisisi merchant pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 53.23 | Melihat detail data realisasi merchant |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail realisasi akuisisi merchant. - [Success] |

|  |  |
| --- | --- |
| 53.24 | Melihat detail data card Eligible Upgrade to Prospera / Prioritas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Eligible Upgrade to Prospera / Prioritas. - [Success] |

|  |  |
| --- | --- |
| 53.25 | Filter data Eligible Upgrade to Prospera / Prioritas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.26 | Mencari data Eligible Upgrade to Prospera Prioritas pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 53.27 | Melihat detail data Eligible Upgrade to Prospera / Prioritas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail Eligible Upgrade to Prospera / Prioritas. - [Success] |

|  |  |
| --- | --- |
| 53.28 | Melihat detail data card Referral to Prospera / Prioritas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Referral to Prospera / Prioritas. - [Success] |

|  |  |
| --- | --- |
| 53.29 | Filter data Referral to Prospera / Prioritas |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 53.30 | Mencari data Referral to Prospera / Prioritas pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 53.31 | Melihat detail data Referral to Prospera / Prioritas |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan detail Referral to Prospera / Prioritas. - [Success] |

# **54. Modul Sales Force - Pipeline - Setting Role Validate Pipeline**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 54.1 | Membuka menu setting Role validate Pipeline |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Input komitmen. - [Success] |

|  |  |
| --- | --- |
| 54.2 | Melakukan filter tipe organisasi |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan komitmen baru. - [Success] |

|  |  |
| --- | --- |
| 54.3 | Menambahkan data setting role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Field tidak bisa di ketik. - [Success] |

|  |  |
| --- | --- |
| 54.4 | Melihat riwayat setting role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan. - [Success] |

|  |  |
| --- | --- |
| 54.5 | Melihat ilustration alur validasi pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengembalikan nilai komitmen menjadi 0. - [Success] |

|  |  |
| --- | --- |
| 54.6 | Mengubah data setting role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data komitmen. - [Success] |

|  |  |
| --- | --- |
| 54.7 | Menghapus data setting role |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data. - [Success] |

|  |  |
| --- | --- |
| 54.8 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan kata kunci yang diinput. - [Success] |

|  |  |
| --- | --- |
| 54.9 | Mencari data kata kunci tidak valid (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data Tidak ditemukan. - [Success] |

# **55. Modul Sales Force - Pipeline - Setting Validate Pipeline**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 55.1 | Membuka menu setting validate pipeline |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Input pipeline. - [Success] |

|  |  |
| --- | --- |
| 55.2 | input setting validate pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert filter dibutuhkan. - [Success] |

|  |  |
| --- | --- |
| 55.3 | Mengubah data setting validate pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Pipeline berhasil di submit. - [Success] |

|  |  |
| --- | --- |
| 55.4 | Menghapus data setting validate pipeline |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan alert data dibutuhkan. - [Success] |

|  |  |
| --- | --- |
| 55.5 | Melihat detail setting validate pipeline |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Pipeline berhasil di submit. - [Success] |

|  |  |
| --- | --- |
| 55.6 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan kata kunci yang diinput - [Success] |

|  |  |
| --- | --- |
| 55.7 | Mencari data kata kunci tidak valid (Negative test) |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Data Tidak ditemukan - [Success] |

# **56. Modul Sales Force - Pipeline - Input komitmen**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 56.1 | Membuka menu input komitmen |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman Dashboard Validate Pipeline. - [Success] |

|  |  |
| --- | --- |
| 56.2 | Input komitmen |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan data sesuai dengan bulan yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 56.3 | Input komitmen menggunakan huruf (Negative test) |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail pipeline data kantor cabang. - [Success] |

|  |  |
| --- | --- |
| 56.4 | Mengubah nilai komitmen |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilka list history validation. - [Success] |

|  |  |
| --- | --- |
| 56.5 | Mengembalikan nilai komitment menjadi 0 |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail Validate pipeline. - [Success] |

|  |  |
| --- | --- |
| 56.6 | Mengunduh data |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan halaman detail pipeline data kantor cabang. - [Success] |

# **57. Modul Kalender**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 57.1 | Membuka halaman Kalender |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Kalender beserta ringkasan status dan grid kalender. - [Success] |

|  |  |
| --- | --- |
| 57.2 | Melakukan navigasi periode kalender |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah tampilan periode kalender sesuai pilihan. - [Success] |

|  |  |
| --- | --- |
| 57.3 | Mengubah mode tampilan kalender |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan kalender berdasarkan mode tampilan yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 57.4 | Memfilter entri kalender berdasarkan kategori |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan entri kalender sesuai kategori yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 57.5 | Menambahkan task baru |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan task baru ke dalam kalender. - [Success] |

|  |  |
| --- | --- |
| 57.6 | Menambahkan acara baru |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan acara baru ke dalam kalender. - [Success] |

|  |  |
| --- | --- |
| 57.7 | Menambahkan label baru |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan label baru dan menampilkan notifikasi sukses. - [Success] |

|  |  |
| --- | --- |
| 57.8 | Menghapus label |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus label dari sistem. - [Success] |

|  |  |
| --- | --- |
| 57.9 | Membuka halaman Daftar Task |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Daftar Task. - [Success] |

|  |  |
| --- | --- |
| 57.10 | Melakukan filter Daftar Task |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data task sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 57.11 | Mencari task dengan keyword valid |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data task yang sesuai dengan kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 57.12 | Mencari task dengan keyword tidak valid |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data task tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 57.13 | Mereset filter Daftar Task |
| ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan seluruh data task ke kondisi default. - [Success] |

|  |  |
| --- | --- |
| 57.14 | Memulai pengerjaan task |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah status task menjadi Berjalan. - [Success] |

|  |  |
| --- | --- |
| 57.15 | Membuka kembali task yang telah selesai |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka kembali task. - [Success] |

|  |  |
| --- | --- |
| 57.16 | Membatalkan task |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membatalkan task. - [Success] |

|  |  |
| --- | --- |
| 57.17 | Mengubah data task |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengubah data task. - [Success] |

|  |  |
| --- | --- |
| 57.18 | Menghapus task secara permanen |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus task secara permanen. - [Success] |

|  |  |
| --- | --- |
| 57.19 | Membagikan task kepada user |
| ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membagikan task kepada user. - [Success] |

|  |  |
| --- | --- |
| 57.20 | Menghapus penugasan task kepada user |
| ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus penugasan task kepada user. - [Success] |

# **58. Modul Report Funding - Personal Funnel**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 58.1 | Membuka halaman Personal Funnel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Personal Funnel. - [Success] |

|  |  |
| --- | --- |
| 58.2 | Melakukan filter data Personal Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 58.3 | Melakukan filter data Personal Funnel tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 58.4 | Mengekspor data Personal Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **59. Modul Report Funding - Rekap Funnel**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 59.1 | Membuka halaman Rekap Funnel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Rekap Funnel. - [Success] |

|  |  |
| --- | --- |
| 59.2 | Melakukan filter data Rekap Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Rekap Funnel yang sesuai dengan kriteria filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 59.3 | Melakukan filter data Rekap Funnel tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 59.4 | Mereset filter data Rekap Funnel |
| ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengosongkan kriteria filter dan mengembalikan kondisi filter ke default. - [Success] |

|  |  |
| --- | --- |
| 59.5 | Mengekspor data Rekap Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **60. Modul Report Funding - Pengaturan Funnel**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 60.1 | Membuka halaman Pengaturan Funnel Funding |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Pengaturan Funnel Funding. - [Success] |

|  |  |
| --- | --- |
| 60.2 | Mengubah data Pengaturan Funnel Funding |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Funding. - [Success] |

|  |  |
| --- | --- |
| 60.3 | Mengubah data Pengaturan Funnel Funding tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field mandatory harus diisi. - [Success] |

|  |  |
| --- | --- |
| 60.4 | Menambahkan Kondisi pada Indikator Performa |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan condition baru pada Performance Indicator. - [Success] |

|  |  |
| --- | --- |
| 60.5 | Menghapus Kondisi pada Indikator Performa |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Funding. - [Success] |

|  |  |
| --- | --- |
| 60.6 | Menambahkan Operator pada Kondisi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Funding. - [Success] |

|  |  |
| --- | --- |
| 60.7 | Menghapus Operator pada Kondisi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Funding. - [Success] |

# **61. Modul Report Funding - Daily Sales Agenda**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 61.1 | Membuka halaman Daily Sales Agenda |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Daily Sales Agenda. - [Success] |

|  |  |
| --- | --- |
| 61.2 | Melakukan filter data Daily Sales Agenda |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 61.3 | Melakukan filter data Daily Sales Agenda tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 61.4 | Menampilkan data tab Prospek Masuk |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Masuk. - [Success] |

|  |  |
| --- | --- |
| 61.5 | Mencari data Prospek Masuk dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 61.6 | Mencari data Prospek Masuk dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 61.7 | Melihat detail Prospek Masuk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 61.8 | Mengekspor data tab Prospek Masuk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 61.9 | Menampilkan data tab Prospek Closing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Closing. - [Success] |

|  |  |
| --- | --- |
| 61.10 | Mencari data Prospek Closing dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 61.11 | Mencari data Prospek Closing dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 61.12 | Melihat detail Prospek Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 61.13 | Mengekspor data tab Prospek Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 61.14 | Menampilkan data tab Prospek Referal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Referal. - [Success] |

|  |  |
| --- | --- |
| 61.15 | Mencari data Prospek Referal dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 61.16 | Mencari data Prospek Referal dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 61.17 | Melihat detail Prospek Referal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 61.18 | Mengekspor data tab Prospek Referal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 61.19 | Menampilkan data tab Prospek Referal Closing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Referal Closing. - [Success] |

|  |  |
| --- | --- |
| 61.20 | Mencari data Prospek Referal Closing dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 61.21 | Mencari data Prospek Referal Closing dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 61.22 | Melihat detail Prospek Referal Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 61.23 | Mengekspor data tab Prospek Referal Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **62. Modul Report Lending - Personal Funnel**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 62.1 | Membuka halaman Personal Funnel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Personal Funnel. - [Success] |

|  |  |
| --- | --- |
| 62.2 | Menampilkan data Personal Funnel berdasarkan tab |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Personal Funnel pada tab Semua, Non PKS, dan PKS. - [Success] |

|  |  |
| --- | --- |
| 62.3 | Melakukan filter data Personal Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 62.4 | Melakukan filter data Personal Funnel tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. - [Success] |

# **63. Modul Report Lending - Rekap Funnel**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 63.1 | Membuka halaman Rekap Funnel |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Rekap Funnel. - [Success] |

|  |  |
| --- | --- |
| 63.2 | Melakukan filter data Rekap Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Rekap Funnel yang sesuai dengan kriteria filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 63.3 | Melakukan filter data Rekap Funnel tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 63.4 | Mereset filter data Rekap Funnel |
| ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengosongkan kriteria filter dan mengembalikan kondisi filter ke default. - [Success] |

|  |  |
| --- | --- |
| 63.5 | Mengekspor data Rekap Funnel |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **64. Modul Report Lending - Pengaturan Funnel**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 64.1 | Membuka halaman Pengaturan Funnel Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Pengaturan Funnel Lending. - [Success] |

|  |  |
| --- | --- |
| 64.2 | Mengubah data Pengaturan Funnel Lending |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Lending. - [Success] |

|  |  |
| --- | --- |
| 64.3 | Mengubah data Pengaturan Funnel Lending tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field mandatory harus diisi. - [Success] |

|  |  |
| --- | --- |
| 64.4 | Menambahkan Kondisi pada Indikator Performa |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan condition baru pada Performance Indicator. - [Success] |

|  |  |
| --- | --- |
| 64.5 | Menghapus Kondisi pada Indikator Performa |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Lending. - [Success] |

|  |  |
| --- | --- |
| 64.6 | Menambahkan Operator pada Kondisi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Lending. - [Success] |

|  |  |
| --- | --- |
| 64.7 | Menghapus Operator pada Kondisi |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data Pengaturan Funnel Lending. - [Success] |

# **65. Modul Report Lending - Daily Sales Agenda**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 65.1 | Membuka halaman Daily Sales Agenda |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Daily Sales Agenda. - [Success] |

|  |  |
| --- | --- |
| 65.2 | Melakukan filter data Daily Sales Agenda |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 65.3 | Melakukan filter data Daily Sales Agenda tanpa mengisi field mandatory |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan pesan validasi bahwa field filter mandatory wajib diisi. - [Success] |

|  |  |
| --- | --- |
| 65.4 | Menampilkan data tab Prospek Masuk |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Masuk. - [Success] |

|  |  |
| --- | --- |
| 65.5 | Mencari data Prospek Masuk dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 65.6 | Mencari data Prospek Masuk dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 65.7 | Melihat detail Prospek Masuk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 65.8 | Mengekspor data tab Prospek Masuk |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 65.9 | Menampilkan data tab Prospek Closing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Closing. - [Success] |

|  |  |
| --- | --- |
| 65.10 | Mencari data Prospek Closing dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 65.11 | Mencari data Prospek Closing dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 65.12 | Melihat detail Prospek Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 65.13 | Mengekspor data tab Prospek Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 65.14 | Menampilkan data tab Prospek Referal |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Referal. - [Success] |

|  |  |
| --- | --- |
| 65.15 | Mencari data Prospek Referal dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 65.16 | Mencari data Prospek Referal dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 65.17 | Melihat detail Prospek Referal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 65.18 | Mengekspor data tab Prospek Referal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 65.19 | Menampilkan data tab Prospek Referal Closing |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data pada tab Prospek Referal Closing. - [Success] |

|  |  |
| --- | --- |
| 65.20 | Mencari data Prospek Referal Closing dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 65.21 | Mencari data Prospek Referal Closing dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 65.22 | Melihat detail Prospek Referal Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail prospek. - [Success] |

|  |  |
| --- | --- |
| 65.23 | Mengekspor data tab Prospek Referal Closing |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **66. Modul Re-Assign dan Approval - Approval Non Banking**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 66.1 | Membuka halaman Approval non Banking |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Approval non Banking. - [Success] |

|  |  |
| --- | --- |
| 66.2 | Melakukan filter data Approval non Banking |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memfilter dan menampilkan data Approval non banking sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 66.3 | Mencari data dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data Approval non banking yang dicari. - [Success] |

|  |  |
| --- | --- |
| 66.4 | Mencari data dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 66.5 | Melakukan approval data prospek |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyetujui prospek. - [Success] |

|  |  |
| --- | --- |
| 66.6 | Melakukan reject data prospek |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menolak prospek. - [Success] |

|  |  |
| --- | --- |
| 66.7 | Melihat detail data prospek |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan detail data prospek. - [Success] |

# **67. Modul Re-Assign dan Approval - Re-Assign Prospek**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 67.1 | Membuka halaman Re-Assign Prospek |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Re-Assign Prospek. - [Success] |

|  |  |
| --- | --- |
| 67.2 | Melakukan filter data Re-Assign Prospek |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memfilter dan menampilkan data prospek sesuai kriteria. - [Success] |

|  |  |
| --- | --- |
| 67.3 | Mencari data dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data prospek yang dicari. - [Success] |

|  |  |
| --- | --- |
| 67.4 | Mencari data dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 67.5 | Melakukan re-assign beberapa data prospek |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan re-assign data prospek yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 67.6 | Melakukan re-assign semua data prospek |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan re-assign seluruh data prospek. - [Success] |

# **68. Modul Re-Assign dan Approval - Re-Assign Management**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 68.1 | Membuka halaman Re-Assign Management |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Re-Assign Management. - [Success] |

|  |  |
| --- | --- |
| 68.2 | Mencari data dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data prospek yang dicari. - [Success] |

|  |  |
| --- | --- |
| 68.3 | Mencari data dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 68.4 | Melakukan re-assign management |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil melakukan re-assign data prospek referral management. - [Success] |

# **69. Modul Export Center - Riwayat Export**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 69.1 | Membuka halaman Riwayat Export |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Riwayat Export. - [Success] |

|  |  |
| --- | --- |
| 69.2 | Mencari data riwayat export dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data riwayat export yang dicari. - [Success] |

|  |  |
| --- | --- |
| 69.3 | Mencari data riwayat export dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 69.4 | Melihat data riwayat export berdasarkan status |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar data riwayat export sesuai status yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 69.5 | Melakukan filter data riwayat export |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil memfilter dan menampilkan data riwayat export sesuai kriteria filter. - [Success] |

|  |  |
| --- | --- |
| 69.6 | Mereset filter data riwayat export |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mereset filter dan menampilkan seluruh data riwayat export. - [Success] |

|  |  |
| --- | --- |
| 69.7 | Melihat detail riwayat export |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan drawer Export Detail. - [Success] |

|  |  |
| --- | --- |
| 69.8 | Mengunduh file data export yang tersedia |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh file data export. - [Success] |

|  |  |
| --- | --- |
| 69.9 | Mengunduh data yang sudah di approve |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh data export. - [Success] |

|  |  |
| --- | --- |
| 69.10 | Membuka dokumen hasil download |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil membuka file hasil download. - [Success] |

|  |  |
| --- | --- |
| 69.11 | Melakukan filter data pada tab Riwayat Export |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 69.12 | Mencari data pada kolom pencarian |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data sesuai kata kunci pencarian. - [Success] |

|  |  |
| --- | --- |
| 69.13 | Mencari data kata kunci salah |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan keterangan data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 69.14 | Melakukan filter data pada tab Semua Request |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data sesuai filter yang dipilih pada tab Semua Request. - [Success] |

|  |  |
| --- | --- |
| 69.15 | Mencari data pada kolom pencarian tab Semua Request |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan data sesuai kata kunci pada tab Semua Request. - [Success] |

|  |  |
| --- | --- |
| 69.16 | Mencari data kata kunci salah tab Semua Request |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Menampilkan keterangan data tidak ditemukan pada tab Semua Request. - [Success] |

|  |  |
| --- | --- |
| 69.17 | Validasi card menunggu approval dengan data table |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil Jumlah data pada card dan table sesuai. - [Success] |

# **70. Modul Export Center - Persetujuan Export**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 70.1 | Membuka halaman Persetujuan Export |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Persetujuan Export. - [Success] |

|  |  |
| --- | --- |
| 70.2 | Mencari data persetujuan export dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data persetujuan export yang dicari. - [Success] |

|  |  |
| --- | --- |
| 70.3 | Mencari data persetujuan export dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 70.4 | Melihat data persetujuan export berdasarkan status |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar data persetujuan export sesuai status yang dipilih. - [Success] |

# **71. Modul Export Center - Aktivitas Export**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 71.1 | Membuka halaman Aktivitas Export |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Aktivitas Export. - [Success] |

|  |  |
| --- | --- |
| 71.2 | Mencari data aktivitas export dengan kata kunci valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data aktivitas export yang dicari. - [Success] |

|  |  |
| --- | --- |
| 71.3 | Mencari data aktivitas export dengan kata kunci tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 71.4 | Melihat data aktivitas export berdasarkan status |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan daftar data aktivitas export sesuai status yang dipilih. - [Success] |

# **72. Modul Ticket Maintenance - Aktivitas Issue**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 72.1 | Membuka halaman Aktivitas Issue |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Aktivitas Issue. - [Success] |

|  |  |
| --- | --- |
| 72.2 | Melakukan filter data Aktivitas Issue |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 72.3 | Mencari data Aktivitas Issue dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 72.4 | Menambahkan pelaporan issue baru |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data pelaporan issue. - [Success] |

|  |  |
| --- | --- |
| 72.5 | Melihat detail pelaporan issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail issue. - [Success] |

|  |  |
| --- | --- |
| 72.6 | Mengubah data pelaporan issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan data issue. - [Success] |

|  |  |
| --- | --- |
| 72.7 | Menambahkan komentar pada detail aktivitas issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan komentar pada detail issue. - [Success] |

|  |  |
| --- | --- |
| 72.8 | Menghapus data pelaporan issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data issue. - [Success] |

# **73. Modul Ticket Maintenance - Kategori Aktivitas Issue**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 73.1 | Membuka halaman Master Kategori Issue |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Master Kategori Issue. - [Success] |

|  |  |
| --- | --- |
| 73.2 | Menambahkan kategori lain melalui pelaporan issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menambahkan data kategori baru ke List Kategori Lain. - [Success] |

|  |  |
| --- | --- |
| 73.3 | Menambahkan data master kategori |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan data master kategori. - [Success] |

|  |  |
| --- | --- |
| 73.4 | Mencari data pada List Kategori Lain |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 73.5 | Melihat detail data kategori pada List Kategori Lain |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan modal detail kategori. - [Success] |

|  |  |
| --- | --- |
| 73.6 | Mengirim data kategori lain ke master kategori |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengirim data kategori lain ke master kategori. - [Success] |

|  |  |
| --- | --- |
| 73.7 | Mengirim data kategori lain ke master kategori secara massal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengirim beberapa kategori lain terpilih ke master kategori. - [Success] |

|  |  |
| --- | --- |
| 73.8 | Mencari data pada List Kategori |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 73.9 | Melihat dan mengubah data master kategori |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan dan memperbarui data master kategori. - [Success] |

# **74. Modul Ticket Maintenance - Dashboard Aktivitas Issue**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 74.1 | Membuka halaman Dashboard Aktivitas Issue |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Dashboard Aktivitas Issue. - [Success] |

|  |  |
| --- | --- |
| 74.2 | Melakukan filter data Dashboard Aktivitas Issue |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 74.3 | Melihat detail issue pada tabel 5 Newest Issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail issue. - [Success] |

# **75. Modul Ticket Maintenance - Report Aktivitas Issue**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 75.1 | Membuka halaman Report Aktivitas Issue |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Report Aktivitas Issue. - [Success] |

|  |  |
| --- | --- |
| 75.2 | Melakukan filter data Report Aktivitas Issue |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 75.3 | Mencari data Report Aktivitas Issue dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 75.4 | Melihat detail report aktivitas issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman detail issue. - [Success] |

|  |  |
| --- | --- |
| 75.5 | Menghapus data report aktivitas issue secara massal |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menghapus data report aktivitas issue. - [Success] |

|  |  |
| --- | --- |
| 75.6 | Mengekspor data Report Aktivitas Issue |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **76. Modul Dashboard - Aktivitas Consumer Funding**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 76.1 | Membuka halaman Dashboard Aktivitas Consumer Funding |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Dashboard Aktivitas Consumer Funding. - [Success] |

|  |  |
| --- | --- |
| 76.2 | Melakukan filter data Dashboard Aktivitas Consumer Funding |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 76.3 | Mencari data pada tabel Aktivitas Sales dengan keyword valid |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 76.4 | Mencari data pada tabel Aktivitas Sales dengan keyword tidak valid |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 76.5 | Mengekspor data tabel Aktivitas Sales |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 76.6 | Mencari data pada tabel Aktivitas Referral dengan keyword valid |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 76.7 | Mencari data pada tabel Aktivitas Referral dengan keyword tidak valid |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 76.8 | Mengekspor data tabel Aktivitas Referral |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **77. Modul Dashboard - Aktivitas Consumer Lending**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 77.1 | Membuka halaman Dashboard Aktivitas Consumer Lending |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Dashboard Aktivitas Consumer Lending. - [Success] |

|  |  |
| --- | --- |
| 77.2 | Melakukan filter data Dashboard Aktivitas Consumer Lending |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data sesuai dengan filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 77.3 | Mencari data pada tabel Aktivitas Sales dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 77.4 | Mencari data pada tabel Aktivitas Sales dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 77.5 | Mengekspor data tabel Aktivitas Sales |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

|  |  |
| --- | --- |
| 77.6 | Mencari data pada tabel Aktivitas Referral dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang dicari. - [Success] |

|  |  |
| --- | --- |
| 77.7 | Mencari data pada tabel Aktivitas Referral dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan informasi bahwa data tidak ditemukan. - [Success] |

|  |  |
| --- | --- |
| 77.8 | Mengekspor data tabel Aktivitas Referral |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mendownload file export. - [Success] |

# **78. Modul Dashboard - Pengaturan Aktivitas Consumer**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 78.1 | Membuka halaman Pengaturan Aktivitas Consumer |
|  | ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Pengaturan Aktivitas Consumer. - [Success] |

|  |  |
| --- | --- |
| 78.2 | Mengubah role pada Pengaturan Aktivitas Consumer Funding |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan role pada Pengaturan Aktivitas Consumer Funding. - [Success] |

|  |  |
| --- | --- |
| 78.3 | Mengubah role pada Pengaturan Aktivitas Consumer Lending |
|  | ![](data:image/jpeg;base64...)  ![](data:image/jpeg;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menyimpan perubahan role pada Pengaturan Aktivitas Consumer Lending. - [Success] |

# **79. Modul Dashboard - Optimalisasi Database**

|  |  |
| --- | --- |
| **No.** | **User Acceptance Testing (UAT)** |
| 79.1 | Membuka halaman Dashboard Optimalisasi Database |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan halaman Dashboard Optimalisasi Database. - [Success] |

|  |  |
| --- | --- |
| 79.2 | Melakukan filter data Dashboard Optimalisasi Database |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data dashboard dan bagan alur optimalisasi sesuai filter yang dipilih. - [Success] |

|  |  |
| --- | --- |
| 79.3 | Mencari data pada tabel dengan keyword valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil menampilkan data yang sesuai dengan keyword pencarian. - [Success] |

|  |  |
| --- | --- |
| 79.4 | Mencari data pada tabel dengan keyword tidak valid |
|  | ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Menampilkan keterangan data tidak ditemukan / tabel kosong. - [Success] |

|  |  |
| --- | --- |
| 79.5 | Mengekspor data tabel Optimalisasi Database |
|  | ![](data:image/png;base64...)  ![](data:image/png;base64...)  ![](data:image/png;base64...) |
| **Hasil yang diharapkan [STATUS]:**  Berhasil mengunduh file data tabel dalam format Excel (.xlsx). - [Success] |