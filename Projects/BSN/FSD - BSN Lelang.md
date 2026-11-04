---
title: Functional Specification Document (FSD) - BSN Lelang
project: BSN Lelang
source: BSN Template - FSD.docx
version: 1.0
vendor: PT Zegen Solusi Mandiri
client: PT Bank Syariah Nasional
date_converted: 2026-10-27
tags:
  - fsd
  - bsn
  - lelang
  - requirement
  - flow-process
  - use-case
  - architecture
---

# Functional Specification Document (FSD) - BSN Lelang

> [!NOTE] Dokumentasi Master FSD BSN Lelang
> Dokumen ini dikonversi dari file `BSN Template - FSD.docx` menggunakan **MarkItDown** dengan 145 gambar, diagram alur, use case, dan arsitektur yang diekstrak secara rapi ke dalam folder aset di `FSD/assets/`.
> 
> **Pusat Navigasi Modul & Alur Bisnis:**
> - 📑 [[FSD/00 - Index & Dokumen Overview|00 - Index & Ringkasan Dokumen]]
> - 🔄 [[FSD/01 - Alur & Flowchart Fitur Internal|01 - Alur & Flowchart Fitur Internal (Backoffice)]]
> - 🌐 [[FSD/02 - Alur & Flowchart Fitur Eksternal & Developer|02 - Alur & Flowchart Fitur Eksternal & Developer]]
> - 🔐 [[FSD/03 - Matriks Fitur & Hak Akses Role (CRUD)|03 - Matriks Fitur & Hak Akses Role (505 Matriks Hak Akses)]]
> - 🏗️ [[FSD/04 - Arsitektur Sistem & Integrasi Middleware|04 - Arsitektur Sistem & Integrasi Middleware]]
> - 📊 [[FSD/05 - Modul Pelaporan & Keamanan (STRIDE)|05 - Modul Pelaporan & Keamanan (STRIDE)]]

---

/

