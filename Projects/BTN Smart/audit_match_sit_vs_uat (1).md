# Audit SIT vs Hasil Uji (UAT)

Tanggal audit: 15 Oktober 2026

## File yang diaudit

| Dokumen | File | Jumlah TC | Jumlah modul |
|---|---|---|---|
| SIT Web | SIT_BTN_SMART_Web.docx | 865 | 79 |
| UAT Web | Dokumen_Hasil_Uji_Web_5.docx | 800 | 79 |
| SIT Mobile | SIT_BTN_SMART_Mobile.docx | 260 | 20 |
| UAT Mobile | Dokumen_Hasil_Uji_Mobile_1.docx | 260 | 20 |

Cara cocok: modul dicocokkan berdasarkan nama modul. TC dicocokkan berdasarkan judul yang sudah dinormalisasi (huruf kecil, spasi dirapikan). Judul yang beda kata tapi hampir sama dicatat terpisah.

## Ringkasan

| Pemeriksaan | Web | Mobile |
|---|---|---|
| Jumlah TC SIT = Jumlah Script di header | Ya (865) | Ya (260) |
| Jumlah TC UAT | 800 | 260 |
| Modul SIT = modul UAT | Ya (79) | Ya (20) |
| TC belum ada SS (UAT) | 0 | 5 |
| Nomor TC dobel | Tidak | Tidak |
| Match SIT dan UAT | Belum (100 TC hanya di SIT, 35 hanya di UAT, 1 beda kata) | Ya, 100% |

## 1. Screenshot (SS) di UAT

### Mobile: 5 TC belum ada SS

| Modul | No. TC |
|---|---|
| 2. Modul Profile | 2.16 |
| 8. Modul Personal Funnel | 8.11 |
| 12. Modul Prospek & Nasabah - Input Prospek | 12.6 |
| 12. Modul Prospek & Nasabah - Input Prospek | 12.20 |
| 13. Modul Prospek & Nasabah - List Nasabah ETB | 13.9 |

### Web: semua TC sudah ada SS

Tidak ada TC yang belum punya SS.

## 2. Kerapian SIT

### SIT Web

- Jumlah TC 865 sesuai dengan header "Jumlah Script".
- Semua TC berstatus P.
- Tidak ada nomor TC dobel dan tidak ada kolom kosong.
- Header Estimasi dan Last Update sudah terisi.

Typo yang perlu diperbaiki:

| No. TC | Judul / hasil | Kesalahan |
|---|---|---|
| 2.22 | Hasil yang diharapkan: "Menampilkan data revovery doe..." | revovery, seharusnya recovery |
| 18.2 sampai 18.9 | Judul "... Data Kantor ..." | "Data Data Kantor", kata Data terulang. Kemungkinan seharusnya "Data Kantor" |
| 41.1 | Judul "Membukan menu dashboard validate pipeline" | Membukan, seharusnya Membuka |
| 43.1 | Hasil: "Menampilkan halaman approval terget growth" | terget, seharusnya target |
| 53.20 | Hasil dan actual: "Menampilkan halaman detail realisasi akuisisi merchat" | merchat, seharusnya merchant |
| 53.23 | Hasil: "... realisasi akuisisi merchat" | merchat, seharusnya merchant |

Judul yang tidak lengkap:

Judul berikut hanya berbunyi "Membuka detail" tanpa objek. Perlu dilengkapi sesuai layarnya.

- 41.6, 41.9, 41.12, 41.15 (Sales Force - Pipeline - Dashboard Validate Pipeline)

### SIT Mobile

- Jumlah TC 260 sesuai dengan header.
- Semua TC berstatus P.
- Tidak ada nomor TC dobel dan tidak ada kolom kosong.
- Tidak ditemukan typo.

## 3. Kerapian UAT

### UAT Web

| No. TC | Kesalahan |
|---|---|
| 2.22 | "revovery" di hasil yang diharapkan, seharusnya "recovery" |
| 18.2 sampai 18.9 | "Data Data Kantor", kata Data terulang |
| 45.1 | Judulnya "Membuka menu cif kelolaan", tapi hasil yang diharapkannya "Menampilkan halaman approval terget growth". Hasilnya tidak sesuai judul. Kemungkinan copy-paste yang salah. |

### UAT Mobile

