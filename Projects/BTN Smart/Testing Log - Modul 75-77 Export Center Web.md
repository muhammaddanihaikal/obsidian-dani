# 📝 Testing Log - Modul 75, 76, 77 Export Center Web (Sinkronisasi Bukti Uji Raihan)

Catatan pengujian dan sinkronisasi bukti uji lengkap untuk fitur **Export Center** pada portal **BTN SMART Web**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN SMART Web (Portal Admin / Web App)
* **Modul Resmi (SIT Master 77 Modul)**:
  * **Modul 75**: Export Center - Riwayat Export (8 TC: 75.1 s/d 75.8)
  * **Modul 76**: Export Center - Persetujuan Export (9 TC: 76.1 s/d 76.9)
  * **Modul 77**: Export Center - Aktivitas Export (8 TC: 77.1 s/d 77.8)
* *(Catatan Pemetaan: Pada dokumen lokal Raihan menggunakan penomoran lama 73, 74, 75 karena Re-Assign 73-74 belum digeser. Di SIT Master resmi dan Master Dokumen Hasil Uji, penomoran tetap konsisten pada Modul 75, 76, 77).*
* **Tanggal Sinkronisasi**: 9 Oktober 2026
* **Tester & Kolaborator**: Dani & Raihan (Team QA)
* **Status**: **100% COMPLETE & SYNCED (43 SCREENSHOT EMBEDDED) - TRI-DRIVE & GIT VERIFIED** ✅

---

## 🔍 Ringkasan Fitur & Bukti Uji Raihan
Raihan telah melengkapi seluruh tangkapan layar (screenshot) untuk ketiga submenu Export Center. Seluruh bukti uji (total 43 screenshot) telah diekstrak langsung dari file Word Raihan (`Dokumen_Hasil_Uji_Web Raihan.docx`), disimpan ke folder screenshot aktif + folder backup `(Original Full)`, serta di-embed ke dalam dokumen master:

1. **Modul 75: Riwayat Export (13 Screenshot)**
   * **75.1** Membuka halaman Riwayat Export (1 SS)
   * **75.2** Mencari data riwayat export dengan kata kunci valid (1 SS)
   * **75.3** Mencari data riwayat export dengan kata kunci tidak valid (1 SS - status *No Data*)
   * **75.4** Melihat data riwayat export berdasarkan status (1 SS - tab status)
   * **75.5** Melakukan filter data riwayat export (3 SS - modal filter, apply, hasil)
   * **75.6** Mereset filter data riwayat export (2 SS - sebelum & sesudah reset)
   * **75.7** Melihat detail riwayat export (2 SS - klik detail & drawer info)
   * **75.8** Mengunduh file data export yang tersedia (2 SS - klik unduh & file terunduh)

2. **Modul 76: Persetujuan Export (17 Screenshot)**
   * **76.1** Membuka halaman Persetujuan Export (1 SS)
   * **76.2** Mencari data persetujuan export dengan kata kunci valid (1 SS)
   * **76.3** Mencari data persetujuan export dengan kata kunci tidak valid (1 SS - status *No Data*)
   * **76.4** Melihat data persetujuan export berdasarkan status (1 SS - tab persetujuan)
   * **76.5** Melakukan filter data persetujuan export (3 SS - modal filter, apply, hasil)
   * **76.6** Mereset filter data persetujuan export (2 SS - sebelum & sesudah reset)
   * **76.7** Melakukan approval data pengajuan export (3 SS - klik approve, modal konfirmasi, status berubah Disetujui)
   * **76.8** Melakukan reject data pengajuan export (3 SS - klik reject, modal alasan reject, status berubah Ditolak)
   * **76.9** Melihat detail pengajuan export (2 SS - klik detail & drawer pengajuan)

3. **Modul 77: Aktivitas Export (13 Screenshot)**
   * **77.1** Membuka halaman Aktivitas Export (1 SS)
   * **77.2** Mencari data aktivitas export dengan kata kunci valid (1 SS)
   * **77.3** Mencari data aktivitas export dengan kata kunci tidak valid (1 SS - status *No Data*)
   * **77.4** Melihat data aktivitas export berdasarkan status (1 SS - tab status aktivitas)
   * **77.5** Melakukan filter data aktivitas export (3 SS - modal filter, apply, hasil)
   * **77.6** Mereset filter data aktivitas export (2 SS - sebelum & sesudah reset)
   * **77.7** Melihat detail aktivitas export (2 SS - klik detail & drawer aktivitas)
   * **77.8** Mengunduh file data export yang tersedia (2 SS - klik unduh & file terunduh)

---

## 📋 Tabel Detail 25 Test Case & Status Bukti Uji Master

