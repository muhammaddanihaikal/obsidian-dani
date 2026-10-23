# Audit Match: SIT vs Hasil Uji (UAT)

Tanggal audit: 15 Oktober 2026

Sumber:
- SIT Web: `SIT_BTN_SMART_Web.docx` (867 TC, 79 modul)
- UAT Web: `Dokumen_Hasil_Uji_Web_4.docx` (800 TC, 79 modul)
- SIT Mobile: `SIT_BTN_SMART_Mobile.docx` (260 TC, 20 modul)
- UAT Mobile: `Dokumen_Hasil_Uji_Mobile_1.docx` (260 TC, 20 modul)

Cara cocok: modul dicocokkan berdasarkan **nama modul** (bukan nomor, karena nomor modul 41–56 berbeda urutannya). TC dicocokkan berdasarkan judul TC yang sudah dinormalisasi (huruf kecil, spasi dirapikan). Judul yang beda kata tapi hampir sama dicatat terpisah.

## Ringkasan

| Dokumen | Total TC SIT | Total TC UAT | Hasil |
|---|---|---|---|
| Mobile | 260 | 260 | MATCH 100%, nama modul, jumlah TC, dan judul TC sama |
| Web | 867 | 800 | BELUM MATCH, selisih 67 TC |

## Mobile

Tidak ada perbedaan. Semua 20 modul dan 260 TC cocok.

## Web

### 1. Perbedaan nomor modul (modul 41–56)

Nomor modul di SIT dan UAT tidak sama untuk modul-modul berikut. Nama modulnya sama, tapi urutannya beda. Ini bukan error isi, tapi nomor TC di modul ini tidak bisa dibandingkan langsung.

| Nama modul | No. SIT | No. UAT |
|---|---|---|
| Sales Force - Approval Sales Code | 41 | 44 |
| Sales Force - CIF Kelolaan | 42 | 45 |
| Sales Force - Approval Cif Kelolaan | 43 | 46 |
| Sales Force - Produktivitas - Target Growth | 44 | 47 |
| Sales Force - Approval Target Growth | 45 | 43 |
| Sales Force - Produktivitas - Target Produktivitas | 46 | 48 |
| Sales Force - Produktivitas - Bobot Produktivitas | 47 | 49 |
| Sales Force - Produktivitas - Realisasi Merchant | 48 | 50 |
| Sales Force - CIF Rebase | 49 | 51 |
| Sales Force - Report - Report Produktivitas | 50 | 52 |
| Sales Force - Dashboard Sales Force | 51 | 53 |
| Sales Force - Pipeline - Setting Role Validate Pipeline | 52 | 54 |
| Sales Force - Pipeline - Setting Validate Pipeline | 53 | 55 |
| Sales Force - Pipeline - Input komitmen | 54 | 56 |
| Sales Force - Pipeline - Input Pipeline | 55 | 42 |
| Sales Force - Pipeline - Dashboard Validate Pipeline | 56 | 41 |

### 2. Jumlah TC per modul yang beda

| Nama modul | SIT | UAT |
|---|---|---|
| Sales Force - Approval Sales Code | 23 | 8 |
| Sales Force - CIF Kelolaan | 10 | 16 |
| Sales Force - Approval Cif Kelolaan | 8 | 7 |
| Sales Force - CIF Rebase | 9 | 7 |
| Sales Force - Report - Report Produktivitas | 33 | 2 |
| Sales Force - Dashboard Sales Force | 31 | 3 |
| Sales Force - Pipeline - Setting Role Validate Pipeline | 2 | 9 |
| Sales Force - Pipeline - Input Pipeline | 11 | 10 |
| Sales Force - Pipeline - Dashboard Validate Pipeline | 25 | 23 |

### 3. TC yang hanya ada di SIT (tidak ada di UAT)

Ini TC yang ada di SIT tapi tidak punya padanan di UAT. Perlu dicek: apakah TC ini sengaja tidak diuji di UAT, atau UAT-nya belum dibuat.


