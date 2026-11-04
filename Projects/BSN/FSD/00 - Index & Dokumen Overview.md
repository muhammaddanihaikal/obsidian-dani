---
title: FSD BSN Lelang - 00 Index & Dokumen Overview
project: BSN Lelang
source: BSN Template - FSD.docx
version: 1.0
vendor: PT Zegen Solusi Mandiri
client: PT Bank Syariah Nasional
tags:
  - fsd
  - bsn
  - overview
  - scope
  - release
---

# 📑 00 - Index & Ringkasan Dokumen FSD BSN Lelang

> [!NOTE] Informasi Dokumen FSD
> Dokumen Spesifikasi Fungsional (Functional Specification Document) ini mendefinisikan seluruh kebutuhan bisnis, fungsi aplikasi, alur kerja (workflow), hak akses role, integrasi sistem, dan standar keamanan untuk platform **BSN Lelang** (Bank Syariah Nasional).

---

## 📌 Indeks Modul Dokumentasi

| No | Modul | Deskripsi | Link |
|---|---|---|---|
| **00** | **Index & Dokumen Overview** | Informasi proyek, histori versi, daftar istilah & ruang lingkup rilis | *Dokumen Ini* |
| **01** | **Alur & Flowchart Fitur Internal** | Seluruh alur kerja backoffice: Staging Ticket, Input Aset, Approval, Publish & Use Case | [[FSD/01 - Alur & Flowchart Fitur Internal\|Buka Modul 01]] |
| **02** | **Alur & Flowchart Fitur Eksternal & Developer** | Alur nasabah (Peminatan, KPR, Simulasi) & Portal Developer (Registrasi, Submit Aset, Leads) | [[FSD/02 - Alur & Flowchart Fitur Eksternal & Developer\|Buka Modul 02]] |
| **03** | **Matriks Fitur & Hak Akses Role (CRUD)** | Matriks 505 hak akses Create, Read, Update, Delete untuk setiap role pengguna | [[FSD/03 - Matriks Fitur & Hak Akses Role (CRUD)\|Buka Modul 03]] |
| **04** | **Arsitektur Sistem & Integrasi Middleware** | Diagram arsitektur sistem, middleware, API service, dan interfacing bank | [[FSD/04 - Arsitektur Sistem & Integrasi Middleware\|Buka Modul 04]] |
| **05** | **Modul Pelaporan & Keamanan (STRIDE)** | Spesifikasi 8 jenis laporan analitik dan matriks keamanan ancaman STRIDE | [[FSD/05 - Modul Pelaporan & Keamanan (STRIDE)\|Buka Modul 05]] |
| 📖 | **Master FSD (Lengkap)** | Seluruh dokumen asli FSD dalam satu file utuh dengan 145 gambar | [[FSD - BSN Lelang\|Buka Master FSD]] |

---

## 🏢 Informasi Proyek & Stakeholder

| NAMA VENDOR | : | PT Zegen Solusi Mandiri | PT Zegen Solusi Mandiri |
| --- | --- | --- | --- |
| DIVISI OWNER | : | DBG – Usein Akbar, Abdul Khaloq Al Bari | DBG – Usein Akbar, Abdul Khaloq Al Bari |
| DIVISI USER | : | CAM -- DBG | CAM -- DBG |
| SYSTEM ANALYST | : | Muhammad Rayhan Subhi | Muhammad Rayhan Subhi |
| JENIS PENGEMBANGAN | : | √ Aplikasi Baru | □ Perubahan/Penambahan Struktur Data |
| JENIS PENGEMBANGAN |  | □ Penambahan/Perubahan Fitur | □ Perubahan / Migrasi Infrastruktur Aplikasi |
| JENIS PENGEMBANGAN |  | □ Perubahan/Migrasi License |  |


### Histori Perubahan Dokumen
| No | Versi | Tanggal | Alasan Perubahan | Penulis |
| --- | --- | --- | --- | --- |
| 1 | 1.0 | 24 September |  | Carol R |
| 2 |  | 5 oktober |  |  |
| 3 |  | 12 Oktober |  |  |
| 4 |  | 26 Oktober |  |  |
| 5 |  |  |  |  |


---

## 📚 Daftar Istilah (Glossary)

| Properties | Value Properties |
| --- | --- |
| Nama Aplikasi | BSN Lelang |
| Kode Nama Aplikasi * | Kode dan nama aplikasi (Kode Nama Aplikasi) |
| Deskripsi | BSN Lelang adalah aplikasi berbasis web untuk menampilkan portofolio/agunan yang siap dijual maupun dilelang, mencakup 2 kategori utama aset: (1) Aset Lelang — aset agunan pembiayaan bermasalah yang dijual melalui mekanisme Lelang, Jual Bersama, Cessie, atau SKM; dan (2) Aset baru — aset baru/persediaan yang dipasarkan di luar mekanisme penyelesaian kredit macet. Tujuan aplikasi: mempercepat proses penjualan aset, menjangkau pasar lebih luas, meningkatkan transparansi transaksi, serta mendukung kepatuhan terhadap prinsip syariah dalam setiap mekanisme penjualan. |
| Jenis Aplikasi | Application |
| PSE Lingkup Privat * | NO |
| Data Retention | Setelah 5 tahun |
| Platform | Web App |
| Development Type | In House |
| Vendor Name | Zegen Solusi Mandiri |
| License Scheme | Perpetual |
| Deployment | PaaS |
| System Owner * | DBG |
| Source Code | YES |
| Application URL |  |
| Implemented Year * | * |
| Log In Auth | AD/Non-AD/ User Auth |
| Kepemilikan | Beli Putus |
| PT & KK | Di isi oleh BP/ user owner |


---

## 🚀 Ruang Lingkup Rilis Fitur (Release Scope)

Tabel berikut mendefinisikan pembagian rilis fitur pada platform BSN Lelang (Release 1, 2, dan 3):

| Fitur | Release 1 | Release 2 | Release 3 |
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


---

## 📋 Daftar Menu & Fungsi Aplikasi

| No | Nama Menu/Fungsi Aplikasi | Nama Fitur per Fungsi Aplikasi | Nama Sub-Fitur Aplikasi | Deskripsi Menu/Fitur/Sub-Fitur |
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

