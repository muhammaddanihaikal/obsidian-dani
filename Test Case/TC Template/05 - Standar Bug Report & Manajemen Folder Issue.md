---
tags:
  - QA
  - BugReport
  - Huly
  - Template
  - FolderStructure
date: 2026-10-23
project: Standard
---

# 🐞 05 - Standar Bug Report & Manajemen Folder Issue

> Panduan baku arsitektur folder lokal (File Manager), penomoran issue incremental (+1), format deskripsi bug report untuk **Huly**, serta format draft komentar retest QA.

---

## 🗂️ 1. Hierarki & Arsitektur Folder Lokal (File Manager)

Setiap kali memulai pengujian pada project baru atau modul baru, arsip bukti dan laporan di File Explorer wajib disusun secara rapi dan hierarkis:

```
📁 Issue Report/ (atau Hasil Test/)
└── 📁 [Nama Modul atau Menu]/
    ├── 📁 01 - [Judul Singkat Issue 1]/
    │   ├── 📄 report.txt
    │   ├── 📄 komentar_huly.txt
    │   ├── 🖼️ evidence_awal_01.png
    │   └── 🖼️ retest_done_01.png
    ├── 📁 02 - [Judul Singkat Issue 2]/        <-- Nomor otomatis bertambah (+1)
    │   ├── 📄 report.txt
    │   ├── 📄 komentar_huly.txt
    │   └── 🖼️ evidence_awal.png
    └── 📁 03 - [Judul Singkat Issue 3]/        <-- +1 untuk issue berikutnya
```

### 📌 Aturan Penamaan & Penomoran Folder (+1 Rule):
1. **Root Folder**: Gunakan nama `Issue Report` atau `Hasil Test`.
2. **Folder Menu**: Dikelompokkan berdasarkan nama Menu atau Modul sistem (misal: `User Authority`, `Menu Absent`, `Report Funding`).
3. **Folder Issue**: Dibuat **1 folder khusus untuk 1 issue**.
   * Format nama folder: `[Nomor Issue] - [Judul Singkat Masalah]`
   * **Aturan Penomoran Incremental (+1)**: Nomor folder diawali dari `01`, dan jika ada temuan bug baru di menu yang sama, nomor folder otomatis bertambah **+1** (`01`, `02`, `03`, dst.).
   * *Contoh:*
     * `01 - Validasi Filter Tanggal Tidak Berfungsi`
     * `02 - File Excel Hasil Export Kosong Tanpa Baris Data`
     * `03 - Tombol Reset Filter Tidak Mereset Field Bulan dan Tahun`

---

## 📄 2. Standar Dua File `.txt` di Dalam Folder Issue

Di dalam setiap folder issue, **WAJIB** terdapat 2 file teks utama:
1. `report.txt` $\rightarrow$ Dokumen sumber utama yang berisi detail lengkap bug untuk di-input sebagai **Issue Baru di Huly**.
2. `komentar_huly.txt` $\rightarrow$ Template teks siap *copy-paste* untuk kolom **Komentar / Update Retest di Huly**.

---

## 📋 3. Template Baku `report.txt` (Input Issue Baru Huly)

Gunakan template markdown ini saat membuat file `report.txt`:

```markdown
🐞 [BUG] | {Nama Modul} - {Sub Menu}: {Ringkasan Singkat Masalah}

> * **Menu**: {Modul} → {Sub Menu} (Tab {Nama Tab jika ada})
> * **Status**: Open
> * **Deskripsi**: {Jelaskan alur masalah secara runut, jelas, dan kapan issue ini terpicu}
> * **Expected**: {Kondisi ideal/seharusnya sesuai PRD atau aturan bisnis}
> * **Actual**: {Kondisi error, cacat sistem, atau penyimpangan yang terjadi saat ini}
> * **Evidence Awal**:
>   * [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
> * **Bukti Retest (Done)**:
>   * [https://files.catbox.moe/yyy.png](https://files.catbox.moe/yyy.png)
> * **Catatan Retest**:
>   * {Catatan ringkas verifikasi hasil pengujian setelah bug diperbaiki}
```

