---
tags:
  - SIT
  - BTN
  - QA
  - Format
  - Word
date: 2026-09-17
project: BTN Smart
type: standard
---

# 📄 SIT BTN Smart - Format & Aturan Dokumen Word

> Standar format dokumen Word SIT yang digunakan untuk **BTN SMART Upgrade Server**.
> Template referensi: `Form Script - Skenario SIT BTN SMART Upgrade Server.docx`

---

## 📐 Layout Halaman

| Property | Value |
|----------|-------|
| **Orientasi** | Landscape |
| **Ukuran Kertas** | A4 (27.9 × 21.6 cm) |
| **Margin Atas** | 1.3 cm |
| **Margin Bawah** | 0.5 cm |
| **Margin Kiri** | 0.8 cm |
| **Margin Kanan** | 0.8 cm |

---

## 🗂️ Struktur Dokumen per File

Setiap file `.docx` (per modul) memiliki struktur berikut:

```
1. Header Table (SIT)
   ├── Kolom 1: [logo/kosong]
   ├── Kolom 2: "System Integration Testing (SIT)"
   └── Kolom 3: "Page <PAGE>" [field auto-nomor]

2. Info Table
   ├── Row 1: Application | Jumlah Script | Version
   ├── Row 2: Modul: <nomor. nama modul (platform)> | Estimasi | Last Update
   └── Row 3: [merged, kosong]

3. Title Paragraph (List Paragraph style, Bold)
   └── "<No>. <Modul> - <Sub Menu> (<Platform>)"
       atau "<No>. <Modul> (<Platform>)" jika tidak ada Sub Menu

4. Data Table
   └── Header + baris test case

5. sectPr (page settings)
```

---

## 🏷️ Aturan Judul & Penomoran

### Judul Modul
- **Ada Sub Menu**: `1. Login - Verifikasi OTP`
- **Tidak ada Sub Menu**: `1. Login`

### Penomoran Kolom No
- Format: `<nomor_modul>.<urutan_tc>`
- Contoh: `1.1`, `1.2`, ..., `1.17`
- Setiap file modul dimulai dari `.1` lagi

### Penomoran File
- Format: `SIT-<dua_digit> <Nama Modul>.docx`
- Contoh: `SIT-01 Login.docx`, `SIT-16 Sales Force.docx`

---

## 📊 Format Tabel Data

| Kolom | Header | Horizontal Align | Vertical Align |
|-------|--------|-----------------|----------------|
| 0 | No | Center | Center |
| 1 | Test Case | Center / Left | Center |
| 2 | Scenario | Center / Left | Center / Top |
| 3 | Expected Result | Center / Left | Center / Top |
| 4 | Actual Result | Center / Left | Center / Top |
| 5 | Test Status (P/F) | **Center** | **Center** |
| 6 | Remarks | Center / Left | Center / Top |

> [!NOTE]
> Pada dokumen master gabungan (`SIT BTN SMART Web.docx` & `SIT BTN SMART Mobile.docx`), seluruh sel tabel (kolom 0 s/d 6) diset **rata tengah (Center / Center)** secara horizontal (`jc='center'`) dan vertikal (`vAlign='center'`) sesuai hasil review dan standarisasi template perbankan BTN.

### Isi Kolom
- **Scenario** ← diambil dari kolom **Steps** di Excel.
- **Expected Result** ← diambil dari kolom **Expected Results** di Excel.
- **Actual Result** ← Sama dengan Expected Result, tiap baris diawali **"Berhasil"**.
- **Test Status (P/F)** ← Wajib diisi huruf kapital **`P`** (Passed) untuk pengujian yang berhasil atau **`F`** (Failed) jika gagal.
  > [!IMPORTANT]
  > **Aturan Penulisan Status `P` (Kapital):**
  > 1. Status **WAJIB** menggunakan **huruf kapital tunggal `P`** (bukan huruf kecil `p`, bukan `Pass`, bukan `Passed`).
  > 2. Format sel: font **Trebuchet MS 11pt Regular**, alignment **Center** horizontal dan **Center** vertikal.
  > 3. Semua baris test case yang lulus uji diisi dengan **`P`**.
- **Remarks** ← dikosongkan (diisi catatan jika ada defect / blocker).

### Format Multiline
- Steps/Expected yang di Excel mengandung `\n` (Enter) → di Word menjadi **paragraf terpisah** dalam satu cell (bukan `\n` biasa)

---

## 📁 Struktur Folder Output

```
d:\Project\BTN\SIT\
└── Document SIT BTN Smart\
    ├── Web\
    │   ├── SIT-01 Login.docx
    │   ├── SIT-02 Profile.docx
    │   └── ... (20 file)
    └── Mobile\
        ├── SIT-01 Login.docx
        ├── SIT-02 Profile.docx
        ├── SIT-03 Sales Tracking Activity.docx
        └── ... (11 file)
```

> [!NOTE]
> Web modul Login = SIT-01, Mobile modul Login = SIT-01 (keduanya sekarang seragam diawali modul Login).

---

## 🔗 Catatan Terkait

- [[SIT BTN Smart - Overview]]
- [[SIT BTN Smart - Panduan Generator Script]]