**Login**

- SIT 1.2: Melakukan login dengan email dan password valid

**Lead Qualification - Aktifitas Referal**

- SIT 27.8: Mencari data tab Prospek yang direferalkan ke saya dengan keyword tidak valid

**Sales Tracking Activity - Client Visit List**

- SIT 34.2: Menampilkan daftar data Client Visit List

**Sales Tracking Activity - Rekap Visit**

- SIT 35.2: Menampilkan daftar data Rekap Visit

**Sales Force - Approval Sales Code**

- SIT 41.9: Membuka detail
- SIT 41.10: Membuka detail Chart Sales Input Pipeline
- SIT 41.11: Mencari data pada kolom pencarian
- SIT 41.12: Membuka detail
- SIT 41.13: Membuka detail Chart Pipeline Category
- SIT 41.14: Mencari data pada kolom pencarian
- SIT 41.15: Membuka detail
- SIT 41.16: List validate Pipeline - mencari data pada kolom pencarian
- SIT 41.17: Membuka detail list validate pipeline
- SIT 41.18: Detail Validate Pipeline - Melakukan Filter data
- SIT 41.19: Detail Validate pipeline - mengunduh data validate pipeline
- SIT 41.20: Melakukan Validate data menggunakan user BM
- SIT 41.21: Melakukan validate all data menggunakan user BM
- SIT 41.22: Melakukan unvalidate data menggunakan user BM
- SIT 41.23: Melakukan Validate data menggunakan user RO Head

**Sales Force - Approval Cif Kelolaan**

- SIT 43.5: Membuka tab status ( pending request/approved/Rejected/expired)

**Sales Force - Approval Target Growth**

- SIT 45.1: Membuka menu Approval Target Growth
- SIT 45.2: Melakukan filter data
- SIT 45.7: Mencari data pada kolom pencarian
- SIT 45.8: Mencari data kata kunci yang tidak sesuai

**Sales Force - CIF Rebase**

- SIT 49.7: Melakukan Unarchive cif
- SIT 49.9: Mencari data pada kolom pencarian

**Sales Force - Report - Report Produktivitas**

- SIT 50.1: Mencari data kata kunci yang tidak sesuai
- SIT 50.3: Melakukan filter data
- SIT 50.5: Mengunduh data resume
- SIT 50.6: Tab sforce
- SIT 50.7: mengunduh data sforce
- SIT 50.8: Tab Calculate
- SIT 50.9: Mengungunduh data calculate
- SIT 50.10: Tab Realisasi
- SIT 50.11: Mengunduh data realisasi
- SIT 50.12: Tab Target
- SIT 50.13: Mengunduh data Target
- SIT 50.14: Tab Target DPK
- SIT 50.15: Mengunduh data terget DPK
- SIT 50.16: Tab DPK port
- SIT 50.17: Mengunduh data Target DPK port
- SIT 50.18: Tab konek Echannel
- SIT 50.19: Mengunduh data konek echannel
- SIT 50.20: Tab All CIF
- SIT 50.21: Mengunduh data all cif
- SIT 50.22: Tab SegMove
- SIT 50.23: Mengunduh data Segmove
- SIT 50.24: Tab Visit
- SIT 50.25: Mengunduh data Visit
- SIT 50.26: Tab Merchant
- SIT 50.27: Mengunduh data Merchant
- SIT 50.28: Tab Tier
- SIT 50.29: Mengunduh data Tier
- SIT 50.30: Tab Referal
- SIT 50.31: Mengunduh data Referal
- SIT 50.32: Tab Presensi
- SIT 50.33: Mengunduh data Presensi

**Sales Force - Dashboard Sales Force**

