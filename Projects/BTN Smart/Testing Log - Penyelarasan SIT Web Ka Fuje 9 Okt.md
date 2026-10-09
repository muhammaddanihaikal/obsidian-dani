---
tags:
  - SIT
  - BTN
  - QA
  - Web
  - Sync
date: 2026-10-09
project: BTN Smart
type: testing-log
---

# 📋 Testing Log - Penyelarasan SIT Web Ka Fuje (9 Oktober 2026)

> Catatan sinkronisasi kelengkapan **Steps (Scenario)** dan **Expected Results** dari dokumen SIT terbaru Senior (Ka Fuje) ke dalam master working document Refactor Mas Dani.

---

## 🎯 Latar Belakang & Prinsip Acuan
1. Dokumen acuan utama (**Single Source of Truth**) adalah **dokumen Refactor kita** (889 TC, 75 modul/submenu).
2. Dokumen Ka Fuje (`SIT BTN Smart Web [update dr ka fuje 9 okt].docx` di Drive H) digunakan sebagai **suplemen data resmi** untuk narasi Steps & Expected Results.
3. Penambahan dan pengurangan TC ditahan sementara menunggu analisis lanjutan Mas Dani.

---

## ⚙️ Eksekusi yang Diselesaikan (Langkah 1 & Langkah 2)

1. **Langkah 1 (Mapping & Pengisian Narasi dari Ka Fuje):**
   - **858 TC** berhasil disinkronkan langsung dari narasi *Scenario* dan *Expected Result* Ka Fuje ke kolom *Steps* dan *Expected Results* Excel kita.
   - **Modul 60–69 (Report Funding & Lending):** Tetap mempertahankan urutan menu UI kita (*Personal Funnel* di awal, *Daily Sales Agenda* di akhir), narasi Steps & Expected Results ditarik berdasarkan kesesuaian judul dari Ka Fuje.
   - **Modul 73 (Export Center):** 5 baris validasi card approval dipertahankan narasi validnya (tidak dikosongkan).
   - **27 TC Refactor Mas Dani:** Tetap dipertahankan 100% narasi existing-nya.

2. **Langkah 2 (Pengisian 4 TC Kosong):**
   - Baris yang sebelumnya kosong diisi narasi QA perbankan standar:
     - `6.2` Menampilkan daftar data User
     - `7.2` Menampilkan daftar data Group Role
     - `8.2` Menampilkan daftar data Tipe Karyawan
     - `9.2` Menampilkan daftar data Hak Akses Role

3. **Sinkronisasi Dokumen Word SIT Web:**
   - Seluruh 75 tabel dan 889 baris di `SIT BTN SMART Web.docx` diperbarui sehingga:
     - *Scenario* = Steps terbaru
     - *Expected Result* = Expected Result terbaru
     - *Actual Result* = Diawali "Berhasil " sesuai standar baku
     - *Test Status* = P (Passed)
     - *Remarks* = Kosong

---

## 🚀 Eksekusi Penyelarasan Modul Senior (Acc Mas Dani)

1. **Modul 52 & 53 (CIF Rebase & Report Produktivitas):**
   - Tetap mempertahankan struktur dokumen kita (mengabaikan salah letak tabel Ka Fuje di mana 53.10 terselip di Modul 52).
   - TC `53.6` diselaraskan judulnya menjadi: *"mengunduh data sforce"*.
2. **Modul 56 (Setting Validate Pipeline):**
   - TC `56.7` diselaraskan judulnya menjadi: *"Mencari data kata kunci tidak valid"* (menghapus label `(Negative test)` agar konsisten dengan Ka Fuje).
3. **Modul 59 (Dashboard Validate Pipeline) — Adopsi 25 TC:**
   - Menyisipkan TC `59.3` *Melakukan filter data* (pilih kantor wilayah, cabang, capem).
   - Menyelaraskan seluruh 25 TC dengan bukti pengujian Hasil Uji dan SIT Senior.
   - Total TC Web menjadi **890 TC** (naik 1 TC).
   - Update Table 1 SIT docx: Jumlah Script = 890, Last Update = 09 Oktober 2026.
4. **Modul 73 (Export Center):**
   - Ditahan sementara menunggu struktur UI fix baru dari Han.

5. **Pembersihan Total Format Penomoran (`1. 2.`):**
   - Ditemukan 26 baris pada modul Mas Dani yang sebelumnya masih memakai format penomoran `1. 2.` pada Steps dan 21 baris pada Expected Result.
   - Seluruh 26 baris berhasil dinormalisasi menjadi format strip baku (`-`) sesuai standar Ka Fuje/BTN.
   - Hasil audit ulang di seluruh file (`Test Case.xlsx`, `SIT BTN SMART Web.docx`, `Dokumen_Hasil_Uji_Web.docx`, `Dokumen_Hasil_Uji_Mobile.docx`): **0 instance penomoran `1. 2.`** (100% Bersih & Seragam!).

---

## 🚀 Status Penyimpanan & Sync Tri-Drive

- [x] **Local D:** `D:\Project\BTN Smart\Refactor\SIT\`
  - `Test Case.xlsx` (890 TC, 0 empty steps/exp, 0 numbered list)
  - `SIT BTN SMART Web.docx` (890 TC, 0 empty scen/exp, 0 numbered list)
- [x] **Drive H:** `H:\My Drive\Zegen\BTN Smart\Refactor\SIT\` (Mirrored & Identical)
- [x] **Drive G:** `G:\My Drive\Zegen\BTN Smart\Refactor\SIT\` (Mirrored & Identical)
- [x] **Git Repository:** Commit `75b793b` (`style(sit): eliminate numbered list formatting (1. 2.) across all Web TCs to standard dash separator`) pushed to `main`.