- Tidak ada nomor TC dobel dan urutan sudah benar.
- Tidak ditemukan typo.

## 4. Match SIT dan UAT Web

### 4.1 Jumlah TC per modul yang beda

| Modul | SIT | UAT |
|---|---|---|
| 41. Sales Force - Pipeline - Dashboard Validate Pipeline | 25 | 23 |
| 42. Sales Force - Pipeline - Input Pipeline | 11 | 10 |
| 46. Sales Force - Approval Cif Kelolaan | 8 | 7 |
| 51. Sales Force - CIF Rebase | 9 | 7 |
| 52. Sales Force - Report - Report Produktivitas | 33 | 2 |
| 53. Sales Force - Dashboard Sales Force | 31 | 3 |

### 4.2 TC yang hanya ada di SIT (100 TC)

Ada di SIT tapi tidak ada di UAT. Perlu dicek apakah TC ini perlu ditambahkan ke UAT.


**Lead Qualification - Aktifitas Referal**

- SIT 27.8: Mencari data tab Prospek yang direferalkan ke saya dengan keyword tidak valid

**Sales Tracking Activity - Client Visit List**

- SIT 34.2: Menampilkan daftar data Client Visit List

**Sales Tracking Activity - Rekap Visit**

- SIT 35.2: Menampilkan daftar data Rekap Visit

**Sales Force - Pipeline - Dashboard Validate Pipeline**

- SIT 41.1: Membukan menu dashboard validate pipeline
- SIT 41.4: Membuka detail Chart total pipeline DPK
- SIT 41.6: Membuka detail
- SIT 41.7: Membuka detail Chart pipeline data kantor cabang
- SIT 41.9: Membuka detail
- SIT 41.10: Membuka detail Chart Sales Input Pipeline
- SIT 41.12: Membuka detail
- SIT 41.13: Membuka detail Chart Pipeline Category
- SIT 41.15: Membuka detail
- SIT 41.16: List validate Pipeline - mencari data pada kolom pencarian
- SIT 41.17: Membuka detail list validate pipeline
- SIT 41.18: Detail Validate Pipeline - Melakukan Filter data
- SIT 41.19: Detail Validate pipeline - mengunduh data validate pipeline
- SIT 41.20: Melakukan Validate data menggunakan user BM
- SIT 41.21: Melakukan validate all data menggunakan user BM
- SIT 41.22: Melakukan unvalidate data menggunakan user BM
- SIT 41.23: Melakukan Validate data menggunakan user RO Head
- SIT 41.24: Melakukan validate all data menggunakan user RO Head
- SIT 41.25: Melakukan unvalidate data menggunakan user RO Head

**Sales Force - Pipeline - Input Pipeline**

- SIT 42.3: Melakukan filter data dengan tidak menginput filter mandatory (Negative test)

**Sales Force - Approval Target Growth**

- SIT 43.1: Membuka menu Approval Target Growth
- SIT 43.2: Melakukan filter data
- SIT 43.7: Mencari data pada kolom pencarian
- SIT 43.8: Mencari data kata kunci yang tidak sesuai

**Sales Force - Approval Cif Kelolaan**

- SIT 46.5: Membuka tab status ( pending request/approved/Rejected/expired)

**Sales Force - CIF Rebase**

- SIT 51.7: Melakukan Unarchive cif
- SIT 51.9: Mencari data pada kolom pencarian

**Sales Force - Report - Report Produktivitas**

- SIT 52.1: Mencari data kata kunci yang tidak sesuai
- SIT 52.3: Melakukan filter data
- SIT 52.5: Mengunduh data resume
- SIT 52.6: Tab sforce
- SIT 52.7: mengunduh data sforce
- SIT 52.8: Tab Calculate
- SIT 52.9: Mengunduh data calculate
- SIT 52.10: Tab Realisasi
- SIT 52.11: Mengunduh data realisasi
- SIT 52.12: Tab Target
- SIT 52.13: Mengunduh data Target
- SIT 52.14: Tab Target DPK
- SIT 52.15: Mengunduh data target DPK
- SIT 52.16: Tab DPK port
- SIT 52.17: Mengunduh data Target DPK port
- SIT 52.18: Tab konek Echannel
- SIT 52.19: Mengunduh data konek echannel
- SIT 52.20: Tab All CIF
- SIT 52.21: Mengunduh data all cif
- SIT 52.22: Tab SegMove
- SIT 52.23: Mengunduh data Segmove
- SIT 52.24: Tab Visit
- SIT 52.25: Mengunduh data Visit
- SIT 52.26: Tab Merchant
- SIT 52.27: Mengunduh data Merchant
- SIT 52.28: Tab Tier
- SIT 52.29: Mengunduh data Tier
- SIT 52.30: Tab Referal
- SIT 52.31: Mengunduh data Referal
- SIT 52.32: Tab Presensi
- SIT 52.33: Mengunduh data Presensi