![Cover Ornament](file:///D:/Project/BSN/Fase%201/FSD/assets/00_common/common_01_cover_decor.png)

**![Logo BSN](file:///D:/Project/BSN/Fase%201/FSD/assets/00_common/common_02_bsn_logo.png)**

**PT. Bank Syariah Nasional**

**[Kode Project] – [Nama Project]**

| **Version**: 1.0 | **Revision Date**: [Date] |
| --- | --- |

Informasi terkait dengan jenis pengembangan pada project yang berjalan:

| NAMA VENDOR | : | PT Zegen Solusi Mandiri | |
| --- | --- | --- | --- |
| DIVISI OWNER | : | DBG – Usein Akbar, Abdul Khaloq Al Bari | |
| DIVISI USER | : | CAM -- DBG | |
| SYSTEM ANALYST | : | Muhammad Rayhan Subhi | |
| JENIS PENGEMBANGAN | : | √ Aplikasi Baru | □ Perubahan/Penambahan Struktur Data |
|  | □ Penambahan/Perubahan Fitur | □ Perubahan / Migrasi Infrastruktur Aplikasi |
|  | □ Perubahan/Migrasi License |  |

**Daftar Isi**

[Informasi Dokumen 2](#_6c6h0n9xrnx6)

[Histori Perubahan Dokumen 2](#_1ce9j533tx24)

[A.](#_srarr7if6p5i) Daftar Istilah 3

[B.](#_ze3uevp84chf) Pendahuluan 4

[C.](#_jrnzq4y0tqyy) Kebutuhan Fungsional 6

[D.](#_7n4jwlb91rg7) Kebutuhan Konfigurasi Sistem 9

[E.](#_nj5s7wmrclz4) Kebutuhan Pelaporan 13

[F.](#_urci5jiud22a) Kebutuhan Keamanan 14

[G.](#_xdwt2agsi270) Lampiran 22

# Informasi Dokumen

| **Nama File** | Functional Specification Document BSN Lelang |
| --- | --- |
| **Tanggal** |  |
| **Versi** | 1.0 |

# Histori Perubahan Dokumen

| **No** | **Versi** | **Tanggal** | **Alasan Perubahan** | **Penulis** |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | 24 September |  | Carol R |
| 2 |  | 5 oktober |  |  |
| 3 |  | 12 Oktober |  |  |
| 4 |  | 26 Oktober |  |  |
| 5 |  |  |  |  |

# Daftar Istilah

**Arsitektur Aplikasi**

Struktur dan organisasi keseluruhan dari suatu aplikasi perangkat lunak, mencakup distribusi sistem, manajemen data, keamanan, kinerja, dan antarmuka pengguna.

**Aset Lelang**

Aset agunan pembiayaan bermasalah (kredit macet) yang dieksekusi Bank melalui mekanisme Lelang, Jual Bersama, Cessie, atau Surat Kuasa Menjual (SKM).

**Aset baru**

Aset baru/persediaan (indent atau ready stock) milik Bank atau mitra developer yang dipasarkan melalui BSN Lelang di luar mekanisme penyelesaian kredit macet.

**Lelang**

Mekanisme penjualan aset agunan melalui prosedur resmi di KPKNL sesuai ketentuan lelang yang berlaku.

**Jual Bersama**

Mekanisme penjualan aset agunan yang dilakukan bersama-sama antara Bank dan debitur/pemilik agunan di luar prosedur lelang KPKNL.

**Cessie**

Pengalihan hak tagih (piutang) Bank atas suatu pembiayaan bermasalah kepada pihak ketiga.

**SKM (Surat Kuasa Menjual)**

Surat kuasa dari debitur/pemilik agunan kepada Bank untuk menjual aset agunan guna penyelesaian kewajiban pembiayaan.

**Jual Sukarela**

Proses penjualan barang milik perorangan, kelompok, atau badan usaha swasta yang dilakukan atas kehendak dan kesadaran pemiliknya sendiri tanpa ada unsur paksaan atau putusan pengadilan.

**Banner**

Media promosi visual yang ditampilkan pada halaman eksternal BSN Lelang.

**Asset**

Segala sesuatu yang dimiliki Bank atau debitur yang memiliki nilai ekonomi, dalam konteks ini berupa tanah dan/atau bangunan agunan.

**Investor**

Pihak (individu/entitas) yang berminat membeli aset yang dipasarkan pada BSN Lelang.

**Ticket**

Catatan tindak lanjut atas peminatan (leads) yang telah memasuki tahap serius/negosiasi menuju transaksi.

# Pendahuluan

Dalam era digital yang terus berkembang, kebutuhan akan solusi inovatif untuk mengatasi tantangan penyelesaian aset bermasalah dan pemasaran aset properti menjadi semakin mendesak. Untuk menjawab tantangan ini, Bank BSN Syariah menghadirkan BSN Lelang, sebuah aplikasi digital yang dirancang untuk mengelola dan memasarkan aset agunan pembiayaan bermasalah (NPF) maupun aset baru/baru, sesuai prinsip syariah.

1. **Deskripsi Sistem aplikasi**

| **Properties** | **Value Properties** |
| --- | --- |
| **Nama Aplikasi** | BSN Lelang |
| **Kode Nama Aplikasi \*** | *Kode dan nama aplikasi* ***(Kode Nama Aplikasi)*** |
| **Deskripsi** | BSN Lelang adalah aplikasi berbasis web untuk menampilkan portofolio/agunan yang siap dijual maupun dilelang, mencakup 2 kategori utama aset: (1) Aset Lelang — aset agunan pembiayaan bermasalah yang dijual melalui mekanisme Lelang, Jual Bersama, Cessie, atau SKM; dan (2) Aset baru — aset baru/persediaan yang dipasarkan di luar mekanisme penyelesaian kredit macet. Tujuan aplikasi: mempercepat proses penjualan aset, menjangkau pasar lebih luas, meningkatkan transparansi transaksi, serta mendukung kepatuhan terhadap prinsip syariah dalam setiap mekanisme penjualan. |
| **Jenis Aplikasi** | Application |
| **PSE Lingkup Privat \*** | NO |
| **Data Retention** | Setelah 5 tahun |
| **Platform** | Web App |
| **Development Type** | In House |
| **Vendor Name** | Zegen Solusi Mandiri |
| **License Scheme** | Perpetual |
| **Deployment** | PaaS |
| **System Owner \*** | DBG |
| **Source Code** | YES |
| **Application URL** |  |
| **Implemented Year \*** | \* |
| **Log In Auth** | ***AD/Non-AD/ User Auth*** |
| **Kepemilikan** | ***Beli Putus*** |
| **PT & KK** | *Di isi oleh BP/ user owner* |

***Notes****: Properties bertanda \* diisi oleh BP atau PM*

1. **Ruang Lingkup**

| **Fitur** | **Release 1** | **Release 2** | **Release 3** |
| --- | --- | --- | --- |
| Autentikasi Internal | Web Version | - | - |
| Dashboard / Overview Aset Lelang | Web Version | - | - |
| Dashboard / Overview Aset Baru | Web Version |  |  |
| Customer Management – Leads Aset Lelang | Web Version | - | - |
| Customer Management – Leads Aset Baru | Web Version | - | - |
| Customer Management – Ticket Aset Lelang | Web Version | - | - |
| Customer Management – Ticket Aset Baru | Web Version | - | - |
| Stock Management – Aset Lelang | Web Version | - | - |
| Stock Management – Aset Baru | Web Version | - | - |
| Katalog Marketing – Aset Lelang | Web Version | - | - |
| Katalog Marketing – Aset Baru | Web Version | - | - |
| Sold out Asset (Aset Terjual) | Web Version | - | - |
| Favorite – Aset Lelang | Web Version | - | - |
| Favorite – Aset Baru | Web Version | - | - |
| Investor – Aset Lelang | Web Version | - | - |
| Investor – Aser Baru | Web Version | - | - |
| Approval – Aset Lelang | Web Version | - | - |
| Approval – Aset Baru | Web Version | - | - |
| Developer – List Developer | Web Version | - | - |
| Developer – Approval Developer | Web Version | - | - |
| Developer - Dashboard Developer | Web Version | - | - |
| Media & Management – FAQ | Web Version | - | - |
| Media & Management – Article | Web Version | - | - |
| Media & Management – Banner Setting | Web Version | - | - |
| User Management – User | Web Version | - | - |
| User Management – Role | Web Version | - | - |
| User Management – User External | Web Version | - | - |
| User Management – User Block | Web Version | - | - |
| Office Management - Tipe Kantor | Web Version | - | - |
| Office Management - Data Kantor | Web Version | - | - |
| Office Management - KPKNL | Web Version | - | - |
| Audit Trail | Web Version | - | - |
| Audit Log | Web Version | - | - |
| Report – Aset Lelang | Web Version | - | - |
| Report – Aset Baru | Web Version | - | - |
| Notifikasi | Web Version | - | - |
| Beranda (Eksternal) | Web Version | - | - |
| Autentikasi (External) | Web Version | - | - |
| Aset Lelang (Eksternal) | Web Version | - | - |
| Aset Baru (Eksternal) | Web Version | - | - |
| Jadwal Lelang (Eksternal) | Web Version | - | - |
| Panduan (External) | Web Version | - | - |
| Bandingkan Aset (External) | Web Version | - | - |
| Simulasi Pembiayaan (Eksternal) | Web Version | - | - |
| Tentang Kami (Eksternal) | Web Version | - | - |
| FAQ (Eksternal) | Web Version | - | - |
| Artikel (Eksternal) | Web Version | - | - |
| Favorit (Eksternal) | Web Version | - | - |
| Notifikasi (Eksternal) | Web Version | - | - |
| Daftar Pesanan (Eksternal) | Web Version | - | - |
| Profile User / Akun (Eksternal) | Web Version | - | - |
| Portal developer – Aset Kelolaan (Eksternal) | Web Version | - | - |
| Portal Developer – Form Input Aset (Eksternal) | Web Version | - | - |
| Portal Developer – List Leads (Eksternal) | Web Version | - | - |
| Portal Developer – Form Input Leads (Eksternal) | Web Version | - | - |
| Portal Developer - Dashboard Developer (Eksternal) | Web Version | - | - |
| Portal Developer - Keamanan (Eksternal) | Web Version | - | - |
| Portal Developer - Akun (Eksternal) | Web Version | - | - |

# Kebutuhan Fungsional

1. **Fitur Sistem Aplikasi**

| **No** | **Nama Menu/Fungsi Aplikasi** | **Nama Fitur per Fungsi Aplikasi** | **Nama Sub-Fitur Aplikasi** | **Deskripsi Menu/Fitur/Sub-Fitur** |
| --- | --- | --- | --- | --- |
| 1 | Autentikasi Internal | - | - | Halaman login untuk user internal Bank menggunakan email dan verifikasi kode OTP, dengan limit waktu 15 menit untuk kirim ulang OTP dan pembatasan akses login (akun terkunci setelah 3x salah kata sandi). |
| 2 | Dashboard / Overview | Aset Lelang | - | Menampilkan rekapan aktivitas BSN Lelang secara informatif: total VoA, total aset terjual, total peminat, statistik pertumbuhan (growth) transaksi per periode, transaksi terkini, peringkat aset diminati, dan urutan kategori penjualan. |
| 3 | Dashboard / Overview | Aset Baru | - | Menampilkan rekapan aktivitas BSN Aset baru secara informatif: total VoA, total aset terjual, total peminat, statistik pertumbuhan (growth) transaksi per periode, transaksi terkini, peringkat aset diminati, dan urutan kategori penjualan. |
| 4 | Customer Management | Leads | Aset Lelang | Memonitoring dan menindaklanjuti peminat (leads) yang mendaftarkan minat pada suatu aset. Dilengkapi mekanisme distribusi peminat otomatis (load balance) ke Sales/CS yangtersedia, serta fitur Edit PIC (khusus role Supervisor). |
| 5 | Customer Management | Leads | Aset Baru | Memonitoring dan menindaklanjuti peminat (leads) yang mendaftarkan minat pada suatu aset. Dilengkapi mekanisme distribusi peminat otomatis (load balance) ke Sales/CS yang tersedia, serta fitur Edit PIC (khusus role Supervisor). |
| 6 | Customer Management | Ticket | Aset Lelang | Mengelola aktivitas tiket transaksi (follow up peminat yang sudah masuk tahap serius) dengan staging: Belum Ada Sales → Perlu Follow Up → Berjalan → Selesai, termasuk validasi nominal wajib diisi dan tidak boleh melebihi total pokok + tunggakan bunga/margin + tunggakan denda saat proses Closing. |
| 7 | Customer Management | Ticket | Aset Baru | Mengelola aktivitas tiket transaksi (follow up peminat yang sudah masuk tahap serius) dengan staging: Belum Ada Sales → Perlu Follow Up → Berjalan → Selesai, termasuk validasi nominal wajib diisi dan tidak boleh melebihi total pokok + tunggakan bunga/margin + tunggakan denda saat proses Closing. |
| 8 | Stock Management | Aset Lelang | - | Mengelola data aset agunan pembiayaan bermasalah melalui wizard input bertahap: No. Rekening Debitur (inquiry ke Core Banking Syariah) → Informasi Aset → Pola Penjualan (Lelang/Jual Bersama/Cessie/SKM) → Dokumen (AJB, SKM/KUM, APHT, PH, IMB/PBG, PBB, PK, SHGB, Video 360, Foto) → Lokasi → Fasilitas. Dilengkapi indikator Akurasi Aset (persentase kelengkapan data) dan status Draft/Verifikasi/Publish. |
| 9 | Stock Management | Aset Baru | - | Mengelola data aset baru/persediaan (indent/ready stock) di luar mekanisme kredit macet, dengan field Status Aset (Indent/Ready) menggantikan No. Rekening Debitur; tahapan input sama seperti Aset Lelang untuk bagian Informasi Aset, Dokumen, Lokasi, dan Fasilitas. |
| 10 | Stock Management | Katalog Marketing | Aset Lelang | Membuat dan mengelola katalog pemasaran aset (Katalog General/Siap Jual dan Katalog Lelang) untuk unit Syariah Konsumer maupun Syariah Komersial, lengkap dengan pilihan cover dan fitur generate/simpan file. |
| 11 | Stock Management | Katalog Marketing | Aset Baru | Membuat dan mengelola katalog pemasaran aset (Katalog General/Siap Jual dan Katalog Lelang) untuk unit Syariah Konsumer maupun Syariah Komersial, lengkap dengan pilihan cover dan fitur generate/simpan file. |
| 12 | Stock Management | Out of Asset (Aset Terjual) | - | Memonitoring seluruh aset yang telah terjual, baik melalui Lelang, Jual Bersama, Cessie, SKM, Jual Sukarela maupun KPR. |
| 13 | Stock Management | Favorite | Aset Lelang | Melihat daftar aset lelang yang paling sering dilihat/difavoritkan oleh calon pembeli atau investor. |
| 14 | Stock Management | Favorite | Aset baru | Melihat daftar aset baru yang paling sering dilihat/difavoritkan oleh calon pembeli atau investor. |
| 15 | Stock Management | Investor | Aset Lelang | Memonitoring dan mengelola data investor aset lelang yang terdaftar beserta riwayat transaksinya. |
| 16 | Stock Management | Investor | Aset Baru | Memonitoring dan mengelola data investor aset baru yang terdaftar beserta riwayat transaksinya. |
| 17 | Stock Management | Approval | Aset Lelang | Pusat pengelolaan persetujuan atas permintaan input aset lelang dan permintaan unpublish aset, dengan sub-tab status (Semua/Menunggu Diproses/Disetujui/Ditolak) dan filter Kode Aset, Kantor Cabang, PIC Approval, dan Tanggal Verifikasi. |
| 18 | Stock Management | Approval | Aset Baru | Pusat pengelolaan persetujuan atas permintaan input aset baru dan permintaan unpublish aset, dengan sub-tab status (Semua/Menunggu Diproses/Disetujui/Ditolak) dan filter Kode Aset, Kantor Cabang, PIC Approval, dan Tanggal Verifikasi. |
| 19 | Developer | List Developer | - | Data developer mitra yang berkaitan dengan pengelolaan aset primary. Pengelompokan data akan dikelola terpisah berdasarkan tipe data Sold Out Aset dan Investor. |
| 20 | Developer | Approval Developer | - | Pusat pengelolaan data developer yang telah melakukan pendaftaran melalui website eksternal, mencakup proses peninjauan, verifikasi, dan tindak lanjut persetujuan (approve/reject) atas data yang diajukan, dengan pengelolaan status pendaftaran berdasarkan hasil review. |
| 21 | Developer | Dashboard Developer | - | Pusat pemantauan dan pengelolaan data developer mitra, khususnya yang berkaitan dengan aset primary, serta informasi terkait Sold Out Aset dan Investor. |
| 22 | Media & Management | FAQ | - | Membuat dan mengelola daftar pertanyaan beserta jawaban yang ditampilkan pada halaman eksternal BSN. |
| 23 | Media & Management | Article | - | Membuat dan mengelola artikel untuk ditampilkan pada halaman eksternal BSN. |
| 24 | Media & Management | Banner Setting | - | Mengatur dan mengelola banner promosi yang ditampilkan pada halaman eksternal BSN Lelang. |
| 25 | User Management | User | - | Mengatur seluruh user internal yang terdaftar pada BSN Lelang (create, read, update, delete). |
| 26 | User Management | Role | - | Mengatur hak akses (role) internal beserta daftar menu yang dapat diakses per role, termasuk akses khusus seperti Edit PIC. |
| 27 | User Management | User Block | - | Mengelola daftar user eksternal yang diblokir (manual maupun otomatis karena percobaan login gagal), lengkap dengan riwayat blokir/unblokir. |
| 28 | User Management | Management User External | - | Membuat, mengubah, dan menonaktifkan akun pengguna, serta mengatur penetapan role dan kantor cabang sesuai kebutuhan. |
| 29 | Office Management | Tipe Kantor | - | Mengatur jenis/tipe kantor Bank (Kantor Pusat – Wilayah – Cabang – Kantor Kas). |
| 30 | Office Management | Data Kantor | - | Mengatur dan memonitoring data kantor cabang/wilayah yang terdaftar. |
| 31 | Office Management | KPKNL | - | Mengatur dan memonitoring data Kantor Pelayanan Kekayaan Negara dan Lelang (KPKNL) mitra lelang. |
| 32 | Audit Trail | - | - | Mencatat dan menampilkan seluruh aktivitas yang dilakukan user maupun sistem (termasuk aktivitas melalui API) sebagai jejak audit yang lengkap dan transparan. |
| 33 | Audit Log | - | - | Mencatat dan menampilkan riwayat aktivitas pengguna dan sistem sebagai dokumentasi serta pemantauan aktivitas untuk kebutuhan audit. |
| 34 | Report | Aset Lelang | - | Menampilkan rekapan transaksi dan aktivitas: total aset lelang, aset terjual, investor, peminat, beserta fitur download/export data. |
| 35 | Report | Aset Baru | - | Menampilkan rekapan transaksi dan aktivitas: total aset baru, aset terjual, investor, peminat, beserta fitur download/export data. |
| 36 | Notifikasi | - | - | Menampilkan kumpulan notifikasi internal yang diterima admin terkait aktivitas sistem, pengajuan atau permintaan yang perlu ditindaklanjuti, dan pembaruan layanan BSN. |
| 37 | Autentikasi External | - | - | Halaman login untuk user external (nasabah & developer) menggunakan email dan verifikasi kode OTP, dengan limit waktu 15 menit untuk kirim ulang OTP dan pembatasan akses login (akun terkunci setelah 3x salah kata sandi). |
| 38 | Beranda (Eksternal) | - | - | Halaman utama BSN Lelang yang menampilkan katalog aset (Lelang/Jual/Cessie/Jual Bersama), pencarian, dan ringkasan FAQ. |
| 39 | Aset Lelang (Eksternal) | - | - | Payung data 5 pola penjualan: Lelang, Jual Bersama, Cessie, SKM, Jual Sukarela (sebelumnya "Aset NPL"). |
| 40 | Aset Baru (Eksternal) | - | - | Data aset baru dari developer, status Indent/Ready (sebelumnya "Aset baru"). |
| 41 | Jadwal Lelang (Eksternal) | - | - | Menampilkan estimasi/perkiraan jadwal dan informasi lelang suatu aset, dengan filter Nearby, Jenis Rumah, Harga, Jumlah Lantai, dan Tanggal. |
| 42 | Simulasi Pembiayaan (Eksternal) | - | - | Menyediakan simulasi pembiayaan berbasis akad syariah untuk calon pembeli aset, menampilkan rincian pembiayaan dan angsuran sesuai skema yang berlaku. |
| 43 | Bandingkan Aset | - | - | Menyediakan fitur untuk membandingkan sampai dengan 4 aset dari sisi harga, fasilitas, dll |
| 44 | Panduan | (Lelang, SKM, Jual Bersama, Jual Sukarela, Cessie, KPR) | - | Berisi Informasi Panduan untuk nasabah jika akan melakukan pembelian Lelang, SKM, Jual bersama, Jual Sukarela dan cessie |
| 45 | Tentang Kami (Eksternal) | - | - | Menyediakan informasi profil Bank BSN Syariah dan layanan BSN Lelang. |
| 46 | FAQ (Eksternal) | - | - | Pusat bantuan berisi daftar pertanyaan yang sering diajukan terkait proses jual-beli/lelang aset. |
| 47 | Artikel (Eksternal) | - | - | Menampilkan kumpulan artikel/berita terkait Bank BSN Syariah dan layanan BSN. |
| 48 | Notifikasi (Eksternal) | - | - | Menampilkan kumpulan pemberitahuan terkait aktivitas transaksi, informasi akun, promo, dan layanan Bank BSN Syariah yang diterima nasabah. |
| 49 | Profile User / Akun (Eksternal) | Favorit (Eksternal) | - | Aset Lelang yang ditandai favorit oleh calon nasabah akan terkumpul dan terdata pada menu ini |
| 50 | Profile User / Akun (Eksternal) | Daftar Pesanan (Eksternal) | - | Riwayat dan Daftar Pesanan yang dibuat oleh nasabah akan terdata pada menu ini. |
| 51 | Profile User / Akun (Eksternal) | - | - | Menampilkan data akun, biodata user eksternal (nasabah/calon pembeli/investor). |
| 52 | Portal Developer (Eksternal) | Aset Kelolaan | - | List aset (Aset Baru) yang terhubung ke akun developer ini. Data dibatasi hanya aset miliknya sendiri (row-level access). |
| 53 | Portal Developer (Eksternal) | Form Input Aset |  | Developer bisa submit aset baru miliknya sendiri. Hasil submit WAJIB melalui Approval Aset internal BSN sebelum publish — tidak ada auto-publish dari eksternal. |
| 54 | Portal Developer (Eksternal) | List Leads |  | Leads yang masuk untuk aset-aset milik developer ini. |
| 55 | Portal Developer (Eksternal) | Form Input Leads |  | Developer bisa input manual leads (misal calon pembeli yang datang langsung ke kantor developer). Leads dari form ini diberi tanda sumber “Input Developer”, terpisah dari leads organik yang masuk dari platform — untuk mitigasi risiko leads fiktif. |
| 56 | Portal Developer (Eksternal) | Dashboard Developer |  | Menampilkan ringkasan informasi dan aktivitas akun developer pada portal, seperti statistik penggunaan API, status integrasi, serta akses cepat ke dokumentasi dan layanan BSN yang tersedia bagi mitra eksternal. |
| 57 | Portal Developer (Eksternal) | Akun |  | Menampilkan informasi profil dan pengaturan akun developer pada portal, seperti data pribadi atau perusahaan, kredensial login, pengaturan keamanan, serta pengelolaan akses mitra eksternal. |
| 58 | Portal Developer (Eksternal) | Keamanan |  | Menampilkan dan mengelola pengaturan keamanan akun developer pada portal, seperti perubahan kata sandi, autentikasi dua faktor (2FA), pengelolaan API key dan token akses, serta riwayat login dan sesi aktif. |

![UI Internal - Login](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_01_login.png)

*[Gambar 1.1 – Login]*

![UI Internal - Dashboard / Overview – Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_02_dashboard_overview_-_aset_lelang.png)

*[Gambar 1.2 – Dashboard / Overview – Aset Lelang]*

*![UI Internal - Dashboard / Overview – Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_03_dashboard_overview_-_aset_baru.png)*

*[Gambar 1.3 – Dashboard / Overview – Aset Baru]*

*![UI Internal - Customer Management – Leads - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_04_customer_management_-_leads_-_aset_lelang.png)*

*[Gambar 1.4 – Customer Management – Leads - Aset Lelang]*

*![UI Internal - Customer Management – Leads - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_05_customer_management_-_leads_-_aset_baru.png)*

*[Gambar 1.5 – Customer Management – Leads - Aset Baru]*

*![UI Internal - Customer Management – Ticket - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_06_customer_management_-_ticket_-_aset_lelang.png)*

*[Gambar 1.6 – Customer Management – Ticket - Aset Lelang]*

*![UI Internal - Customer Management – Ticket - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_07_customer_management_-_ticket_-_aset_baru.png)*

*[Gambar 1.7 – Customer Management – Ticket - Aset Baru]*

*![UI Internal - Stock Management – Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_08_stock_management_-_aset_lelang.png)*

*[Gambar 1.8 – Stock Management – Aset Lelang]*

*![UI Internal - Stock Management  – Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_09_stock_management_-_aset_baru.png)*

*[Gambar 1.9 – Stock Management – Aset Baru]*

*![UI Internal - Katalog Marketing - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_10_katalog_marketing_-_aset_lelang.png)*

*[Gambar 1.10 – Katalog Marketing - Aset Lelang]*

*![UI Internal - Katalog Marketing - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_11_katalog_marketing_-_aset_baru.png)*

*[Gambar 1.11 – Katalog Marketing - Aset Baru]*

*![UI Internal - Sold out Aset](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_12_sold_out_aset.png)*

*[Gambar 1.12 – Sold out Aset]*

*![UI Internal - Favorit - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_13_favorit_-_aset_lelang.png)*

*[Gambar 1.13 – Favorit - Aset Lelang]*

*![UI Internal - Favorit - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_14_favorit_-_aset_baru.png)*

*[Gambar 1.14 – Favorit - Aset Baru]*

*![UI Internal - Investor - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_15_investor_-_aset_lelang.png)*

*[Gambar 1.15 – Investor - Aset Lelang]*

*![UI Internal - Investor - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_16_investor_-_aset_baru.png)*

*[Gambar 1.16 – Investor - Aset Baru]*

*![UI Internal - Approval Aset - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_17_approval_aset_-_aset_lelang.png)*

*[Gambar 1.17 – Approval Aset - Aset Lelang]*

*![UI Internal - Approval Aset - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_18_approval_aset_-_aset_baru.png)*

*[Gambar 1.18 – Approval Aset - Aset Baru]*

*![UI Internal - Developer - List Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_19_developer_-_list_developer.png)*

*[Gambar 1.19 – Developer - List Developer]*

*![UI Internal - Developer - Approval Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_20_developer_-_approval_developer.png)*

*[Gambar 1.20 – Developer - Approval Developer]*

*![UI Internal - Developer - Dashboard Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_21_developer_-_dashboard_developer.jpg)*

*[Gambar 1.21 – Developer - Dashboard Developer]*

*[Gambar 1.22 – Media & Information - FAQ]*

*![UI Internal - Media & Information - Article](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_22_media_information_-_article.png)*

*[Gambar 1.23 – Media & Information - Article]*

*![UI Internal - Media & Information - Banner Setting](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_23_media_information_-_banner_setting.png)*

*[Gambar 1.24 – Media & Information - Banner Setting]*

*![UI Internal - User Management – User](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_24_user_management_-_user.png)*

*[Gambar 1.25 – User Management – User]*

*![UI Internal - User Management – Role](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_25_user_management_-_role.png)*

*[Gambar 1.26 – User Management – Role]*

*![UI Internal - User Management - User External ](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_26_user_management_-_user_external.png)*

*[Gambar 1.27 – User Management - User External ]*

*![UI Internal - User Management - User Block](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_27_user_management_-_user_block.png)*

*[Gambar 1.28 – User Management - User Block]*

*![UI Internal - Office Management - Tipe Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_28_office_management_-_tipe_kantor.png)*

*[Gambar 1.29 – Office Management - Tipe Kantor]*

*![UI Internal - Office Management - Data Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_29_office_management_-_data_kantor.png)*

*[Gambar 1.30 – Office Management - Data Kantor]*

*[Gambar 1.31 – Office Management - KPKNL]*

*![UI Internal - Audit Trail](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_30_audit_trail.png)*

*[Gambar 1.32 – Audit Trail]*

*![UI Internal - Audit Log](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_31_audit_log.png)*

*[Gambar 1.33 – Audit Log]*

*![UI Internal - Report - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_32_report_-_aset_lelang.png)*

*[Gambar 1.34 – Report - Aset Lelang]*

*![UI Internal - Report - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_33_report_-_aset_baru.png)*

*[Gambar 1.35 – Report - Aset Baru]*

*![UI Internal - Notifikasi](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_34_notifikasi.png)*

*[Gambar 1.36 – Notifikasi]*

*![UI Internal - Akun](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_35_akun.png)*

*[Gambar 1.37 – Akun]*

*![UI Internal - Beranda (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_36_beranda_eksternal.png)*

*[Gambar 1.38 – Beranda (Eksternal)]*

*![UI Eksternal - Login (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_37_login_eksternal.png)*

*[Gambar 1.39 – Login (Eksternal)]*

*![UI Eksternal - Aset Lelang (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_38_aset_lelang_eksternal.png)*

*[Gambar 1.40 – Aset Lelang (Eksternal)]*

*![UI Eksternal - Aset Baru (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_39_aset_baru_eksternal.png)*

*[Gambar 1.41 – Aset Baru (Eksternal)]*

*![UI Eksternal - Jadwal Lelang (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_40_jadwal_lelang_eksternal.jpg)*

*[Gambar 1.42 – Jadwal Lelang (Eksternal)]*

*![UI Eksternal - Simulasi Pembiayaan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_41_simulasi_pembiayaan_eksternal.png)[*

*Gambar 1.43 – Simulasi Pembiayaan (Eksternal)]*

*![UI Eksternal - Bandingkan Aset (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_42_bandingkan_aset_eksternal.png)*

*[Gambar 1.44 – Bandingkan Aset (Eksternal)]*

*![UI Eksternal - Panduan Lelang (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_43_panduan_lelang_eksternal.png)*

*[Gambar 1.45 – Panduan Lelang (Eksternal)]*

*![UI Eksternal - Panduan Cessie (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_44_panduan_cessie_eksternal.png)*

*[Gambar 1.46 – Panduan Cessie (Eksternal)]*

*![UI Eksternal - Panduan Jual Bersama (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_45_panduan_jual_bersama_eksternal.png)*

*[Gambar 1.47 – Panduan Jual Bersama (Eksternal)]*

*![UI Eksternal - Panduan SKM (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_46_panduan_skm_eksternal.png)*

*[Gambar 1.48 – Panduan SKM (Eksternal)]*

*![UI Eksternal - Panduan KPR (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_47_panduan_kpr_eksternal.png)*

*[Gambar 1.49 – Panduan KPR (Eksternal)]*

*![UI Eksternal - Panduan Penjualan Sukarela (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_48_panduan_penjualan_sukarela_eksternal.png)*

*[Gambar 1.50 – Panduan Penjualan Sukarela (Eksternal)]*

*![UI Eksternal - Tentang Kami (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_49_tentang_kami_eksternal.jpg)*

*[Gambar 1.51 – Tentang Kami (Eksternal)]*

*![UI Eksternal - FAQ (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_50_faq_eksternal.png)*

*[Gambar 1.52 – FAQ (Eksternal)]*

*![UI Eksternal - Article (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_51_article_eksternal.png)*

*[Gambar 1.53 – Article (Eksternal)]*

*![UI Eksternal - Profile User - Profile  (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_52_profile_user_-_profile_eksternal.png)*

*[Gambar 1.54 – Profile User - Profile (Eksternal)]*

*![UI Eksternal - Profile User - Akun (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_53_profile_user_-_akun_eksternal.png)*

*[Gambar 1.55 – Profile User - Akun (Eksternal)]*

*![UI Eksternal - Profile User - Favorit (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_54_profile_user_-_favorit_eksternal.png)*

*[Gambar 1.56 – Profile User - Favorit (Eksternal)]*

*![UI Eksternal - Profile User - Daftar Pesanan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_55_profile_user_-_daftar_pesanan_eksternal.png)*

*[Gambar 1.57 – Profile User - Daftar Pesanan (Eksternal)]*

*![UI Eksternal - Profile User - Notifikasi (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_56_profile_user_-_notifikasi_eksternal.jpg)*

*[Gambar 1.58 – Profile User - Notifikasi (Eksternal)]*

*![UI Eksternal - Portal Developer - Aset Kelolaan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_57_portal_developer_-_aset_kelolaan_eksternal.png)*

*[Gambar 1.59 – Portal Developer - Aset Kelolaan (Eksternal)]*

*![UI Eksternal - Portal Developer - Form Input Aset (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_58_portal_developer_-_form_input_aset_eksternal.png)*

*[Gambar 1.60 – Portal Developer - Form Input Aset (Eksternal)]*

*![UI Eksternal - Portal Developer- List Leads (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_59_portal_developer-_list_leads_eksternal.png)*

*[Gambar 1.61 – Portal Developer- List Leads (Eksternal)]*

*![UI Eksternal - Portal Developer - Form Input Leads (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_60_portal_developer_-_form_input_leads_eksternal.png)*

*[Gambar 1.62 – Portal Developer - Form Input Leads (Eksternal)]*

*![UI Eksternal - Portal Developer - Detail Leads (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_61_portal_developer_-_detail_leads_eksternal.png)*

*[Gambar 1.63 – Portal Developer - Detail Leads (Eksternal)]*

*![UI Eksternal - Portal Developer - Dashboard Developer (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_62_portal_developer_-_dashboard_developer_eksternal.png)*

*[Gambar 1.57 – Portal Developer - Dashboard Developer (Eksternal)*

*![UI Eksternal - Portal Developer - Akun (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_63_portal_developer_-_akun_eksternal.png)*

*[Gambar 1.58 – Portal Developer - Akun (Eksternal)]*

*![UI Eksternal - Portal Developer - Keamanan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/02_ui_external/ui_external_64_portal_developer_-_keamanan_eksternal.png)*

*[Gambar 1.59 – Portal Developer - Keamanan (Eksternal)]*

1. ***User Access Matrix* (UAM)**

| **No** | **Fitur / Menu** | **Role / Group** | **Akses (C/R/U/D)** |
| --- | --- | --- | --- |
| 1 | **Dashboard / Overview – Aset Lelang** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | R |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | R |
| DBM Supporting (Aset Lelang) | R |
| Nasabah | - |
| Developer | - |
| 2 | **Dashboard / Overview – Aset Baru** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | R |
| FSO (Aset Baru) | R |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 3 | **Customer Management – Leads (Aset Lelang)** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | R |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | R |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 4 | **Customer Management – Leads (Aset Baru)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | R |
| FSO (Aset Baru) | R |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 5 | **Customer Management – Ticket (Aset Lelang)** | Admin Pusat (Aset Lelang) | R |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | RUD |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 6 | **Customer Management – Ticket (Aset Baru)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | R |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | RUD |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 7 | **Stock Management – Aset Lelang** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | CRUD |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 8 | **Stock Management – Aset Lelang** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | CRUD |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 9 | **Stock Management – Katalog Marketing (Aset Lelang)** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | CRUD |
| DBM Supporting (Aset Lelang) | CRU |
| Nasabah | R |
| Developer | - |
| 10 | **Stock Management – Katalog Marketing (Aset Baru)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | CRUD |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 11 | **Stock Management – Sold Out Aset** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | R |
| CWO (Aset Lelang) | R |
| DBM Supporting (Aset Lelang) | R |
| Nasabah | - |
| Developer | - |
| 12 | **Stock Management – Favorit (Aset Lelang)** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 13 | **Stock Management – Favorit (Aset baru)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 14 | **Stock Management – Investor (Aset Lelang)** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | R |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 15 | **Stock Management – Investor (Aset Baru)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | R |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 16 | **Approval - Aset Lelang** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | CRUD |
| Nasabah | - |
| Developer | - |
| 17 | **Approval - Aset Baru** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 18 | **Developer - List Developer** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 19 | **Developer - Approval Developer** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 20 | **Developer - Dashboard Developer** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 21 | **Media & Management - FAQ** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 22 | **Media & Management – Article** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 23 | **Media & Management – Banner Setting** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 24 | **User Management - User** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 25 | **User Management - Role** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 26 | **User Management – User External** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 27 | **User Management – User Block** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 28 | **Office Manegement – Tipe Kantor / Cabang** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 29 | **Office Management – Data Kantor / Cabang** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | CRUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 30 | **Office Management – KPKNL** | Admin Pusat (Aset Lelang) | CRUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | CRUD |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 31 | **Audit Trail** | Admin Pusat (Aset Lelang) | R |
| Admin Pusat (Aset Baru) | R |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 32 | **Audit Log** | Admin Pusat (Aset Lelang) | R |
| Admin Pusat (Aset Baru) | R |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 33 | **Report – Aset Lelang** | Admin Pusat (Aset Lelang) | CR |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | R |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 34 | **Report – Aset Baru** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CR |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | R |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | - |
| 35 | **Notifikasi** | Admin Pusat (Aset Lelang) | R |
| Admin Pusat (Aset Baru) | R |
| Helpdesk (Aset Llelang) | R |
| Helpdesk (Aset Baru) | R |
| FSO (Aset Baru) | R |
| CWO (Aset Lelang) | R |
| DBM Supporting (Aset Lelang) | R |
| Nasabah | - |
| Developer | - |
| 36 | **Beranda (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 37 | **Asel Lelang (Ekxternal)** | Admin Pusat (Aset Lelang) | CUD |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | CR |
| Developer | - |
| 38 | **Aset Baru (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | CUD |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | CR |
| Developer | CU |
| 39 | **Jadwal Lelang (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 40 | **Simulasi Pembiayaan (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | CRU |
| Developer | - |
| 41 | **Bandingkan Aset (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | CRU |
| Developer | - |
| 42 | **Panduan (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 43 | **Tentang Kami (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 44 | **FAQ** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 45 | **Artikel (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 46 | **Favorit (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | CRU |
| Developer | - |
| 47 | **Notifikasi (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 48 | **Daftar Pesanan (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | R |
| Developer | - |
| 49 | **Profile User (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | CRU |
| Developer | - |
| 50 | **Portal Developer – Aset Kelolaan (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | CRUD |
| 51 | **Portal Developer – Form Input Aset (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | CRUD |
| 52 | **Portal Developer – List Aset (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | R |
| 53 | **Portal Developer – Form Input Aset (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | CRUD |
| 54 | **Portal Developer – Dashboard Developer (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | CRUD |
| 55 | **Portal Developer – Akun (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | CRU |
| 56 | **Portal Developer – Keamanan (Eksternal)** | Admin Pusat (Aset Lelang) | - |
| Admin Pusat (Aset Baru) | - |
| Helpdesk (Aset Llelang) | - |
| Helpdesk (Aset Baru) | - |
| FSO (Aset Baru) | - |
| CWO (Aset Lelang) | - |
| DBM Supporting (Aset Lelang) | - |
| Nasabah | - |
| Developer | RU |

1. **Use *Case***

![Use Case Internal - Use Case Login / Autentikasi Internal](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_01_use_case_login_autentikasi_internal.png)

*[Gambar 1.1 – Use Case Login / Autentikasi Internal]*

*![Use Case Internal - Use Case Dashboard / Overview – Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_02_use_case_dashboard_overview_-_aset_lelang.png)*

*[Gambar 1.2 – Use Case Dashboard / Overview – Aset Lelang]*

*![Use Case Internal - Use Case Dashboard / Overview – Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_03_use_case_dashboard_overview_-_aset_baru.png)*

*[Gambar 1.3 – Use Case Dashboard / Overview – Aset Baru]*

*![Use Case Internal - Use Case Customer Management – Leads - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_04_use_case_customer_management_-_leads_-_aset_lelang.png)*

*[Gambar 1.4 – Use Case Customer Management – Leads - Aset Lelang]*

*![Use Case Internal - Use Case Customer Management – Leads - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_05_use_case_customer_management_-_leads_-_aset_baru.png)*

*[Gambar 1.5 – Use Case Customer Management – Leads - Aset Baru]*

***![Use Case Internal - Use Case Customer Management – Ticket - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_06_use_case_customer_management_-_ticket_-_aset_lelang.png)***

*[Gambar 1.6 – Use Case Customer Management – Ticket - Aset Lelang]*

*![Use Case Internal - Use Case Customer Management – Ticket - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_07_use_case_customer_management_-_ticket_-_aset_baru.png)*

*[Gambar 1.7 – Use Case Customer Management – Ticket - Aset Baru]*

*![Use Case Internal - Use Case Stock Management – Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_08_use_case_stock_management_-_aset_lelang.png)*

*[Gambar 1.8 – Use Case Stock Management – Aset Lelang]*

*![Use Case Internal - Use Case Stock Management  – Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_09_use_case_stock_management_-_aset_baru.png)*

*[Gambar 1.9 – Use Case Stock Management – Aset Baru]*

*![Use Case Internal - Use Case Katalog Marketing - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_10_use_case_katalog_marketing_-_aset_lelang.png)*

*[Gambar 1.10 – Use Case Katalog Marketing - Aset Lelang]*

*![Use Case Internal - Use Case Katalog Marketing - Aset Baru ](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_11_use_case_katalog_marketing_-_aset_baru.png)*

*[Gambar 1.11 – Use Case Katalog Marketing - Aset Baru ]*

*![Use Case Internal - Use Case Sold out Aset](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_12_use_case_sold_out_aset.png)*

*[Gambar 1.12 – Use Case Sold out Aset]*

*![Use Case Internal - Use Case Favorit - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_13_use_case_favorit_-_aset_lelang.png)*

*[Gambar 1.13 – Use Case Favorit - Aset Lelang]*

*![Use Case Internal - Use Case Favorit - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_14_use_case_favorit_-_aset_baru.png)*

*[Gambar 1.14 – Use Case Favorit - Aset Baru]*

*![Use Case Internal - Use Case Investor - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_15_use_case_investor_-_aset_lelang.png)*

*[Gambar 1.15 – Use Case Investor - Aset Lelang]*

*![Use Case Internal - Use Case Investor - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_16_use_case_investor_-_aset_baru.png)*

*[Gambar 1.16 – Use Case Investor - Aset Baru]*

*![Use Case Internal - Use Case Approval Aset - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_17_use_case_approval_aset_-_aset_lelang.png)*

*[Gambar 1.17 – Use Case Approval Aset - Aset Lelang]*

*![Use Case Internal - Use Case Approval Aset - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_18_use_case_approval_aset_-_aset_baru.png)*

*[Gambar 1.18 – Use Case Approval Aset - Aset Baru]*

*![Use Case Internal - Use Case Developer - List Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_19_use_case_developer_-_list_developer.png)*

*[Gambar 1.19 – Use Case Developer - List Developer]*

*![Use Case Internal - Use Case Developer - Dashboard Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_20_use_case_developer_-_dashboard_developer.png)*

*[Gambar 1.20 – Use Case Developer - Dashboard Developer]*

*![Use Case Internal - Use Case Developer - Approval Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_21_use_case_developer_-_approval_developer.png)*

*[Gambar 1.21 – Use Case Developer - Approval Developer]*

*![Use Case Internal - Media & Information - FAQ](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_22_media_information_-_faq.png)*

*[Gambar 1.22 – Media & Information - FAQ]*

*![Use Case Internal - Media & Information - Article](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_23_media_information_-_article.png)*

*[Gambar 1.23 – Media & Information - Article]*

*![Use Case Internal - Media & Information - Banner Setting](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_24_media_information_-_banner_setting.png)*

*[Gambar 1.24 – Media & Information - Banner Setting]*

*![Use Case Internal - Use Case User Management – User](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_25_use_case_user_management_-_user.png)*

*[Gambar 1.25 – Use Case User Management – User]*

*![Use Case Internal - Use Case User Management – Role](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_26_use_case_user_management_-_role.png)*

*[Gambar 1.26 – Use Case User Management – Role]*

*![Use Case Internal - Use Case User Management - User External](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_27_use_case_user_management_-_user_external.png)*

*[Gambar 1.27 – Use Case User Management - User External]*

*![Use Case Internal - Use Case User Management - User Block](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_28_use_case_user_management_-_user_block.png)*

*[Gambar 1.28 – Use Case User Management - User Block]*

*![Use Case Internal - Use Case Office Management - Tipe Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_29_use_case_office_management_-_tipe_kantor.png)*

*[Gambar 1.29 – Use Case Office Management - Tipe Kantor]*

*![Use Case Internal - Use Case Office Management - Data Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_30_use_case_office_management_-_data_kantor.png)*

*[Gambar 1.30 – Use Case Office Management - Data Kantor]*

*![Use Case Internal - Use Case Office Management - KPKNL](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_31_use_case_office_management_-_kpknl.png)*

*[Gambar 1.31 – Use Case Office Management - KPKNL]*

***![Use Case Internal - Use Case Audit Trail](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_32_use_case_audit_trail.png)***

*[Gambar 1.32 – Use Case Audit Trail]*

*![Use Case Internal - Use Case Audit Log](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_33_use_case_audit_log.png)*

*[Gambar 1.33 – Use Case Audit Log]*

*![Use Case Internal - Use Case Report - Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_34_use_case_report_-_aset_lelang.png)*

*[Gambar 1.34 – Use Case Report - Aset Lelang]*

*![Use Case Internal - Use Case Report - Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_35_use_case_report_-_aset_baru.png)*

*[Gambar 1.35 – Use Case Report - Aset Baru]*

*![Use Case Internal - Use Case Notifikasi](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_36_use_case_notifikasi.png)*

*[Gambar 1.36 – Use Case Notifikasi]*

*![Use Case Internal - Use Case Beranda (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_37_use_case_beranda_eksternal.png)*

*[Gambar 1.37 – Use Case Beranda (Eksternal)]*

*![Use Case Eksternal - Use Case Aset Lelang (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_01_use_case_aset_lelang_eksternal.png)*

*[Gambar 1.38 – Use Case Aset Lelang (Eksternal)]*

*![Use Case Eksternal - Use Case Aset Baru (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_02_use_case_aset_baru_eksternal.png)*

*[Gambar 1.39 – Use Case Aset Baru (Eksternal)]*

*![Use Case Eksternal - Use Case Jadwal Lelang (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_03_use_case_jadwal_lelang_eksternal.png)*

*[Gambar 1.40 – Use Case Jadwal Lelang (Eksternal)]*

*![Use Case Eksternal - Use Case Simulasi Pembiayaan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_04_use_case_simulasi_pembiayaan_eksternal.png)*

*[Gambar 1.41 – Use Case Simulasi Pembiayaan (Eksternal)]*

*![Use Case Eksternal - Use Case Bandingkan Aset (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_05_use_case_bandingkan_aset_eksternal.png)*

*[Gambar 1.42 – Use Case Bandingkan Aset (Eksternal)]*

*![Use Case Eksternal - Use Case Panduan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_06_use_case_panduan_eksternal.png)*

*[Gambar 1.43 – Use Case Panduan (Eksternal)]*

*![Use Case Eksternal - Use Case Tentang Kami (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_07_use_case_tentang_kami_eksternal.png)*

*[Gambar 1.44 – Use Case Tentang Kami (Eksternal)]*

*![Use Case Eksternal - Use Case FAQ (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_08_use_case_faq_eksternal.png)*

*[Gambar 1.45 – Use Case FAQ (Eksternal)]*

*![Use Case Eksternal - Use Case Article (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_09_use_case_article_eksternal.png)*

*[Gambar 1.46 – Use Case Article (Eksternal)]*

*![Use Case Eksternal - Use Case Profile User - Profile Akun  (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_10_use_case_profile_user_-_profile_akun_eksternal.png)*

*[Gambar 1.47 – Use Case Profile User - Profile Akun (Eksternal)]*

*![Use Case Eksternal - Use Case Profile User - Favorite (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_11_use_case_profile_user_-_favorite_eksternal.png)*

*[Gambar 1.49 – Use Case Profile User - Favorite (Eksternal)]*

*![Use Case Eksternal - Use Case Profile User - Daftar Pesanan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_12_use_case_profile_user_-_daftar_pesanan_eksternal.png)*

*[Gambar 1.50 – Use Case Profile User - Daftar Pesanan (Eksternal)]*

*![Use Case Eksternal - Use Case Profile User - Notifikasi (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_13_use_case_profile_user_-_notifikasi_eksternal.png)*

*[Gambar 1.51 – Use Case Profile User - Notifikasi (Eksternal)]*

*![Use Case Eksternal - Use Case Portal Developer - Aset Kelolaan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_14_use_case_portal_developer_-_aset_kelolaan_eksternal.png)*

*[Gambar 1.52 – Use Case Portal Developer - Aset Kelolaan (Eksternal)]*

*![Use Case Eksternal - Use Case Portal Developer - Form Input Aset (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_15_use_case_portal_developer_-_form_input_aset_eksternal.png)*

*[Gambar 1.53 – Use Case Portal Developer - Form Input Aset (Eksternal)]*

*![Use Case Eksternal - Use Case Portal Developer- List Leads (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_16_use_case_portal_developer-_list_leads_eksternal.png)*

*[Gambar 1.54 – Use Case Portal Developer- List Leads (Eksternal)]*

*![Use Case Eksternal - Use Case Portal Developer - Form Input Leads (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_17_use_case_portal_developer_-_form_input_leads_eksternal.png)*

*[Gambar 1.55 – Use Case Portal Developer - Form Input Leads (Eksternal)]*

*![Use Case Eksternal - Use Case Portal Developer - Dashboard Developer  (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_18_use_case_portal_developer_-_dashboard_developer_eksternal.png)*

*[Gambar 1.55 – Use Case Portal Developer - Dashboard Developer (Eksternal)]*

*![Use Case Eksternal - Use Case Portal Developer - Keamanan (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_19_use_case_portal_developer_-_keamanan_eksternal.png)*

*[Gambar 1.55 – Use Case Portal Developer - Keamanan (Eksternal)]*

*![Use Case Eksternal - Use Case Portal Developer - Akun (Eksternal)](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_usecase_external_20_use_case_portal_developer_-_akun_eksternal.png)*

*[Gambar 1.55 – Use Case Portal Developer - Akun (Eksternal)]*

1. ***Flow Process***

| **No** | **Porses Aplikasi** | **Report yang di hasilkan** |
| --- | --- | --- |
| 1. | Flow Leads 🡪 Ticket (Peminatan) | Peminatan aset dari sisi eksternal (leads) masuk ke sistem, ditindaklanjuti oleh CS, kemudian di-drop ke menu Ticket oleh PIC Aset jika calon pembeli setuju melanjutkan, atau dibatalkan jika tidak. |
| ![Alur Bisnis - Flow 01 Leads To Ticket](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_01_leads_to_ticket.png) | | |
| 2 | ***Flow Staging Ticket – Aset Lelang*** | Staging: New → On Going → Deals → Closing / Cancel. Perpindahan Deals → Closing tidak dapat dilakukan manual dan memerlukan validasi parameter (transaksi terjadi pada nomor debitur, atau nomor debitur terbaca sudah tidak ada kredit). Jika tidak ada perubahan dalam 7 hari, tiket otomatis batal (auto-cancel). Validasi ini hanya berlaku untuk Aset Lelang. |
| ![Alur Bisnis - Flow 02 Staging Ticket Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_02_staging_ticket_aset_lelang.png) | | |
| 3 | *Flow* Staging *Ticket – Aset baru* | Staging "Deals" untuk Aset baru tercapai saat akad telah ditandatangani (bukan saat pengajuan diajukan/disetujui). Tidak terdapat SLA auto-cancel untuk Aset baru — proses cancel dan menuju Closing dilakukan manual dengan proses evidence, bukan validasi otomatis sistem. |
| ![Alur Bisnis - Flow 03 Staging Ticket Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_03_staging_ticket_aset_baru.png) | | |
| 4 | Flow Input Asset Lelang (wizard) | Input aset Lelang mengikuti wizard bertahap: No. Rekening Debitur / Status Aset → Informasi Aset → Pola Penjualan → Dokumen → Lokasi → Fasilitas → Simpan Data Aset (status Draft/Verifikasi menunggu Approval). |
| ![Alur Bisnis - Flow 04A Input Asset Lelang Wizard P1](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_04a_input_asset_lelang_wizard_p1.png)![Alur Bisnis - Flow 04B Input Asset Lelang Wizard P2](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_04b_input_asset_lelang_wizard_p2.png) ![Alur Bisnis - Flow 04C Input Asset Lelang Wizard P3](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_04c_input_asset_lelang_wizard_p3.png) | | |
| 5 | Flow Input Asset Baru | Input aset Baru mengikuti wizard bertahap: Informasi Aset → Informasi Harga Aset→ Galeri Foto→ Legalitas→ Lokasi → Fasilitas → Simpan Data Aset (status Draft/Verifikasi menunggu Approval). |
| ![Alur Bisnis - Flow 05 Input Asset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_05_input_asset_baru.png) | | |
| 6 | Flow Approval Request | Permintaan input aset dan permintaan unpublish aset diajukan melalui 2 pintu, PIC Aset dan Developer, kemudian diproses melalui menu Approval oleh pihak berwenang (Supervisor/Kepatuhan Syariah/Legal sesuai kewenangan) untuk disetujui atau ditolak. |
| ![Alur Bisnis - Flow 06A Approval Request P1](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_06a_approval_request_p1.png)![Alur Bisnis - Flow 06B Approval Request P2](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_06b_approval_request_p2.png) | | |
| 6 | Developer Input Leads |  |
| ![Alur Bisnis - Flow 07 Developer Input Leads](file:///D:/Project/BSN/Fase%201/FSD/assets/04_flow_usecase_external/flow_07_developer_input_leads.png) | | |
| 7 | Flow Publish | Data yang sudah masuk di stock management dapat dipublish dan di unpublish oleh admin pusat.  \* Jika status aset sudah terverifikasi maka baru toggle untuk publish dan unpublish bisa di klik\* |
| ![Alur Bisnis - Flow 08 Publish Unpublish](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_08_publish_unpublish.png) | | |

# Kebutuhan Konfigurasi Sistem

*Bab ini menjelaskan mengenai kebutuhan konfigurasi sistem yang akan dibangun, mulai dari pengelolaan Aplikasi, Database, Infrastruktur, Security, dan Standar Konfigurasi.* ***Mohon untuk hanya menyertakan Integrasi aplikasi (Service, Data, dan Diagram Arsitektur Aplikasi) yang di kembangkan dalam project ini.***

1. **Integrasi Aplikasi**

*Tabel di bawah menjelaskan aplikasi yang terintegrasi dengan aplikasi yang akan dibangun beserta dengan Middleware dan service yang digunakan (surrounding aplikasi). Apabila aplikasi tersebut tidak memiliki Middleware dapat di tulis* ***“direct”. Apabila tidak ada integrasi tidak perlu isi.***

| **No** | **Nama Menu atau Fitur** | **Nama Aplikasi A *(Aplikasi yang Akan Dibangun)*** | **Nama Aplikasi B**  ***(Aplikasi Lain yang Terintegrasi)*** | **Nama Middleware / Interface /Messaging A**  ***(Nama Middleware dari Aplikasi yang Akan Dibangun)*** | **Nama Middleware / Interface /Messaging B**  ***(Nama Middleware dari Aplikasi Lain)*** | **Nama Service A**  ***(Nama Service Milik Aplikasi A)*** | **Nama Service B**  ***(Nama Service yang digunakan Aplikasi B)*** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | *Login* | *BSN Properti* | *LDAP* | *direct* | *direct* | *Autentikasi SSO LDAP* | *Login Auth* |
| 2 | *Inquiry* | *BSN Properti* | *API Core* | *-* | *-* | *Inquiry data nasabah* | *…* |
| 3 | *Simulasi KPR* | *BSN Properti* | *API Simulasi KPR* | *-* | *-* | *Simulasi KPR web BSN Properti* | *…* |
| 4 | *-* | *BSN Properti* | *EDW* | *-* | *-* | *belum diketahui* | *…* |
| 5 | *Email OTP* | *BSN Properti* | *SMTP* | *-* | *-* | *Email OTP* | *…* |
| dst |  | *…* | *…* | *…* | *…* | *…* | *…* |

![Arsitektur Sistem - Arsitektur Aplikasi](file:///D:/Project/BSN/Fase%201/FSD/assets/05_architecture/architecture_01_arsitektur_aplikasi.png)![Arsitektur Sistem - Integrasi Middleware Data](file:///D:/Project/BSN/Fase%201/FSD/assets/05_architecture/architecture_02_integrasi_middleware_data.png)

**Gambar 1.1 Architecture Aplikasi**

1. **Integrasi Data**

| **Nama Aplikasi A**  ***(Nama aplikasi yang dibangun sebagai sudut pandang utama)*** | **Nama Aplikasi B**  ***(Nama aplikasi tujuan)*** | **Data Aplikasi A**  ***(Data dari Aplikasi A ke aplikasi B)*** | **Data Aplikasi B**  ***(Data dari Aplikasi B ke aplikasi A)*** |
| --- | --- | --- | --- |
| BSN Lelang | Core Banking Syariah | Referensi, No. Rekening Pembiayaan | No. Rekening, Nama Debitur, DPD, Kolektibilitas, Outstanding, Jenis Pembiayaan, Kantor Cabang, Status Rekening, Tunggakan Margin, Tunggakan Denda, Total Kewajiban |
| BSN Lelang | LDAP | Username, Password, Apps | Status, Data, Nama, Divisi, Kantor, NIP, Email, userAD |

1. **Teknologi Development**

| **Technology Development** | **Value Properties Technology Development** |
| --- | --- |
| **Platform Technology** | Echo v4 (Backend) & Next JS v14 + Node JS v20 (Frontend) |
| **Bahasa Pemrograman** | Golang v1.27 + JavaScript ES6 |
| **Web Service** | Nginx v1.27 |

# Kebutuhan Pelaporan

1. **Daftar Laporan yang Tersedia pada Sistem aplikasi**

* **Halaman Overview / Dashboard Laporan (Ase Lelang )** : Menampilkan rekapan aktivitas BSN Lelang secara informatif: total VoA, total aset terjual, total peminat, statistik pertumbuhan (growth) transaksi per periode, transaksi terkini, peringkat aset diminati, dan urutan kategori penjualan.
* **Halaman Overview / Dashboard Laporan (Aset Baru)** : Menampilkan rekapan aktivitas BSN Lelang secara informatif: total VoA, total aset terjual, total peminat, statistik pertumbuhan (growth) transaksi per periode, transaksi terkini, peringkat aset diminati, dan urutan kategori penjualan.
* **Halaman Laporan Peminat (Leads) - Aset Lelang** : Memonitoring dan menindaklanjuti peminat (leads) yang mendaftarkan minat pada suatu aset. Dilengkapi mekanisme distribusi peminat otomatis (load balance) ke Sales/CS yangtersedia, serta fitur Edit PIC (khusus role Supervisor).
* **Halaman Laporan Peminat (Leads) - Aset Baru** : Memonitoring dan menindaklanjuti peminat (leads) yang mendaftarkan minat pada suatu aset. Dilengkapi mekanisme distribusi peminat otomatis (load balance) ke Sales/CS yangtersedia, serta fitur Edit PIC (khusus role Supervisor).
* **Halaman Laporan Stock Management - Aset Baru**: Mengelola data aset agunan pembiayaan bermasalah melalui wizard input bertahap, dilengkapi indikator Akurasi Aset (persentase kelengkapan data) dan status Draft/Verifikasi/Publish, dan data aset baru/persediaan (indent/ready stock) di luar mekanisme kredit macet, dengan field Status Aset (Indent/Ready) menggantikan No. Rekening Debitur; tahapan input sama seperti Aset Lelang untuk bagian Informasi Aset, Dokumen, Lokasi, dan Fasilitas.
* **Halaman Laporan Stock Management - Aset Lelang** : Mengelola data aset agunan pembiayaan bermasalah melalui wizard input bertahap, dilengkapi indikator Akurasi Aset (persentase kelengkapan data) dan status Draft/Verifikasi/Publish, dan data aset baru/persediaan (indent/ready stock) di luar mekanisme kredit macet, dengan field Status Aset (Indent/Ready) menggantikan No. Rekening Debitur; tahapan input sama seperti Aset Lelang untuk bagian Informasi Aset, Dokumen, Lokasi, dan Fasilitas.
* **Halaman Laporan Aset Terjual** : Memonitoring seluruh aset yang telah terjual, baik melalui Lelang, Jual Bersama, Cessie, maupun SKM.
* **Halaman Laporan Aset Favorit - Aset Lelang :**: Melihat daftar aset yang paling sering dilihat/difavoritkan oleh calon pembeli atau investor.
* **Halaman Laporan Aset Favorit - Aset Baru:**: Melihat daftar aset yang paling sering dilihat/difavoritkan oleh calon pembeli atau investor.
* **Halaman Laporan Aset Investor Lelang** : Memonitoring dan mengelola data investor yang terdaftar pada BSN Lelang beserta riwayat transaksinya.
* **Halaman Laporan Aset Investor Baru** : Memonitoring dan mengelola data investor yang terdaftar pada BSN Lelang beserta riwayat transaksinya.
* **Halaman Dashboard Developer** : Menyajikan data
* **Halaman Laporan Audit Trail** : Mencatat dan menampilkan seluruh aktivitas yang dilakukan user maupun sistem (termasuk aktivitas melalui API) sebagai jejak audit yang lengkap dan transparan.
* **Halaman Laporan Audit Log** : Mencatat dan menampilkan seluruh aktivitas yang dilakukan user maupun sistem (termasuk aktivitas melalui API) sebagai jejak audit yang lengkap dan transparan.
* **Halaman Laporan Report Aset Baru**
* **Halaman Laporan Report Aset Lelang**

1. **Tampilan Laporan**

*![Laporan - Halaman Overview / Dashboard Laporan](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_01_halaman_overview_dashboard_laporan.png)*

*[Gambar 2.1 – Halaman Overview / Dashboard Laporan]*

*![Laporan - Halaman Laporan Peminat / Leads](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_02_halaman_laporan_peminat_leads.png)*

*[Gambar 2.2 – Halaman Laporan Peminat / Leads]*

![Laporan - Halaman Laporan Inventory Asset](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_03_halaman_laporan_inventory_asset.png)

*[Gambar 2.3 – Halaman Laporan Inventory Asset]*

*![Laporan - Halaman Laporan Aset Terjual](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_04_halaman_laporan_aset_terjual.png)*

*[Gambar 2.4 – Halaman Laporan Aset Terjual]*

![Laporan - Halaman Laporan Aset Favorit](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_05_halaman_laporan_aset_favorit.png)

*[Gambar 2.5 – Halaman Laporan Aset Favorit]*

*![Laporan - Halaman Laporan Investor](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_06_halaman_laporan_investor.png)*

*[Gambar 2.6 – Halaman Laporan Investor]*

![Laporan - Halaman Laporan Audit Trail / Audit Log](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_07_halaman_laporan_audit_trail_audit_log.png)

![Laporan - Halaman Laporan Audit Trail / Audit Log](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_08_halaman_laporan_audit_trail_audit_log.png)

*[Gambar 2.7 – Halaman Laporan Audit Trail / Audit Log]*

# Kebutuhan Keamanan

1. **Identifikasi Profil Risiko dan Kebutuhan Pengujian Keamanan**

| **No** | **Pertanyaan** | **Ya/Tidak** | **Bobot**  **Skor\*** | **Catatan** |
| --- | --- | --- | --- | --- |
| Application-Related Questions *(diisi oleh IT BP/PM)* | |  |  |  |
| 1. | Aplikasi dapat diakses melalui internet (*internet/public facing*)? | ☒Ya  ☐Tidak | 4 | Aplikasi dapat diakses melalui internet utk platform external dan internal |
| 2. | Aplikasi menyimpan/mengolah data pribadi pegawai BSN atau Nasabah? | ☒Ya  ☐Tidak | 1 | ya, informasi yang disimpan sesuai data integrasi LDAP, contohnya NIP, email, nama |
| 3. | Aplikasi merupakan aplikasi transaksional atau terkait dengan proses settlement? | ☐Ya  ☒Tidak | 1 | Aplikasi tidak ada proses settlement dana, murni pencatatan administrasi |
| 4. | Aplikasi merupakan aplikasi yang terkait dengan regulator atau untuk memenuhi kepatuhan regulasi? | ☐Ya  ☒Tidak | 1 |  |
| 5. | Apakah *source code* aplikasi dimiliki/berada di premise BSN? | ☒Ya  ☐Tidak | 1 |  |
| Development/Changes-Related Questions *(diisi oleh IT BP/PM)* | |  |  |  |
| 5. | Terdapat pengembangan/perubahan pada salah satu diantara fitur aplikasi sebagai berikut:   1. Fitur Keamanan (Otentikasi, Otorisasi, Provisioning, 2FA, Token dll) 2. Fitur Transaksional | ☒Ya  ☐Tidak | 1 | a. terdapat semua fitu rkeamanan  b. transaksi hanya bersifat administratif dan tidak terintegrasi dengan core banking utk mutasi data |
| 6. | Terdapat pengembangan/perubahan pada salah satu diantara fitur pemrosesan data dengan klasifikasi *restricted/confidential\** sebagai berikut:   1. Inquiry 2. Create 3. Edit/Update/Modify 4. Delete 5. Upload & Download   \*) Misal: data pribadi nasabah, pegawai, data transaksi, data legalitas nasabah | ☒Ya  ☐Tidak | 1 | a. pemrosesan data restricted hanya Inquiry data nasabah dan rekening |
| 7. | Terdapat pengembangan/perubahan pada salah satu diantara fitur pemrosesan data/informasi yang memerlukan integritas tinggi, yang apabila terdapat manipulasi/perubahan yang tidak sah dapat berisiko tinggi/sifgnifikan terhadap reputasi Bank.  \*) Misal: data laporan keuangan, data laporan tahunan, data kurs, data company profile | ☐Ya  ☒Tidak | 1 | Aplikasi tidak memproses data laporan dengan integritas tinggi |
| **Total Jumlah Skor** | | |  |  |

\*) Skor hanya dihitung apabila pertanyaan terjawab ”Ya”.

**Panduan Scoring:**

| **Total Skor** | **Penetration Test** | **Vulnerability Scan/DAST** | **SAST** |
| --- | --- | --- | --- |
| 0-4 | Opsional | **Mandatory** | **Mandatory, if source code on-premise** |
| >4 | **Mandatory** | Not Required –included in PenTest | **Mandatory, if source code on-premise** |

1. **Analisis Ancaman dan Kontrol Keamanan (*Threat Model*)**

| **No** | **STRIDE** | **Threat Scenario** | **Area** | **Security Requirement/Control** | **Catatan** |
| --- | --- | --- | --- | --- | --- |
| 1 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki fitur autentikasi single-factor sekurang-kurangnya menggunakan UserID and Password | Tersedia, aplikasi mendukung single factor dan two factor authentication |
| 2 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan UserID yang bersifat unik, mudah diidentifikasi, dan merepresentasikan pengguna individu atau kelompok/group pengguna | User memiliki identifier unik disetiap data user |
| 3 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Memiliki/menerapkan konfigurasi password sesuai dengan kebijakan password BSN sebagai berikut:   1. Panjang password minimal 10 karakter 2. Kombinasi alfanumerik dan symbol 3. Masa berlaku password 90 hari 4. Tidak dapat menggunakan 5 password terakhir sebagai password baru 5. Dapat mengidentifikasi dictionary checking untuk mencegah penggunaan kata-kata yang terkait BSN (misal: batara) | Aplikasi mendukung penerapan opsi a, b, c dan e |
| 4 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan fitur pengecekan kebijakan password pada setiap pembuatan password baru (saat registrasi awal, ubah password, maupun saat reset/lupa password) | Aplikasi memiliki validasi disetiap proses autentikasi yang memerlukan kata sandi |
| 5 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Memiliki/menerapkan batas maksimum input password yang salah saat login sebanyak 3 (tiga) kali (maximum failed login attempt) | Aplikasi mendukung rate limit utk maksimum input password jika melebihi maksimal percobaan |
| 6 | Denial of Service | Idle sessions abused to keep resources occupied | User Identification and Authentication | Memiliki/menerapkan timeout/logout secara otomatis\* saat tidak terdapat aktivitas (idle) dengan ketentuan sebagai berikut:   1. Aplikasi internet facing dan mengandung PII, 15 menit 2. Aplikasi internet facing dan tidak mengadung data PII, 60 menit 3. Aplikasi non-internet facing dan mengandung PII, 15 menit 4. Aplikasi non-internet facing dan mengandung PII, 120 menit   \*) waktu paling lama, apabila timeout/logout lebih cepat, maka lebih baik | Aplikasi memiliki idle timeout selama 15 menit utk platform internal dan external |
| 7 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan mekanisme first time login yang aman:   1. Tidak menerapkan default password yang seragam 2. Pengguna harus ubah password saat pertama login | Aplikasi tidak menerapkan default password, setiap pengguna platform external wajib melakukan 2 factor verifikasi email |
| 8 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Fitur ubah password mengharuskan pengguna untuk menginputkan password lamaa | Tidak wajib, tetapi wajib melakukan autentikasi 2 factor |
| 9 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan logout otomatis dan secara paksa setelah Pengguna berhasil sukses ubah password | Aplikasi mendukung |
| 10 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan fitur lupa/reset passsword yang menggunakan mekanisme media di luar aplikasi (misalnya melalui email, SMS, dan lainnya) | mendukung |
| 11 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Dalam hal fitur lupa/reset passsword menggunakan link/URL, kode unik, atau token, telah dilengkapi dengan fitur kadaluwarsa dan sekali pakai (single-use) | mendukung |
| 12 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Memiliki/menerapkan Multi Factor Authentication (MFA) sekurang-kurangnya 2 (dua) faktor autentikasi pada saat login atau akses ke fitur-fitur sensitif (misalnya fitur transaksional, fitur akses/ubah data sensitif) | Mandatory untuk semua aplikasi internet facing, atau non-internet facing yang kritikal |
| 13 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Apabila menggunakan/menerapkan Multi Factor Authentication (MFA) dengan OTP, terdapat fitur maksimal jumlah input gagal OTP | Mandatory untuk semua aplikasi internet facing, atau non-internet facing yang kritikal |
| 14 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Apabila menggunakan/menerapkan Multi Factor Authentication (MFA) dengan OTP, terdapat fitur kadaluwarsa pada kode OTP. | Mandatory untuk semua aplikasi internet facing, atau non-internet facing yang kritikal |
| 15 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Apabila menggunakan/menerapkan Multi Factor Authentication (MFA) dengan OTP, kode OTP harus bersifat single-use atau hanya dapat digunakan 1 (satu) kali | Mandatory untuk semua aplikasi internet facing, atau non-internet facing yang kritikal |
| 16 | Spoofing | Attacker impersonates a service or machine account | Machine Identification and Authentication | Memiliki/menerapkan fitur autentikasi menggunakan password atau certificate | menggunakan password |
| 17 | Spoofing | Attacker impersonates a service or machine account | Machine Identification and Authentication | Memiliki/menerapkan UserID machine/service yang bersifat unik, mudah diidentifikasi, dan representatif | mendukung |
| 18 | Elevation of Privilege | Exploiting shared or weak service accounts | Machine Identification and Authentication | Memiliki/menerapkan konfigurasi password sesuai dengan kebijakan password BSN (panjang dan kompeksitas) | Mendukung |
| 19 | Elevation of Privilege | Regular user escalates to admin | Machine Identification and Authentication | Akun machine/service memiliki akses yang terbatas (least privileges) sesuai kebutuhan dan tidak memiliki hak akses Administrator/SuperUser | mendukung apabila server melakukan konfigurasi privilege |
| 20 | Elevation of Privilege | Service accounts misused for interactive access | Machine Identification and Authentication | Akun machine/service memiliki akses non-interaktif. Tidak dapat digunakan untuk akses manusia melalui remote-interactive protocol seperti RDP dan SSH. | mengikuti kebijakan dari tim infrastruktur & security BSN |
| 21 | Spoofing | Replay or stolen credential use | Machine Identification and Authentication | Informasi credentials yang digunakan untuk autentikasi mesin/service disimpan secara terproteksi dan tidak secara ditulis secara cleartext (misalnya menggunakan file konfigurasi dan dienkripsi, tidak di-hardcode pada source code) | mengikuti kebijakan dari tim infrastruktur & security BSN |
| 22 | Spoofing | Attacker impersonates a service or machine account | Machine Identification and Authentication | 1 (satu) akun machine/service, hanya digunakan untuk mengautentikasi 1 (satu) machine/service (one-to-one) dan tidak digunakan oleh beberapa machine/service secara bersamaan. | mengikuti kebijakan dari tim infrastruktur & security BSN |
| 23 | Elevation of Privilege | Regular user escalates to admin | Roles and authorization management | Memiliki role dengan hak akses berjenjang dan terbatas sesuai kebutuhan dan prinsip least privilege/need-to-know basis | mendukung RBAC |
| 24 | Elevation of Privilege | Misuse of dormant/inactive accounts | Roles and authorization management | Memiliki fitur disable/deaktivasi otomatis apabila Pengguna tidak pernah login selama periode waktu tertentu | belum didukung |
| 25 | Elevation of Privilege | Privilege chaining via stolen tokens | Session Management | Session token baru di-generate oleh sistem pada saat setiap autentikasi pengguna yang berhasil untuk memitigasi pencurian session token dan penggunaan kembali session token (reuse) secara tidak sah | mendukung |
| 26 | Spoofing | Session hijacking / reuse of tokens | Session Management | Session token pengguna di-destroy setiap kali logout dilakukan | mendukung |
| 27 | Spoofing | Session hijacking / reuse of tokens | Session Management | Terdapat pembatasan login/session yang bersamaan dalam waktu waktu (concurrent session) | bisa dikonfigurasi utk one time login device |
| 28 | Repudiation | User denies an action (e.g., password reset, transaction) | Audit and Logging | Menerapkan/memiliki fitur audit trail/logging yang mencatat aktivitas terkait dengan keamanan, seperti login sukses dan gagal, serta ubah password | Mendukung |
| 29 | Repudiation | User denies an action (e.g., password reset, transaction) | Audit and Logging | Menerapkan/memiliki fitur audit trail/logging yang mencatat informasi yang dibutuhkan untuk memudahkan investigasi/troubleshoot diantaranya timestamp, UserID, menu yang diakses dan aktivitas yang dilakukan | Mendukung |
| 30 | Repudiation | Lack of forensic traceability | Audit and Logging | Menerapkan/memiliki fitur audit trail/logging yang menggunakan konfigurasi waktu (timestamp) yang disinkronisasikan dengan zona waktu yang sesuai | Mendukung |
| 31 | Information Disclosure | Data exposed in storage | Data at-rest Encryption | Password harus disimpan secara terproteksi menggunakan one-way-function (hashing) atau dengan enkripsi dengan algoritma yang kuat dan tidak obsolete | menggunakan argon2 dan bcrypt |
| 32 | Information Disclosure | Data exposed in storage | Data at-rest Encryption | Memiliki/menerapkan enkripsi pada database | mendukung utk data sensitif seperti password |
| 33 | Tampering | Data modified in transit (MITM, parameter tampering) | Data-in-Transit Encryption | Menggunakan protokol TLS 1.2 atau TLS 1.3 dengan cipher suite yang aman dan tidak obsolete. | mengikuti kebijakan dari tim security BSN |
| 34 | Information Disclosure | Data leaked in transit | Data-in-Transit Encryption | Menggunakan SSL certificate yang dikeluarkan oleh Public Certificate Authority (CA) yang well-known dan aman, serta bukan merupakan self-signed certificate. | Mandatory untuk semua aplikasi internet facing, atau non-internet facing yang kritikalv |
| 35 | Information Disclosure | Sensitive data exposed in logs or errors | Error Handling | Menerapkan pesan error yang tidak mengungkapkan informasi sensitif, tidak mengandung detail teknis yang dapat memperlihatkan struktur sistem atau kode internal. | mendukung |
| … |  |  |  |  |  |
| … |  |  |  | ![Separator End](file:///D:/Project/BSN/Fase%201/FSD/assets/00_common/common_separator_end.png) |  |

# Lampiran

1. **Data Pendukung (Optional)**

*Cantumkan setiap data yang diacu pada saat penyusunan Functional Specification Document seperti:*

* *Dokumen IR/ Change Request (CR).*
* *Dan Sebagainya.*

| **Disusun Oleh:**  **PT Zegen Solusi Mandiri** | | |
| --- | --- | --- |
| Tanggal: | | Tanggal: |
| **Business Relationship Manager**  ( ) | **Business Relationship Manager**  ( ) | **Project Manager**  (Mochammad Henry Daudi) |

| **Diverifikasi Oleh:**  **[NAMA DIVISI]** | **Diverifikasi Oleh:**  **[NAMA DIVISI OWNER]** | |
| --- | --- | --- |
| Tanggal: | Tanggal: | |
| **Business Relationship Manager**  (Sandra Putri) | **Business User**  *`*  (Abdul Kholiq Al Bari) | **Business User**  (Usein Akbar) |

| **Diketahui Oleh:**  **PT. BANK SYARIAH NASIONAL** | | | |
| --- | --- | --- | --- |
| Tanggal: | Tanggal: | | Tanggal: |
| **Application Architecture**  ( ) | **Project Manager**  (Muhammad Fadhil Mubaraq) | | **Apps & Data Protection**  ( ) |
| Tanggal: | | Tanggal: | |
| **EA & Innovation Department Head**  ( ) | | **Apps & Data Protection Department Head**  ( ) | |
|  | | | |
| *Note: Apabila ada catatan / dispensasi* | | | |
|  | | | |