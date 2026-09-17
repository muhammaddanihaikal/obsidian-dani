---
tags:
  - SIT
  - BTN
  - QA
  - BTN-Smart
date: 2026-09-17
updated: 2026-09-17
project: BTN Smart
type: project-note
---

# 📋 SIT - BTN SMART Upgrade Server

> **System Integration Testing (SIT)** untuk proyek BTN SMART Upgrade Server.
> Dokumen dibuat secara otomatis dari Excel test case menggunakan Python script.

---

## 📁 Lokasi File

| Item | Path |
|------|------|
| **Folder Project** | `d:\Project\BTN\SIT\` |
| **Excel Test Case** | `d:\Project\BTN\SIT\Test Case.xlsx` |
| **Template Word** | `d:\Project\BTN\SIT\Form Script - Skenario SIT BTN SMART Upgrade Server.docx` |
| **Output Web (merged)** | `d:\Project\BTN\SIT\Document SIT BTN Smart\SIT BTN SMART Web.docx` |
| **Output Mobile (merged)** | `d:\Project\BTN\SIT\Document SIT BTN Smart\SIT BTN SMART Mobile.docx` |
| **Output Web (per modul)** | `d:\Project\BTN\SIT\Document SIT BTN Smart\Web\` |
| **Output Mobile (per modul)** | `d:\Project\BTN\SIT\Document SIT BTN Smart\Mobile\` |
| **Script per modul** | `generate_all_sit.py` |
| **Script merged** | `generate_merged_sit.py` |

---

## 📊 Ringkasan Modul

### 🌐 Web (BTN SMART Web) — 20 Modul

| No | Modul | Jumlah TC |
|----|-------|-----------|
| 01 | Login | 17 |
| 02 | Profile | 47 |
| 03 | Overview | 13 |
| 04 | User Authority | 80 |
| 05 | Profile Nasabah & Sales | 26 |
| 06 | Bisnis dan Produk | 90 |
| 07 | Kantor | 20 |
| 08 | Menu Target | 6 |
| 09 | Upload Bulk | 115 |
| 10 | Lead Generation | 44 |
| 11 | Lead Qualification | 36 |
| 12 | List Prospek ETB | 20 |
| 13 | Menu Absent | 56 |
| 14 | Sales Tracking Activity | 35 |
| 15 | Setting Absent | 48 |
| 16 | Sales Force | 223 |
| 17 | Report Funding | 45 |
| 18 | Report Lending | 42 |
| 19 | Re-Assign dan Approval | 39 |
| 20 | Export Data Management | 25 |

**Total Web TC: 1.027**

---

### 📱 Mobile (BTN SMART Mobile) — 12 Modul

| No | Modul | Jumlah TC |
|----|-------|-----------|
| 01 | Profile | 2 |
| 02 | Profile Mobile | 30 |
| 03 | Sales Tracking Activity | 5 |
| 04 | Authentication | 16 |
| 05 | Absent | 4 |
| 06 | Log Absensi | 5 |
| 07 | Personal Funnel | 17 |
| 08 | Cuti & Izin | 9 |
| 09 | Prospek & Nasabah | 55 |
| 10 | Agenda | 14 |
| 11 | Fitur | 9 |
| 12 | Sales Force | 7 |

**Total Mobile TC: 173**

---

## ✅ Status Generate

- [x] Folder `Document SIT BTN Smart/Web/` — 20 file `.docx` (per modul)
- [x] Folder `Document SIT BTN Smart/Mobile/` — 12 file `.docx` (per modul)
- [x] `SIT BTN SMART Web.docx` — 1 file merged (1.027 TC, 20 modul)
- [x] `SIT BTN SMART Mobile.docx` — 1 file merged (173 TC, 12 modul)

---

## 📝 Aturan Pengisian Kolom (Merged & Per Modul)

| Kolom | Isi |
|-------|-----|
| **Scenario** | Diambil dari kolom **Steps** di Excel |
| **Expected Result** | Diambil dari kolom **Expected Results** di Excel |
| **Actual Result** | Sama dengan Expected, tiap baris dipastikan diawali **"Berhasil"**, jumlah baris sama |
| **Test Status** | **P** (Passed) — untuk semua baris |
| **Remarks** | Kosong |

---

## 🔗 Catatan Terkait

- [[SIT BTN Smart - Format & Aturan Dokumen]]
- [[SIT BTN Smart - Panduan Generator Script]]

---

*Dibuat: 2026-09-17 | Update terakhir: 2026-09-17 | PIC: Dani*