**Sales Force - Dashboard Sales Force**

- SIT 53.3: Melakukan filter data
- SIT 53.5: Filter data Voa Realization
- SIT 53.6: Mencari data Voa realization pada kolom pencarian
- SIT 53.7: Melihat detail Voa Realization
- SIT 53.8: Melihat detail card Cif Kelolaan
- SIT 53.9: Filter data Cif Kelolaan
- SIT 53.10: mencari data Cif Kelolaan pada kolom pencarian
- SIT 53.11: Melihat detail Cif Kelolaan
- SIT 53.12: Melihat detail card skor Produktivitas
- SIT 53.13: Filter data produktivitas
- SIT 53.14: Melihat detail skor Produktivitas
- SIT 53.15: Melihat detail data card konek echannel
- SIT 53.16: Filter data konek echannel
- SIT 53.17: Mencari data konek echannel pada kolom pencarian
- SIT 53.18: Melihat detail data konek echannel
- SIT 53.19: Melihat detail data card realisasi visit
- SIT 53.20: Melihat detail data card realisasi akuisisi merchant
- SIT 53.21: Filter data realisasi akuisisi merchant
- SIT 53.22: Mencari data realisasi akuisisi merchant pada kolom pencarian
- SIT 53.23: Melihat detail data realisasi merchant
- SIT 53.24: Melihat detail data card Eligible Upgrade to Prospera / Prioritas
- SIT 53.25: Filter data Eligible Upgrade to Prospera / Prioritas
- SIT 53.26: Mencari data Eligible Upgrade to Prospera Prioritas pada kolom pencarian
- SIT 53.27: Melihat detail data Eligible Upgrade to Prospera / Prioritas
- SIT 53.28: Melihat detail data card Referral to Prospera / Prioritas
- SIT 53.29: Filter data Referral to Prospera / Prioritas
- SIT 53.30: Mencari data Referral to Prospera / Prioritas pada kolom pencarian
- SIT 53.31: Melihat detail data Referral to Prospera / Prioritas

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

### 4.3 TC yang hanya ada di UAT (35 TC)

Ada di UAT tapi tidak ada di SIT. Perlu dicek apakah TC ini perlu ditambahkan ke SIT, atau memang tidak perlu.


**Lead Qualification - Aktifitas Referal**

- UAT 27.6: Melihat detail tab Prospek yang saya referalkan

**Sales Tracking Activity - Client Visit List**

- UAT 34.13: Mengekspor data Client Visit List

**Sales Tracking Activity - Rekap Visit**

- UAT 35.7: Mengekspor data Rekap Visit

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

**Sales Force - Approval Target Growth**

- UAT 43.1: Melihat detail
- UAT 43.6: Melakukan approval data
- UAT 43.7: Melakukan reject data
- UAT 43.8: Membuka tab status ( pending request/approved/Rejected/expired)

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

### 4.4 Judul beda kata (1 pasang)

| Modul | Judul di SIT | Judul di UAT |
|---|---|---|
| Login | SIT 1.7: Melakukan login tanpa mengisi email dan password | UAT 1.7: Melakukan login tanpa mengisi username/email dan password |

## 5. Match SIT dan UAT Mobile

Tidak ada perbedaan. Semua 20 modul dan 260 TC cocok, termasuk judulnya.

## Catatan

- Selisih 65 TC web (865 dikurangi 800) berasal dari 100 TC yang hanya ada di SIT dikurangi 35 TC yang hanya ada di UAT.
- Di UAT mobile masih ada 5 TC yang belum punya SS. Lihat bagian 1.
- Kalau dokumen mana yang benar belum jelas, konfirmasi dulu ke tim QA sebelum mengubah dokumen.