### 🛠️ Opsional: Technical Evidence (Jika Ada Error DevTools / API)
Jika bug berkaitan dengan error backend/network, tambahkan blok teknis berikut:
```markdown
> * **Technical Evidence**:
>   * **API Endpoint**: `POST /api/v1/...`
>   * **Status Code**: `500 Internal Server Error`
>   * **Error Response**: `{"message": "Column 'id' cannot be null"}`
```

---

## 💬 4. Template Baku `komentar_huly.txt` (Komentar Retest Huly)

File ini digunakan saat developer menandai issue sudah diperbaiki dan QA melakukan retest.

### A. Kondisi 1: Retest Berhasil (`Done`)
```markdown
Retest: Done

{Penjelasan ringkas 1 kalimat bahwa fitur/masalah sudah diperbaiki dan sesuai. Kata kunci penting dibungkus backtick `...` agar ter-highlight kuning di Huly}.

Bukti Retest:
* `{Label Skenario/Fitur 1}`: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
* `{Label Skenario/Fitur 2}`: [https://files.catbox.moe/yyy.png](https://files.catbox.moe/yyy.png)
```

### B. Kondisi 2: Retest Masih Ditemukan Masalah (`Re-Open`)
```markdown
Retest: Re-Open

{Penjelasan ringkas dan tegas kendala atau bug turunan yang masih terjadi setelah dilakukan retest}.

Bukti Retest:
* `{Kondisi Masih Issue}`: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
```

---

## 🖼️ 5. Standar Tangkapan Layar (Screenshot) & Catbox

1. **Penamaan File Screenshot Lokal:**
   * Bukti Awal: `evidence_awal_01.png`, `evidence_awal_02.png`
   * Bukti Retest: `retest_done_01.png`, `retest_done_02.png` (atau gunakan nama skenario spesifik: `retest_done_filter_reset.png`).
2. **Highlight Red Box:**
   * Beri penanda kotak merah pada area yang membuktikan error (misal pesan error toast, kolom yang salah, atau data yang hilang) agar developer langsung memahami konteks masalah.
3. **Upload Otomatis ke Catbox (API cURL):**
   * Upload file screenshot ke Catbox menggunakan command cURL:
     ```bash
     curl.exe -s -F "reqtype=fileupload" -F "fileToUpload=@<path_file_gambar>" https://catbox.moe/user/api.php
     ```
   * Perintah di atas akan langsung mengembalikan URL publik (misal: `https://files.catbox.moe/abc123.png`).
4. **Format Link di Huly:**
   * Di dalam Huly, link **WAJIB** berupa clickable markdown format:
     `[https://files.catbox.moe/abc123.png](https://files.catbox.moe/abc123.png)`

---

## 🤖 6. Alur Kerja Otomatis AI Agent saat Menerima Screenshot Baru

Saat user mengirimkan screenshot temuan bug / retest baru, AI harus otomatis menjalankan tahapan berikut:
1. **Analisis Gambar:** Buka/inspeksi gambar, cari area kotak merah, pesan error toast, URL/menu yang sedang dibuka, dan kondisi data.
2. **Tentukan Menu & Nomor (+1):** Cek folder menu di direktori laporan (`Issue Report/<Nama Menu>/`). Hitung nomor issue berikutnya (+1 dari nomor terakhir, misal `01`, `02`, `03`...).
3. **Buat Folder Issue:** Buat folder dengan format `[Nomor Issue] - [Judul Singkat Masalah]`.
4. **Simpan & Upload Screenshot:**
   * Simpan file screenshot ke folder issue tersebut.
   * Upload file gambar ke Catbox melalui API cURL (`https://catbox.moe/user/api.php`) untuk mendapatkan URL Catbox.
5. **Generate Dokumen:**
   * Tulis file `report.txt` lengkap (berisi Judul, Menu, Deskripsi, Expected, Actual, dan link Catbox).
   * Tulis file `komentar_huly.txt` (format ringkas siap copas untuk Huly).
6. **Sajikan ke User:** Tampilkan ringkasan temuan dan teks siap copas di chat.
