---
tags:
  - SIT
  - UAT
  - BTN
  - QA
  - Format
  - Word
  - HasilUji
date: 2026-10-12
project: BTN Smart
type: standard
---

# 📄 Hasil Uji BTN Smart - Format & Aturan Dokumen Word

> Standar format dokumen Word Hasil Uji yang digunakan untuk **BTN SMART** (Web & Mobile).
> Di-generate dan distandarisasi secara otomatis menggunakan script Python berbasis struktur folder Google Drive dan file master SIT.

---

## 📐 Layout Halaman

| Property | Value | Keterangan |
|---|---|---|
| **Orientasi** | Portrait | Standar dokumen A4 |
| **Ukuran Kertas** | A4 (21.01 cm × 29.7 cm) | `11910 dxa × 16838 dxa` |
| **Margin Atas (Section 3 UAT)** | 4.76 cm (135 pt) | 2700 dxa (wajib 135 pt / 2700 dxa agar tidak bertabrakan dengan tabel floating header) |
| **Margin Bawah** | 0.49 cm | `280 dxa` |
| **Margin Kiri** | 1.55 cm | `880 dxa` (Section 3 UAT) |
| **Margin Kanan** | 0.35 cm | `180 dxa` (Section 3 UAT) |

---

## 🗂️ Struktur Dokumen Keseluruhan

```
Cover & Halaman Awal
├── Table 0 - Informasi Dokumen (6 baris × 2 kolom)
├── Table 1 - Penandatangan Penyedia Jasa (5 baris × 4 kolom)
├── Table 2 - Diketahui Oleh BTN (4 baris × 1 kolom)
├── Daftar Isi (TOC Section - Field w:sdt, mengalir normal)
└── Histori Perbaikan (Wajib di Halaman Baru — pageBreakBefore=True & keepWithNext=True)
    └── Table 3 - Histori Perbaikan (2 baris × 5 kolom)

Isi UAT (1 Tabel Utuh per Modul — Total 77 Tabel di Web, 20 Tabel di Mobile)
├── Heading 1: "[No]. Modul [Nama Modul]" (Tanpa baris enter kosong!)
└── Table UAT Utuh Modul:
    ├── Row 0: Blue Header (No. | User Acceptance Testing (UAT))
    ├── Row 1: Header TC Pertama (X.1 | [Judul TC]) — Abu-abu D0CECE
    ├── Row 2: Screenshot TC X.1 (Tanpa enter kosong di awal cell!)
    ├── Row 3: Expected Result TC X.1 (Compact & Simetris, vAlign Center)
    ├── Row 4: Header TC Kedua (X.2 | [Judul TC]) — Abu-abu D0CECE
    ├── Row 5: Screenshot TC X.2
    ├── Row 6: Expected Result TC X.2
    └── ... dst mengalir sampai TC terakhir modul tersebut
```

> [!IMPORTANT]
> **Pola Kunci 1 Tabel Utuh per Modul:**
> Seluruh TC dalam satu modul digabungkan menjadi **1 `<w:tbl>` utuh**. DILARANG memecah modul menjadi 2 tabel terpisah (`X.1` dan `X.2 dst.`), karena dua tabel yang menempel akan menyebabkan **garis border hitam tebal 2 lapis** antara `X.1` dan `X.2`.

---

## 📌 Struktur Baris di Dalam Tabel UAT

### 1. Blue Header Row (Row 0 Tabel Modul)
- **Kolom 0 (`No.`):** Width `709 dxa`, Background `#2C5293` (Biru Tua), Font Arial 10pt Bold Putih, **Align Center** (Horizontal & Vertical Center).
- **Kolom 1 (`User Acceptance Testing (UAT)`):** Width `9084 dxa`, Background `#2C5293`, Font Arial 10pt Bold Putih, **Align Center** (Horizontal & Vertical Center).

### 2. Grey TC Header Row (Judul TC, misal `7.1`, `7.2`, dll.)
- **Kolom 0 (`No.`):**
  - Background `#D0CECE` (Abu-abu).
  - Teks: Nomor TC murni tanpa spasi di depan/belakang (`7.1`).
  - **Alignment:** **Align Center** (Horizontal Center + Vertical Center).
  - Spacing: `Space Before = 0 pt`, `Space After = 0 pt`, `Line Spacing = 1.0` (single).
  - Font: Arial 10pt Regular, Hitam.
- **Kolom 1 (`TC Title`):**
  - Background `#D0CECE` (Abu-abu).
  - Teks: Diawali 1 spasi agar berjarak manis dari border vertikal (`" Membuka halaman User"`).
  - **Alignment:** **Align Center Left** (Horizontal Left + Vertical Center).
  - Spacing: `Space Before = 0 pt`, `Space After = 0 pt`, `Line Spacing = 1.0` (single).
  - Font: Arial 10pt Regular, Hitam.
- **Pagination Rule:** Paragraf pada baris judul TC wajib diset **`keep_with_next = True`** (`<w:keepNext/>`) agar judul TC tidak pernah tertinggal sendirian di bagian bawah halaman terpisah dari gambar screenshot-nya.