- SIT 51.3: Melakukan filter data
- SIT 51.5: Filter data Voa Realization
- SIT 51.6: Mencari data Voa realizaion Pada kolom pencarian
- SIT 51.7: Melihat detail Voa Realization
- SIT 51.8: Melihat detail card Cif Kelolaan
- SIT 51.9: Filter data Cif Kelolaan
- SIT 51.10: mencari data Cif Kelolaan pada kolom pencarian
- SIT 51.11: Melihat detail Cif Kelolaan
- SIT 51.12: Melihat detail card skor Produktivitas
- SIT 51.13: Filter data produktivitas
- SIT 51.14: Melihat detail skor Produktivitas
- SIT 51.15: Melihat detail data card konek echannel
- SIT 51.16: Filter data konek echannel
- SIT 51.17: Mencari data konek echannel pada kolom pencarian
- SIT 51.18: Melihat detail data konek echannel
- SIT 51.19: Melihat detail data card realisasi visit
- SIT 51.20: Melihat detail data card realisasi akuisisi merchat
- SIT 51.21: Filter data realisasi akuisisi merchant
- SIT 51.22: Mencari data realisasi akuisis merchant pada kolom pencarian
- SIT 51.23: Melihat detail data realisasi merchant
- SIT 51.24: Melihat detial data card Eligible Upgrade to Prospera / Prioritas
- SIT 51.25: Filter data Eligible Upgrade to Prospera / Prioritas
- SIT 51.26: Mencari data Eligible Upgrade to Prospera Prioritas pada kolom pencarian
- SIT 51.27: Melihat detail data Eligible Upgrade to Prospera / Prioritas
- SIT 51.28: Melihat detail data card Referral to Prospera / Prioritas
- SIT 51.29: Filter data Referral to Prospera / Prioritas
- SIT 51.30: Mencari data Referral to Prospera / Prioritas pada kolom pencarian
- SIT 51.31: Melihat detail data Referral to Prospera / Prioritas

**Sales Force - Pipeline - Input Pipeline**

- SIT 55.3: Melakukan filter data dengan tidak menginput filter mandatory (Negative test)

**Sales Force - Pipeline - Dashboard Validate Pipeline**

- SIT 56.1: Membukan menu dashboard validate pipeline
- SIT 56.4: Membuka detail Chart total pipeline DPK
- SIT 56.6: Membuka detail
- SIT 56.7: Membuka detail Chart pipeline data kantor cabang
- SIT 56.9: Membuka detail
- SIT 56.10: Membuka detail Chart Sales Input Pipeline
- SIT 56.12: Membuka detail
- SIT 56.13: Membuka detail Chart Pipeline Category
- SIT 56.15: Membuka detail
- SIT 56.16: List validate Pipeline - mencari data pada kolom pencarian
- SIT 56.17: Membuka detail list validate pipeline
- SIT 56.18: Detail Validate Pipeline - Melakukan Filter data
- SIT 56.19: Detail Validate pipeline - mengunduh data validate pipeline
- SIT 56.20: Melakukan Validate data menggunakan user BM
- SIT 56.21: Melakukan validate all data menggunakan user BM
- SIT 56.22: Melakukan unvalidate data menggunakan user BM
- SIT 56.23: Melakukan Validate data menggunakan user RO Head
- SIT 56.24: Melakukan validate all data menggunakan user RO Head
- SIT 56.25: Melakukan unvalidate data menggunakan user RO Head

**Report Funding - Rekap Funnel**

- SIT 59.2: Menampilkan data Rekap Funnel

**Report Funding - Pengaturan Funnel**

- SIT 60.2: Menampilkan data Pengaturan Funnel Funding berdasarkan section
- SIT 60.5: Menambahkan Condition pada Performance Indicator
- SIT 60.6: Menambahkan Condition pada Performance Indicator tanpa mengisi field mandatory
- SIT 60.7: Menghapus Condition pada Performance Indicator

**Report Lending - Personal Funnel**

- SIT 62.4: Mengekspor data Personal Funnel

**Report Lending - Rekap Funnel**

