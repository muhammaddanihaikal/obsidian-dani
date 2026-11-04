---
title: FSD BSN Lelang - 05 Modul Pelaporan & Keamanan (STRIDE)
project: BSN Lelang
tags:
  - fsd
  - bsn
  - report
  - analytics
  - security
  - stride
---

# 📊 05 - Modul Pelaporan & Keamanan (STRIDE)

> [!NOTE] Pelaporan & Kepatuhan Keamanan
> Dokumen ini mendefinisikan format pelaporan manajemen dan hasil analisis model ancaman keamanan (**STRIDE Threat Model**).

---

## 📈 1. Modul Pelaporan (Reporting)

Sistem menyediakan 8 modul pelaporan utama dengan visualisasi dashboard grafikal dan tabel ekspor:

### 1.1 Overview / Dashboard Laporan
Ringkasan performa penjualan, total aset terjual, dan status tiket secara real-time.
![Dashboard Overview Laporan](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_01_halaman_overview_dashboard_laporan.png)

---

### 1.2 Laporan Peminat / Leads
Rekap seluruh nasabah yang menyatakan minat pada aset lelang maupun aset baru.
![Laporan Peminat Leads](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_02_halaman_laporan_peminat_leads.png)

---

### 1.3 Laporan Inventory Asset
Laporan ketersediaan stok aset, nilai taksasi, dan status verifikasi legalitas.
![Laporan Inventory Asset](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_03_halaman_laporan_inventory_asset.png)

---

### 1.4 Laporan Aset Terjual
Rekapitulasi aset yang telah laku terjual, nilai realisasi lelang, dan data pemenang.
![Laporan Aset Terjual](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_04_halaman_laporan_aset_terjual.png)

---

### 1.5 Laporan Aset Favorit
Analisis tren properti yang paling banyak disimpan/difavoritkan oleh calon pembeli.
![Laporan Aset Favorit](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_05_halaman_laporan_aset_favorit.png)

---

### 1.6 Laporan Investor
Daftar profil investor aktif yang berminat membeli aset properti secara borongan (*bulk*).
![Laporan Investor](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_06_halaman_laporan_investor.png)

---

### 1.7 Laporan Audit Trail & Audit Log
Pencatatan riwayat setiap aksi pengguna sistem untuk audit forensik dan kepatuhan perbankan.
- **Audit Trail**: ![Laporan Audit Trail](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_07_halaman_laporan_audit_trail_audit_log.png)
- **Audit Log**: ![Laporan Audit Log](file:///D:/Project/BSN/Fase%201/FSD/assets/06_reports/report_08_halaman_laporan_audit_trail_audit_log.png)

---

## 🛡️ 2. Kebutuhan Keamanan & Pengujian

### 2.1 Kuesioner Kesiapan Keamanan
| No | Pertanyaan | Ya/Tidak | Bobot Skor* | Catatan |
| --- | --- | --- | --- | --- |
| Application-Related Questions (diisi oleh IT BP/PM) | Application-Related Questions (diisi oleh IT BP/PM) |  |  |  |
| 1. | Aplikasi dapat diakses melalui internet (internet/public facing)? | ☒Ya ☐Tidak | 4 | Aplikasi dapat diakses melalui internet utk platform external dan internal |
| 2. | Aplikasi menyimpan/mengolah data pribadi pegawai BSN atau Nasabah? | ☒Ya ☐Tidak | 1 | ya, informasi yang disimpan sesuai data integrasi LDAP, contohnya NIP, email, nama |
| 3. | Aplikasi merupakan aplikasi transaksional atau terkait dengan proses settlement? | ☐Ya ☒Tidak | 1 | Aplikasi tidak ada proses settlement dana, murni pencatatan administrasi |
| 4. | Aplikasi merupakan aplikasi yang terkait dengan regulator atau untuk memenuhi kepatuhan regulasi? | ☐Ya ☒Tidak | 1 |  |
| 5. | Apakah source code aplikasi dimiliki/berada di premise BSN? | ☒Ya ☐Tidak | 1 |  |
| Development/Changes-Related Questions (diisi oleh IT BP/PM) | Development/Changes-Related Questions (diisi oleh IT BP/PM) |  |  |  |
| 5. | Terdapat pengembangan/perubahan pada salah satu diantara fitur aplikasi sebagai berikut: Fitur Keamanan (Otentikasi, Otorisasi, Provisioning, 2FA, Token dll) Fitur Transaksional | ☒Ya ☐Tidak | 1 | a. terdapat semua fitu rkeamanan b. transaksi hanya bersifat administratif dan tidak terintegrasi dengan core banking utk mutasi data |
| 6. | Terdapat pengembangan/perubahan pada salah satu diantara fitur pemrosesan data dengan klasifikasi restricted/confidential* sebagai berikut: Inquiry Create Edit/Update/Modify Delete Upload & Download  *) Misal: data pribadi nasabah, pegawai, data transaksi, data legalitas nasabah | ☒Ya ☐Tidak | 1 | a. pemrosesan data restricted hanya Inquiry data nasabah dan rekening |
| 7. | Terdapat pengembangan/perubahan pada salah satu diantara fitur pemrosesan data/informasi yang memerlukan integritas tinggi, yang apabila terdapat manipulasi/perubahan yang tidak sah dapat berisiko tinggi/sifgnifikan terhadap reputasi Bank.  *) Misal: data laporan keuangan, data laporan tahunan, data kurs, data company profile | ☐Ya ☒Tidak | 1 | Aplikasi tidak memproses data laporan dengan integritas tinggi |
| Total Jumlah Skor | Total Jumlah Skor | Total Jumlah Skor |  |  |


### 2.2 Skor Hasil Pengujian Keamanan (Penetration Test, SAST, DAST)
| Total Skor | Penetration Test | Vulnerability Scan/DAST | SAST |
| --- | --- | --- | --- |
| 0-4 | Opsional | Mandatory | Mandatory, if source code on-premise |
| >4 | Mandatory | Not Required –included in PenTest | Mandatory, if source code on-premise |


---

## 🚨 3. Analisis Ancaman Keamanan (STRIDE Threat Model)

Model ancaman mencakup:
- **S**poofing (Pemalsuan Identitas)
- **T**ampering (Manipulasi Data)
- **R**epudiation (Penyangkalan Aksi)
- **I**nformation Disclosure (Kebocoran Data Pribadi)
- **D**enial of Service (Gangguan Ketersediaan Layanan)
- **E**levation of Privilege (Penyalahgunaan Wewenang)

| No | STRIDE | Threat Scenario | Area | Security Requirement/Control | Catatan |
| --- | --- | --- | --- | --- | --- |
| 1 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki fitur autentikasi single-factor sekurang-kurangnya menggunakan UserID and Password | Tersedia, aplikasi mendukung single factor dan two factor authentication |
| 2 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan UserID yang bersifat unik, mudah diidentifikasi, dan merepresentasikan pengguna individu atau kelompok/group pengguna | User memiliki identifier unik disetiap data user |
| 3 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Memiliki/menerapkan konfigurasi password sesuai dengan kebijakan password BSN sebagai berikut: Panjang password minimal 10 karakter Kombinasi alfanumerik dan symbol Masa berlaku password 90 hari Tidak dapat menggunakan 5 password terakhir sebagai password baru Dapat mengidentifikasi dictionary checking untuk mencegah penggunaan kata-kata yang terkait BSN (misal: batara) | Aplikasi mendukung penerapan opsi a, b, c dan e |
| 4 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan fitur pengecekan kebijakan password pada setiap pembuatan password baru (saat registrasi awal, ubah password, maupun saat reset/lupa password) | Aplikasi memiliki validasi disetiap proses autentikasi yang memerlukan kata sandi |
| 5 | Spoofing | Brute force or credential stuffing attacks | User Identification and Authentication | Memiliki/menerapkan batas maksimum input password yang salah saat login sebanyak 3 (tiga) kali (maximum failed login attempt) | Aplikasi mendukung rate limit utk maksimum input password jika melebihi maksimal percobaan |
| 6 | Denial of Service | Idle sessions abused to keep resources occupied | User Identification and Authentication | Memiliki/menerapkan timeout/logout secara otomatis* saat tidak terdapat aktivitas (idle) dengan ketentuan sebagai berikut: Aplikasi internet facing dan mengandung PII, 15 menit Aplikasi internet facing dan tidak mengadung data PII, 60 menit Aplikasi non-internet facing dan mengandung PII, 15 menit Aplikasi non-internet facing dan mengandung PII, 120 menit *) waktu paling lama, apabila timeout/logout lebih cepat, maka lebih baik | Aplikasi memiliki idle timeout selama 15 menit utk platform internal dan external |
| 7 | Spoofing | Attacker impersonates a user with stolen credentials | User Identification and Authentication | Memiliki/menerapkan mekanisme first time login yang aman: Tidak menerapkan default password yang seragam Pengguna harus ubah password saat pertama login | Aplikasi tidak menerapkan default password, setiap pengguna platform external wajib melakukan 2 factor verifikasi email |
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
| … |  |  |  |  |  |