### 3. Screenshot Row
- **Kolom 0:** Kosong, vertikal merge (`vMerge = restart`).
- **Kolom 1:** Berisi gambar screenshot inline (`<wp:inline>`).
- **DILARANG ADA ENTER KOSONG DI AWAL CELL:**
  - Pastikan paragraf pertama di dalam cell screenshot adalah gambar itu sendiri (`P0` berisi drawing). Dilarang menyisipkan paragraf kosong (`<w:p>`) di atas gambar, karena Word akan memotong paragraf kosong tersebut ke halaman atas dan meninggalkan **kotak putih kosong melompong** setinggi halaman.
- **Tinggi Baris (`trHeight`):**
  - Baris screenshot yang sudah memiliki gambar **DILARANG memiliki `<w:trHeight w:val="4316"/>` (tinggi paksa 7.6 cm)**. Biarkan tinggi baris mengikuti ukuran gambar + cell margin.
- **Spacing Paragraf Gambar:** `Space Before = 6 pt`, `Space After = 6 pt`, `Alignment = Center`.

### 4. Expected Result Row (`Hasil yang diharapkan [STATUS]:`)
- **Kolom 0:** Kosong, vertikal merge (`vMerge`).
- **Kolom 1:** Berisi teks hasil yang diharapkan dan status hasil uji.
- **Standar Dimensi & Vertical Alignment:**
  - **DILARANG memiliki tinggi paksa `1290 dxa` (`64.5 pt` / `2.3 cm`)** yang membuat bagian bawah cell melompong.
  - Cell diset **Vertical Alignment: Center** (`<w:vAlign w:val="center"/>`).
  - **Padding Simetris:** Paragraf label pertama diberi `Space Before = 6 pt`, paragraf narasi/status terakhir diberi `Space After = 6 pt`, dan antar-paragraf `Space After = 2 pt`, `Line Spacing = 1.15`.
  - Hasilnya: Jarak putih di atas label dan di bawah status sama rata (simetris) dan padat proporsional.

---

## 🎨 Standar Teks "Hasil yang diharapkan [STATUS]:"

1. **Sumber Teks Baku:** Wajib mengambil teks ringkasan resmi dari dokumen SIT.
2. **❌ Dilarang Keras Penomoran Angka (`1. 2. 3. ...`):**
   - Di dokumen Word, teks harus mengalir rapi dalam bentuk narasi (bukan numbered list).
3. **Format & Warna Font:**
   - **Label** `"Hasil yang diharapkan [STATUS]:"`: Arial 10pt, **Hitam (`#000000`)**, **Bold**.
   - **Isi Narasi SIT**: Arial 10pt, **Biru BTN (`#2C5293`)**, **Regular / Normal**.
   - **Tag Status Akhir** (` - [Success]` / ` - [Failed]`): Arial 10pt, **Biru BTN (`#2C5293`)**, **Regular / Normal (DILARANG BOLD)**.
4. **Contoh Tampilan Baku:**
   > **Hasil yang diharapkan [STATUS]:**
   > Berhasil menampilkan halaman User. - [Success]

---

## 🏷️ Judul Modul (Heading 1) & Header Page Rules

### 1. Aturan Paragraph Spacing Judul Modul
- **DILARANG MENYISIPKAN ENTER KOSONG DI BAWAH JUDUL MODUL:**
  - Di bawah judul modul (`Heading 1`), tabel UAT langsung menyambung tanpa diselingi paragraf kosong.
- **Paragraph Spacing Baku:**
  - `Space Before`: `12 pt` (memberikan ruang lega dari tabel modul sebelumnya).
  - `Space After`: `6 pt` (memberi jarak proporsional ke header tabel biru).
  - `Keep with Next`: `True` (judul modul tidak boleh menggantung di ujung bawah halaman).

### 2. Aturan Logo Header (Mencegah Judul Terbelah)
- **Masalah:** Jika logo di header menggunakan mode `wrapSquare` (Square wrap), judul modul yang berada di paling atas halaman akan terdorong dan membungkus logo (misal angka `1.` terlempar ke kanan logo, dan teks `Modul Login` turun ke bawah).
- **Aturan Baku:**
  - Seluruh gambar logo di `word/header1.xml` WAJIB menggunakan mode **`wrapNone`** (`<wp:wrapNone/>`).
  - Dengan `wrapNone`, logo header tidak akan pernah bertabrakan atau memecah susunan teks judul modul di dokumen body.

---

## 📊 Ukuran Kolom & Geometri Tabel UAT

| Kolom | Lebar (dxa) | ≈ cm | Alignment Horisontal | Alignment Vertikal |
|---|---|---|---|---|
| **Col 0 (No.)** | `709 dxa` / `720 dxa` | ~1.25 cm | Center | Center |
| **Col 1 (Content/Title)** | `9084 dxa` / `9090 dxa` | ~16.0 cm | Left (spasi depan) | Center |
| **Total Tabel** | **9793 dxa – 9810 dxa** | **~17.3 cm** | **Center** | - |

- **Table Alignment:** `<w:jc w:val="center"/>` dengan `<w:tblInd w:w="0" w:type="dxa"/>`.
- **Table Borders:** Single line, `sz = 4` (0.5 pt), warna `#000000`.

---

## 🔗 Referensi & SOP Terkait
- [[Hasil Uji BTN Smart - Panduan Generator & Siklus Uji]] — Siklus sinkronisasi Tri-Drive (Local D, Drive H, Drive G) dan automasi Git.
- Repository GitHub: `https://github.com/muhammaddanihaikal/btn-smart-refactor.git`