- SIT 63.2: Menampilkan data Rekap Funnel

**Report Lending - Pengaturan Funnel**

- SIT 64.2: Menampilkan data Pengaturan Funnel Lending berdasarkan section
- SIT 64.5: Menambahkan Condition pada Performance Indicator
- SIT 64.6: Menambahkan Condition pada Performance Indicator tanpa mengisi field mandatory
- SIT 64.7: Menghapus Condition pada Performance Indicator

Total: 116 TC

### 4. TC yang hanya ada di UAT (tidak ada di SIT)

Ini TC yang ada di UAT tapi tidak ada di SIT. Perlu dicek: apakah TC ini perlu ditambahkan ke SIT.


**Login**

- UAT 1.2: Melakukan login dengan kredensial valid

**Lead Qualification - Aktifitas Referal**

- UAT 27.6: Melihat detail tab Prospek yang saya referalkan

**Sales Tracking Activity - Client Visit List**

- UAT 34.13: Mengekspor data Client Visit List

**Sales Tracking Activity - Rekap Visit**

- UAT 35.7: Mengekspor data Rekap Visit

**Sales Force - CIF Kelolaan**

- UAT 45.11: Menghapus data cif kelolaan
- UAT 45.12: Melakukan filter data
- UAT 45.13: Membuka tab status ( pending request/approved/Rejected/expired)
- UAT 45.14: Melihat detail data
- UAT 45.15: Mencari data pada kolom pencarian
- UAT 45.16: Mencari data kata kunci yang tidak sesuai

**Sales Force - Approval Target Growth**

- UAT 43.5: Melihat detail
- UAT 43.6: Melakukan approval data
- UAT 43.7: Melakukan reject data
- UAT 43.8: Membuka tab status ( pending request/approved/Rejected/expired)

**Sales Force - Pipeline - Setting Role Validate Pipeline**

- UAT 54.3: Menambahkan data setting role
- UAT 54.4: Melihat riwayat setting role
- UAT 54.5: Melihat ilustration alur validasi pipeline
- UAT 54.6: Mengubah data setting role
- UAT 54.7: Menghapus data setting role
- UAT 54.8: Mencari data pada kolom pencarian
- UAT 54.9: Mencari data kata kunci tidak valid (Negative test)

**Sales Force - Pipeline - Dashboard Validate Pipeline**

- UAT 41.5: Melakukan filter data
- UAT 41.7: Melakukan filter data
- UAT 41.9: Melakukan Filter data
- UAT 41.10: Mencari data pada kolom pencarian
- UAT 41.11: Melakukan filter data
- UAT 41.12: Mencari data pada kolom pencarian
- UAT 41.13: Melakukan Filter data
- UAT 41.14: Mencari data pada kolom pencarian
- UAT 41.15: Melakukan Filter data
- UAT 41.16: Mencari data pada kolom pencarian
- UAT 41.17: Melakukan Filter data
- UAT 41.18: Mencari data pada kolom pencarian
- UAT 41.19: Melakukan filter data
- UAT 41.20: Mencari data pada kolom pencarian
- UAT 41.21: Melakukan Filter data
- UAT 41.22: Melakukan filter data
- UAT 41.23: Mencari data pada kolom pencarian

**Report Funding - Rekap Funnel**

- UAT 59.4: Mereset filter data Rekap Funnel

**Report Funding - Pengaturan Funnel**

- UAT 60.4: Menambahkan Kondisi pada Indikator Performa
- UAT 60.5: Menghapus Kondisi pada Indikator Performa
- UAT 60.6: Menambahkan Operator pada Kondisi
- UAT 60.7: Menghapus Operator pada Kondisi

**Report Lending - Personal Funnel**

- UAT 62.2: Menampilkan data Personal Funnel berdasarkan tab

**Report Lending - Rekap Funnel**

- UAT 63.4: Mereset filter data Rekap Funnel