### Modul 75: Export Center - Riwayat Export
| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Jumlah SS | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :---: | :---: |
| **75.1** | Export Center | Riwayat Export | Membuka halaman Riwayat Export | Positive | High | 1 SS | Embedded ✅ |
| **75.2** | Export Center | Riwayat Export | Mencari data riwayat export dengan kata kunci valid | Positive | Normal | 1 SS | Embedded ✅ |
| **75.3** | Export Center | Riwayat Export | Mencari data riwayat export dengan kata kunci tidak valid | Negative | Normal | 1 SS | Embedded ✅ (No Data) |
| **75.4** | Export Center | Riwayat Export | Melihat data riwayat export berdasarkan status | Positive | Normal | 1 SS | Embedded ✅ |
| **75.5** | Export Center | Riwayat Export | Melakukan filter data riwayat export | Positive | Normal | 3 SS | Embedded ✅ |
| **75.6** | Export Center | Riwayat Export | Mereset filter data riwayat export | Positive | Normal | 2 SS | Embedded ✅ |
| **75.7** | Export Center | Riwayat Export | Melihat detail riwayat export | Positive | High | 2 SS | Embedded ✅ |
| **75.8** | Export Center | Riwayat Export | Mengunduh file data export yang tersedia | Positive | High | 2 SS | Embedded ✅ |

### Modul 76: Export Center - Persetujuan Export
| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Jumlah SS | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :---: | :---: |
| **76.1** | Export Center | Persetujuan Export | Membuka halaman Persetujuan Export | Positive | High | 1 SS | Embedded ✅ |
| **76.2** | Export Center | Persetujuan Export | Mencari data persetujuan export dengan kata kunci valid | Positive | Normal | 1 SS | Embedded ✅ |
| **76.3** | Export Center | Persetujuan Export | Mencari data persetujuan export dengan kata kunci tidak valid | Negative | Normal | 1 SS | Embedded ✅ (No Data) |
| **76.4** | Export Center | Persetujuan Export | Melihat data persetujuan export berdasarkan status | Positive | Normal | 1 SS | Embedded ✅ |
| **76.5** | Export Center | Persetujuan Export | Melakukan filter data persetujuan export | Positive | Normal | 3 SS | Embedded ✅ |
| **76.6** | Export Center | Persetujuan Export | Mereset filter data persetujuan export | Positive | Normal | 2 SS | Embedded ✅ |
| **76.7** | Export Center | Persetujuan Export | Melakukan approval data pengajuan export | Positive | High | 3 SS | Embedded ✅ |
| **76.8** | Export Center | Persetujuan Export | Melakukan reject data pengajuan export | Positive | High | 3 SS | Embedded ✅ |
| **76.9** | Export Center | Persetujuan Export | Melihat detail pengajuan export | Positive | High | 2 SS | Embedded ✅ |

### Modul 77: Export Center - Aktivitas Export
| No | Modul | Sub Menu | Judul Test Case | Tipe | Prioritas | Jumlah SS | Status Bukti Uji |
| :---: | :---: | :---: | :--- | :---: | :---: | :---: | :---: |
| **77.1** | Export Center | Aktivitas Export | Membuka halaman Aktivitas Export | Positive | High | 1 SS | Embedded ✅ |
| **77.2** | Export Center | Aktivitas Export | Mencari data aktivitas export dengan kata kunci valid | Positive | Normal | 1 SS | Embedded ✅ |
| **77.3** | Export Center | Aktivitas Export | Mencari data aktivitas export dengan kata kunci tidak valid | Negative | Normal | 1 SS | Embedded ✅ (No Data) |
| **77.4** | Export Center | Aktivitas Export | Melihat data aktivitas export berdasarkan status | Positive | Normal | 1 SS | Embedded ✅ |
| **77.5** | Export Center | Aktivitas Export | Melakukan filter data aktivitas export | Positive | Normal | 3 SS | Embedded ✅ |
| **77.6** | Export Center | Aktivitas Export | Mereset filter data aktivitas export | Positive | Normal | 2 SS | Embedded ✅ |
| **77.7** | Export Center | Aktivitas Export | Melihat detail aktivitas export | Positive | High | 2 SS | Embedded ✅ |
| **77.8** | Export Center | Aktivitas Export | Mengunduh file data export yang tersedia | Positive | High | 2 SS | Embedded ✅ |

---

## 🗂️ Sinkronisasi Tri-Drive & Version Control

1. **Penyimpanan Folder Screenshot Aktif (`Hasil Uji\Screenshot\Web\`)**:
   * `75. Export Center - Riwayat Export/` (8 subfolder, total 13 file PNG)
   * `76. Export Center - Persetujuan Export/` (9 subfolder, total 17 file PNG)
   * `77. Export Center - Aktivitas Export/` (8 subfolder, total 13 file PNG)
   * Disinkronkan 100% ke Local D, Google Drive H, dan Google Drive G (MD5 Match).

2. **Folder Backup uncropped `(Original Full)`**:
   * Dibuat dan diamankan di Local D dan Google Drive G.
   * **Zero-Backup Drive H**: Drive H tetap bersih dari folder `(Original Full)` sesuai aturan operasional.

3. **Dokumen Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**:
   * Tables 151 s/d 156 memuat seluruh 43 gambar dengan layout rapi (`width=5.90 in`, center alignment, 5.8 pt paragraph spacing).
   * XML duplicate ID dibersihkan.
   * Table of Contents (TOC) di-refresh via Word COM automation.
   * Disinkronkan ke Drive H dan Drive G dengan MD5 hash identik.

4. **Git Repository (`D:\Project\BTN Smart\Refactor`)**:
   * Commit: `feat(export-center): sync and embed 43 complete screenshots from Raihan for Modul 75, 76, and 77`
   * Push ke `origin/main` berhasil.
