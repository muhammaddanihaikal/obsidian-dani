# Audit SIT vs Hasil Uji (UAT)

Tanggal audit: 15 Oktober 2026

Terakhir diupdate: 15 Oktober 2026, pukul 17:36 WIB (10:36 UTC)

## File yang diaudit

| Dokumen | File | Jumlah TC | Jumlah modul |
|---|---|---|---|
| SIT Web | SIT_BTN_SMART_Web.docx | 865 | 79 |
| UAT Web | Dokumen_Hasil_Uji_Web_6.docx | 800 | 79 |
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
| Match SIT dan UAT | Belum (98 TC hanya di SIT, 33 hanya di UAT, 0 beda kata) | Ya, 100% |

## Keputusan: 6 modul yang dipertahankan

Modul 41, 42, 46, 51, 52, dan 53 dipertahankan apa adanya di SIT dan UAT untuk sementara. Alasannya, pengujian teknis mendalam QA di SIT tidak boleh hilang. Perbedaan di modul-modul ini perlu didiskusikan dengan tim sebelum ada perubahan. Jangan diubah atau dihapus dulu saat perbaikan.

## Status dan langkah berikutnya

Status saat ini: **belum aman**.

**Sudah aman**
- SS web: semua 800 TC di UAT sudah punya SS.
- Format SIT web: 865 TC, sesuai dengan header. Semua status P, tidak ada nomor dobel, dan typo sudah diperbaiki.
- Mobile: SIT dan UAT cocok 100%.

**Belum aman**
- Match SIT dan UAT web: 98 TC hanya di SIT dan 33 hanya di UAT.
  - 82 dari yang hanya di SIT dan 17 dari yang hanya di UAT ada di 6 modul yang ditahan (41, 42, 46, 51, 52, 53).
  - Sisanya 16 di SIT dan 16 di UAT ada di modul di luar 6 modul itu. Jumlahnya seimbang, kemungkinan hanya beda penamaan, misalnya "Condition" di SIT dan "Kondisi" di UAT. Perlu dicek.
- Hasil yang diharapkan UAT web: 15 TC menyebut modul lain. 8 di modul yang ditahan (41, 52, 53), dan 7 di modul yang tidak ditahan (43, 44, 49, 50).
- SIT web modul 41: TC 41.6, 41.9, 41.12, dan 41.15 punya judul dan hasil yang sama persis. Modul ini termasuk yang ditahan.
- SS mobile: 5 TC di UAT belum punya SS, yaitu 2.16, 8.11, 12.6, 12.20, dan 13.9.

**Langkah berikutnya**
1. Perbaiki 7 hasil UAT yang tidak sesuai di modul 43, 44, 49, dan 50.
2. Cek 16 pasangan TC yang beda penamaan.
3. Lengkapi 5 SS mobile.
4. Diskusikan 6 modul yang ditahan dengan tim.

## 1. Screenshot (SS) di UAT

### Web: semua TC sudah ada SS

Semua 800 TC di UAT web sudah punya SS.

### Mobile: 5 TC belum ada SS

| Modul | No. TC |
|---|---|
| 2. Modul Profile | 2.16 |
| 8. Modul Personal Funnel | 8.11 |
| 12. Modul Prospek & Nasabah - Input Prospek | 12.6 |
| 12. Modul Prospek & Nasabah - Input Prospek | 12.20 |
| 13. Modul Prospek & Nasabah - List Nasabah ETB | 13.9 |

## 2. Kerapian SIT

### SIT Web

- Jumlah TC 865 sesuai dengan header "Jumlah Script".
- Semua TC berstatus P.
- Tidak ada nomor TC dobel dan tidak ada kolom kosong.
- Header Estimasi dan Last Update sudah terisi.
- Typo di versi sebelumnya (2.22, 18.2 sampai 18.9, 41.1, 43.1, 53.20, 53.23) sudah diperbaiki.

Yang masih perlu dicek:

- TC 41.6, 41.9, 41.12, dan 41.15 punya judul dan hasil yang sama persis: "Membuka detail Validate Pipeline" dan "Menampilkan halaman detail Validate pipeline". Perlu dibedakan sesuai layar yang diuji.

### SIT Mobile

- Jumlah TC 260 sesuai dengan header.
- Semua TC berstatus P.
- Tidak ada nomor TC dobel dan tidak ada kolom kosong.
- Tidak ditemukan typo.

## 3. Kerapian UAT

### UAT Web

Tidak ditemukan nomor TC dobel dan semua TC punya baris hasil yang diharapkan.

Hasil yang diharapkan tidak sesuai dengan modul tempatnya berada. Kemungkinan copy-paste dari modul lain. Perlu dicek ulang:

| No. TC | Modul | Judul | Hasil yang diharapkan | Catatan |
|---|---|---|---|---|
| 41.1 | Pipeline - Dashboard Validate Pipeline | Melakukan filter data | Menampilkan halaman approval sales code | Hasil menyebut approval sales code |
| 41.5 | Pipeline - Dashboard Validate Pipeline | Melakukan filter data | Berhasil melakukan approval data cif kelolaan | Hasil menyebut cif kelolaan |
| 41.6 | Pipeline - Dashboard Validate Pipeline | Mencari data pada kolom pencarian | Berhasil melakukan reject data cif kelolaan | Hasil menyebut cif kelolaan |
| 41.8 | Pipeline - Dashboard Validate Pipeline | Mencari data pada kolom pencarian | Berhasil melakukan approval data target growth | Hasil menyebut target growth |
| 41.9 | Pipeline - Dashboard Validate Pipeline | Melakukan Filter data | Berhasil melakukan reject data target growth | Hasil menyebut target growth |
| 43.1 | Approval Target Growth | Melihat detail | Menampilkan halaman approval cif kelolaan | Hasil menyebut approval cif kelolaan |
| 44.1 | Approval Sales Code | Membuka menu approval sales code | Menampilkan halaman target growth | Hasil menyebut target growth |
| 49.1 | Produktivitas - Bobot Produktivitas | Membuka menu Bobot Produktivitas | Menampilkan halaman cif rebase | Hasil menyebut cif rebase |
| 49.2 | Produktivitas - Bobot Produktivitas | Import data Bobot Produktivitas | Berhasil melakukan rebase cif | Hasil menyebut rebase cif |
| 49.4 | Produktivitas - Bobot Produktivitas | Mengunduh data Bobot Produktivitas | Menampilkan list data cif rebase history | Hasil menyebut cif rebase |
| 50.1 | Produktivitas - Realisasi Merchant | Membuka menu realisasi merchant | Menampilkan halaman report produktivitas | Hasil menyebut report produktivitas |
| 50.2 | Produktivitas - Realisasi Merchant | Import data realisasi merchant | Berhasil mengunduh all data report produktivitas | Hasil menyebut report produktivitas |
| 52.1 | Report - Report Produktivitas | Membuka menu Report produktivitas | Menampilkan halaman setting role validate pipeline | Hasil menyebut setting role validate pipeline |
| 53.1 | Dashboard Sales Force | Membuka menu dashboard sales code | Menampilkan halaman setting validate pipeline | Hasil menyebut setting validate pipeline |
| 53.2 | Dashboard Sales Force | Melakukan filter data berdasarkan bulan | Berhasil menambahkan data dan data akan tampil pada menu dashboard | Hasil berisi kalimat yang janggal, perlu dicek |

### UAT Mobile

- Tidak ada nomor TC dobel dan urutan sudah benar.
- Tidak ditemukan typo.

## 4. Match SIT dan UAT Web

### 4.1 Jumlah TC per modul yang beda (6 modul dipertahankan, lihat bagian Keputusan)

| Modul | SIT | UAT |
|---|---|---|
| 41. Sales Force - Pipeline - Dashboard Validate Pipeline | 25 | 23 |
| 42. Sales Force - Pipeline - Input Pipeline | 11 | 10 |
| 46. Sales Force - Approval Cif Kelolaan | 8 | 7 |
| 51. Sales Force - CIF Rebase | 9 | 7 |
| 52. Sales Force - Report - Report Produktivitas | 33 | 2 |
| 53. Sales Force - Dashboard Sales Force | 31 | 3 |

Nomor modul SIT dan UAT sudah sama semua.

### 4.2 TC yang hanya ada di SIT (98 TC)

Ada di SIT tapi tidak ada di UAT. Perlu dicek apakah TC ini perlu ditambahkan ke UAT.


**Lead Qualification - Aktifitas Referal**

- SIT 27.8: Mencari data tab Prospek yang direferalkan ke saya dengan keyword tidak valid

**Sales Force - Pipeline - Dashboard Validate Pipeline**

- SIT 41.1: Membuka menu dashboard validate pipeline
- SIT 41.4: Membuka detail Chart total pipeline DPK
- SIT 41.6: Membuka detail Validate Pipeline
- SIT 41.7: Membuka detail Chart pipeline data kantor cabang
- SIT 41.9: Membuka detail Validate Pipeline
- SIT 41.10: Membuka detail Chart Sales Input Pipeline
- SIT 41.12: Membuka detail Validate Pipeline
- SIT 41.13: Membuka detail Chart Pipeline Category
- SIT 41.15: Membuka detail Validate Pipeline
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

### 4.3 TC yang hanya ada di UAT (33 TC)

Ada di UAT tapi tidak ada di SIT. Perlu dicek apakah TC ini perlu ditambahkan ke SIT, atau memang tidak perlu.


**Lead Qualification - Aktifitas Referal**

- UAT 27.6: Melihat detail tab Prospek yang saya referalkan

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

## 5. Match SIT dan UAT Mobile

Tidak ada perbedaan. Semua 20 modul dan 260 TC cocok, termasuk judulnya.

## Catatan

- Selisih 65 TC web (865 dikurangi 800) berasal dari 98 TC yang hanya ada di SIT dikurangi 33 TC yang hanya ada di UAT.
- Di UAT mobile masih ada 5 TC yang belum punya SS. Lihat bagian 1.
- Kalau dokumen mana yang benar belum jelas, konfirmasi dulu ke tim QA sebelum mengubah dokumen.
- Modul 41, 42, 46, 51, 52, dan 53 dipertahankan sementara, menunggu diskusi tim.