**Report Lending - Pengaturan Funnel**

- UAT 64.4: Menambahkan Kondisi pada Indikator Performa
- UAT 64.5: Menghapus Kondisi pada Indikator Performa
- UAT 64.6: Menambahkan Operator pada Kondisi
- UAT 64.7: Menghapus Operator pada Kondisi

Total: 49 TC

### 5. Judul TC yang beda kata (hampir sama)

Ini TC yang kira-kira sama tapi kalimatnya beda. Perlu dipilih mana yang benar, lalu disamakan.

| Modul | Judul di SIT | Judul di UAT |
|---|---|---|
| Login | SIT 1.3: Melakukan login dengan email tidak terdaftar | UAT 1.3: Melakukan login dengan kredensial tidak terdaftar |
| Login | SIT 1.5: Melakukan login tanpa mengisi email | UAT 1.5: Melakukan login tanpa mengisi username/email |
| Login | SIT 1.7: Melakukan login tanpa mengisi email dan password | UAT 1.7: Melakukan login tanpa mengisi username/email dan password |
| Profile | SIT 2.23: Melakukan revovery code dengan input password yang salah | UAT 2.23: Melkukan revovery code dengan input password yang salah |
| Profile Nasabah & Sales - Sales | SIT 12.8: Mengubah periode filter (Bulan/Tahun) pada grafik Staging Prospek | UAT 12.8: Mengubah periode filter (Bulan-Tahun) pada grafik Staging Prospek |
| Sales Force - Approval Target Growth | SIT 45.6: Melihat detail data | UAT 43.1: Melihat detail |
| Sales Force - Dashboard Sales Force | SIT 51.1: Membuka menu dashboard | UAT 53.1: Membuka menu dashboard sales code |
| Sales Force - Pipeline - Setting Validate Pipeline | SIT 53.7: Mencari data kata kunci tidak valid | UAT 55.7: Mencari data kata kunci tidak valid (Negative test) |
| Sales Force - Pipeline - Dashboard Validate Pipeline | SIT 56.2: Melakukan filter data bulan | UAT 41.3: Melakukan filter data |
| Report Funding - Rekap Funnel | SIT 59.5: Mengunduh data Rekap Funnel | UAT 59.5: Mengekspor data Rekap Funnel |
| Report Lending - Rekap Funnel | SIT 63.5: Mengunduh data Rekap Funnel | UAT 63.5: Mengekspor data Rekap Funnel |

Total: 11 pasangan

### 6. Typo yang ditemukan di judul TC

| Dokumen | No. TC | Modul | Judul |
|---|---|---|---|
| SIT | 2.23 | Profile | Melakukan revovery code dengan input password yang salah |
| SIT | 50.9 | Sales Force - Report - Report Produktivitas | Mengungunduh data calculate |
| SIT | 50.15 | Sales Force - Report - Report Produktivitas | Mengunduh data terget DPK |
| SIT | 51.6 | Sales Force - Dashboard Sales Force | Mencari data Voa realizaion Pada kolom pencarian |
| SIT | 51.20 | Sales Force - Dashboard Sales Force | Melihat detail data card realisasi akuisisi merchat |
| SIT | 51.22 | Sales Force - Dashboard Sales Force | Mencari data realisasi akuisis merchant pada kolom pencarian |
| SIT | 51.24 | Sales Force - Dashboard Sales Force | Melihat detial data card Eligible Upgrade to Prospera / Prioritas |
| UAT | 2.23 | Profile | Melkukan revovery code dengan input password yang salah |

## Catatan

- Selisih 67 TC (867 − 800) berasal dari gabungan TC yang hanya ada di SIT dan TC yang hanya ada di UAT, ditambah perbedaan kata.
- Mobile sudah match, tidak perlu tindakan.
- Kalau dokumen mana yang benar belum diketahui, perlu dikonfirmasi ke tim QA dulu sebelum mengubah dokumen.
