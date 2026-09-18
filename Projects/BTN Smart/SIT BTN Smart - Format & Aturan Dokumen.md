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
| 1 | Test Case | Left | Center |
| 2 | Scenario | Left | **Top** |
| 3 | Expected Result | Left | **Top** |
| 4 | Actual Result | Left | **Top** |
| 5 | Test Status (P/F) | Left | Center |
| 6 | Remarks | Left | **Top** |

### Isi Kolom
- **Scenario** ← diambil dari kolom **Steps** di Excel
- **Expected Result** ← diambil dari kolom **Expected Results** di Excel
- **Actual Result** ← dikosongkan (diisi saat testing)
- **Test Status** ← dikosongkan (diisi saat testing)
- **Remarks** ← dikosongkan (diisi saat testing)

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
        ├── SIT-01 Profile.docx
        ├── SIT-02 Sales Tracking Activity.docx
        ├── SIT-03 Login.docx
        └── ... (11 file)
```

> [!NOTE]
> Nomor modul Web dan Mobile **tidak harus sama** karena urutannya berbeda di Excel.
> Web modul Login = SIT-01, Mobile modul Login = SIT-03.

---

## 🔗 Catatan Terkait

- [[SIT BTN Smart - Overview]]
- [[SIT BTN Smart - Panduan Generator Script]]
