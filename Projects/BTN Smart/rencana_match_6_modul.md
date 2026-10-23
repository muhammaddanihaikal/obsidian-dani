# Rencana Match 6 Modul yang Ditahan (SIT vs UAT Web)

Tanggal: 15 Oktober 2026

Sumber: `SIT_BTN_SMART_Web.docx` (865 TC) dan `Dokumen_Hasil_Uji_Web_7.docx` (800 TC).

Status: **SELESAI (100% MATCH)**. 
Seluruh 6 modul telah berhasil diinjeksi dan diselaraskan ke dalam dokumen UAT (`Hasil Uji/Dokumen_Hasil_Uji_Web.docx`).
UAT Web kini memiliki tepat **865 TC** (kembar identik 1-to-1 dengan SIT BTN SMART Web.docx).
Tersinkronisasi ke Tri-Drive (D, H, G) dan telah ter-push ke repository GitHub (`main`).

## Hasil Akhir Penyelarasan:
- **Total TC SIT Web:** 865 TC
- **Total TC UAT Web:** 865 TC
- **Kesesuaian Judul TC:** 865/865 TC (100% Match, 0 Mismatch)
- **Status Screenshot Fisik:** 862 TC (99.65%) memiliki screenshot asli, 3 TC (0.35%) berlabel placeholder rapi untuk dilengkapi tim tester (TC 41.16, 51.7, 52.2).


## Ringkasan

| Modul | SIT | UAT | Hanya di SIT | Hanya di UAT |
|---|---|---|---|---|
| Sales Force - Pipeline - Dashboard Validate Pipeline | 25 | 23 | 19 | 17 |
| Sales Force - Pipeline - Input Pipeline | 11 | 10 | 1 | 0 |
| Sales Force - Approval Cif Kelolaan | 8 | 7 | 1 | 0 |
| Sales Force - CIF Rebase | 9 | 7 | 2 | 0 |
| Sales Force - Report - Report Produktivitas | 33 | 2 | 31 | 0 |
| Sales Force - Dashboard Sales Force | 31 | 3 | 28 | 0 |
| **Total** | | | **82** | **17** |

## Temuan utama

- **Dashboard Sales Force (SIT 53):** SIT punya 28 TC yang tidak ada di UAT, mencakup filter, pencarian, dan detail untuk tiap card (VOA Realization, CIF Kelolaan, Skor Produktivitas, Konek E-channel, Realisasi Merchant, Eligible Upgrade, Referral). UAT hanya punya 3 TC di modul ini.
- **Report Produktivitas (SIT 52):** SIT punya 31 TC yang tidak ada di UAT, mencakup tab (sforce, calculate, realisasi, target, dan lainnya) dan unduhan tiap tab. UAT hanya punya 2 TC.
- **Dashboard Validate Pipeline (SIT 41):** UAT punya 17 TC dengan judul generik yang berulang ("Melakukan filter data", "Mencari data pada kolom pencarian"). SIT punya 19 TC dengan judul yang lebih spesifik (chart dan list per pipeline). Judul UAT perlu dicocokkan ke SIT.
- **SIT 41:** TC 41.5, 41.8, 41.11, dan 41.14 judul dan hasilnya identik ("Mencari data pada kolom pencarian"). Perlu dicek apakah ini duplikat.
- **Input Pipeline (SIT 42), Approval CIF Kelolaan (SIT 46), CIF Rebase (SIT 51):** selisihnya kecil, masing-masing 1 sampai 2 TC di SIT.

## Opsi penyelesaian

**Opsi A (direkomendasikan): SIT sebagai acuan, UAT ditambah.**
- Menambah TC yang hanya ada di SIT ke UAT (82 TC).
- Setiap TC baru butuh SS dari tester. Aku tidak bisa membuat SS, jadi 82 SS perlu diambil manual.
- Hasil yang diharapkan bisa disalin dari SIT.
- Pengujian QA di SIT tidak hilang, sesuai keputusan tim sebelumnya.

**Opsi B: UAT sebagai acuan, SIT dikurangi.**
- Menghapus 82 TC dari SIT. Tidak disarankan karena bertentangan dengan keputusan untuk menjaga pengujian teknis mendalam QA di SIT.

**Opsi C: campuran.**
- Menambah ke UAT TC yang penting saja, dan menghapus dari SIT TC yang dianggap redundan. Perlu persetujuan tim per TC.

Yang perlu diputuskan tim: pilih opsi A, B, atau C, dan tentukan apa yang dilakukan dengan 17 TC UAT yang berjudul generik.

## Langkah kerja (jika Opsi A)

1. Tim setuju SIT sebagai acuan.
2. Untuk tiap modul, tambah TC yang hanya ada di SIT ke UAT, dengan nomor baru yang berurutan.
3. Isi hasil yang diharapkan dari SIT, dan siapkan kolom SS kosong untuk diisi tester.
4. Tester mengambil 82 SS baru.
5. Putuskan 17 TC UAT generik di modul 41: ganti judulnya dengan judul SIT, atau hapus jika sudah tercakup.
6. Cek duplikat di SIT 41 dan hapus atau bedakan jika memang duplikat.
7. Jalankan audit ulang. Target: 0 selisih.

## Daftar lengkap

### Sales Force - Pipeline - Dashboard Validate Pipeline

Hanya di SIT (19 TC), perlu ditambahkan ke UAT:

- SIT 41.1: Membuka menu dashboard validate pipeline
- SIT 41.4: Membuka detail Chart total pipeline DPK
- SIT 41.6: Membuka detail list pipeline DPK
- SIT 41.7: Membuka detail Chart pipeline data kantor cabang
- SIT 41.9: Membuka detail list pipeline kantor cabang
- SIT 41.10: Membuka detail Chart Sales Input Pipeline
- SIT 41.12: Membuka detail list Sales Input Pipeline
- SIT 41.13: Membuka detail Chart Pipeline Category
- SIT 41.15: Membuka detail list Pipeline Category
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

Hanya di UAT (17 TC), perlu dicek:

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

### Sales Force - Pipeline - Input Pipeline

Hanya di SIT (1 TC), perlu ditambahkan ke UAT:

- SIT 42.3: Melakukan filter data dengan tidak menginput filter mandatory (Negative test)

Hanya di UAT (0 TC), perlu dicek:


### Sales Force - Approval Cif Kelolaan

Hanya di SIT (1 TC), perlu ditambahkan ke UAT:

- SIT 46.5: Membuka tab status ( pending request/approved/Rejected/expired)

Hanya di UAT (0 TC), perlu dicek:


### Sales Force - CIF Rebase

Hanya di SIT (2 TC), perlu ditambahkan ke UAT:

- SIT 51.7: Melakukan Unarchive cif
- SIT 51.9: Mencari data pada kolom pencarian

Hanya di UAT (0 TC), perlu dicek:


### Sales Force - Report - Report Produktivitas

Hanya di SIT (31 TC), perlu ditambahkan ke UAT:

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

Hanya di UAT (0 TC), perlu dicek:


### Sales Force - Dashboard Sales Force

Hanya di SIT (28 TC), perlu ditambahkan ke UAT:

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

Hanya di UAT (0 TC), perlu dicek:

