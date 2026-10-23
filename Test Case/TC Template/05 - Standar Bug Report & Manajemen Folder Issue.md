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
> * **Deskripsi**: {Jelaskan alur masalah secara runut, padat, dan to the point (1–2 kalimat)}
> * **Expected**: {Kondisi ideal/seharusnya sesuai PRD atau aturan bisnis}
> * **Actual**: {Kondisi error, cacat sistem, atau penyimpangan yang terjadi saat ini}
> * **Evidence Awal**:
>   * [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
> * **Bukti Retest (Done)**:
>   * [https://files.catbox.moe/yyy.png](https://files.catbox.moe/yyy.png)
> * **Catatan Retest**:
>   * {Catatan ringkas verifikasi hasil pengujian setelah bug diperbaiki}
```

> [!TIP]
> ### 🎯 PRINSIP PENULISAN: SIMPLE & TO THE POINT (NO BASA-BASI)
> 1. **Ringkas & Padat**:
>    - Isi `Deskripsi`, `Expected`, dan `Actual` harus langsung menusuk ke inti masalah (maksimal 1–2 kalimat per bagian).
>    - Hindari kalimat bertele-tele atau pengulangan kata yang tidak perlu.
> 2. **Aturan Langkah Reproduksi (Steps to Reproduce / STR)**:
>    - **DILARANG membuat STR jika langkahnya sedikit / pendek**: Jika masalahnya langsung muncul dalam 1–2 klik (misal: klik tombol Keluar langsung error, klik tombol Export file kosong, klik Reset field tidak tereset), **JANGAN** membuat section Steps to Reproduce. Cukup jelaskan aksinya langsung di bagian **Deskripsi**.
>    - **HANYA gunakan STR jika alurnya panjang / kompleks**: Tambahkan `> * **Langkah Reproduksi**:` hanya ketika bug membutuhkan skenario bertahap lintas halaman atau multi-aksi (misal: input data di Form A $\rightarrow$ ubah status di Tab B $\rightarrow$ lakukan approval di Menu C $\rightarrow$ terjadi error kalkulasi).

> [!WARNING]
> ### 🚫 DILARANG MENYISIPKAN LINK PANJANG / QUERY PARAMETER DI DALAM TEKS!
> - **DILARANG KERAS** menaruh URL domain lengkap atau rentetan query parameter panjang di bagian **Deskripsi**, **Expected**, maupun **Actual** (contoh buruk: `https://terasrumah-sandbox.zegen.app/auth/error?error=invalid_request&error_description=The+request+is+missing+a+required+parameter...`). Hal ini membuat laporan berantakan dan membingungkan yang membaca!
> - Tulis kalimat fungsional yang bersih, manusiawi, dan to the point:
>   * ❌ **JANGAN:** `Sistem ter-redirect ke https://terasrumah-sandbox.zegen.app/auth/error dengan pesan "Permintaan Tidak Dapat Diproses" (query parameter: error=invalid_request&error_description=The+request+is+missing...)`
>   * ✅ **GUNAKAN:** `Sistem mengarahkan pengguna ke halaman error dengan pesan "Permintaan Tidak Dapat Diproses" dan proses logout gagal.`
> - **Satu-satunya link URL yang diperbolehkan** hanyalah link bukti screenshot Catbox di bagian **Evidence**!

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

> [!IMPORTANT]
> **Prinsip Utama Komentar Huly:**
> - **Super Ringkas & To The Point (Maksimal 1–2 kalimat saja)**, tanpa basa-basi pembuka/penutup.
> - **Highlight Kuning Huly**: Bungkus nama fitur, status, atau istilah penting dengan backtick `` `...` `` agar Huly otomatis mewarnainya kuning.
> - **Clickable Link**: Link bukti Catbox **WAJIB** berupa markdown link ganda `[URL](URL)` agar langsung bisa diklik di Huly.

### A. Kondisi 1: Retest Berhasil (`Done`)
```markdown
Retest: Done

Fitur Export di seluruh tab `Daily Sales Agenda` sudah terintegrasi dengan drawer `Export Center` dan status export tercatat normal.

Bukti Retest:
* `Daily Sales Agenda Funding`: [https://files.catbox.moe/3rpt87.png](https://files.catbox.moe/3rpt87.png)
* `Daily Sales Agenda Lending`: [https://files.catbox.moe/6gznpn.png](https://files.catbox.moe/6gznpn.png)
```

### B. Kondisi 2: Retest Masih Ditemukan Masalah (`Re-Open`)
```markdown
Retest: Re-Open

Saat tombol Reset ditekan, field `Fee Based`, `Info Bulan`, dan `Info Tahun` belum ter-reset dan masih mempertahankan nilai sebelumnya.

Bukti Retest:
* `Kondisi Filter Setelah Reset`: [https://files.catbox.moe/a9ssv5.png](https://files.catbox.moe/a9ssv5.png)
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

Saat user mengirimkan screenshot temuan bug / retest baru, AI **WAJIB** mengikuti alur bertahap berikut:

> [!CAUTION]
> ### 🛑 ATURAN WAJIB: KONFIRMASI DULU SEBELUM EKSEKUSI!
> AI **DILARANG KERAS** langsung membuat folder issue fisik atau menulis file `report.txt` / `komentar_huly.txt` sebelum meminta izin dan mendapatkan konfirmasi/persetujuan eksplisit dari User!
> 
> **Yang wajib dilakukan AI terlebih dahulu:**
> Tampilkan draft preview ringkas di chat (Calon Judul Issue, Menu, Deskripsi, Expected, Actual), lalu tanyakan ke User:
> *"Apakah temuan issue ini sudah pas bro? Mau langsung dibuatkan folder dan report-nya atau ada yang perlu dikoreksi?"*

### Tahapan Eksekusi AI:
1. **Analisis Gambar:** Buka/inspeksi gambar, cari area kotak merah, pesan error toast, URL/menu yang sedang dibuka, dan kondisi data.
2. **Draft Preview & Minta Konfirmasi (WAJIB):**
   * Sajikan rancangan ringkas:
     * **Judul**: `🐞 [BUG] | [Modul] - [Sub Menu]: [Ringkasan Masalah]`
     * **Menu**: `[Modul] → [Sub Menu]`
     * **Deskripsi & Actual vs Expected**: Tulis dengan kalimat bersih fungsional (**DILARANG menempelkan URL panjang atau query parameter mentah**).
   * Minta User konfirmasi terlebih dahulu sebelum membuat file apapun.
3. **Eksekusi Setelah User Konfirmasi ("Ya" / "Gas"):**
   * **Tentukan Nomor (+1):** Cek folder menu di direktori laporan (`Issue Report/<Nama Menu>/`), hitung nomor issue berikutnya (+1 dari nomor terakhir, misal `01`, `02`, `03`...).
   * **Buat Folder Issue:** Buat folder dengan format `[Nomor Issue] - [Judul Singkat Masalah]`.
   * **Simpan & Upload Screenshot:**
     * Simpan file screenshot ke folder issue tersebut.
     * Upload file gambar ke Catbox via cURL API (`https://catbox.moe/user/api.php`) untuk mendapatkan URL Catbox.
   * **Generate Dokumen Lokal:**
     * Tulis file `report.txt` lengkap (berisi Judul, Menu, Deskripsi, Expected, Actual, dan link Catbox).
     * Tulis file `komentar_huly.txt` (format ringkas siap copas untuk Huly).
   * **Simpan Salinan ke Obsidian (Master Tracker):**
     * Tambahkan blok issue bug tersebut ke dalam file master tracker project di Obsidian:
       `D:\Obsidian\dani\Projects\<Nama Project>\Regression Test - <Nama Project>.md`
     * Update tabel rekapitulasi status jika tersedia di file tersebut.
     * Buat `git commit` di `D:\Obsidian\dani` agar riwayat perubahan aman tercatat.
4. **Sajikan ke User:** Tampilkan konfirmasi folder selesai dibuat beserta teks siap copas ke Huly di chat.

---

## 🗣️ 7. Glosarium Terminologi Tim (Wajib Digunakan AI)

Dalam penulisan seluruh teks bug report (`Deskripsi`, `Expected`, `Actual`, `Langkah Reproduksi`, dan `Komentar`), AI **WAJIB** menggunakan istilah baku industri/tim berikut dan **DILARANG** menggunakan padanan bahasa Indonesia kaku:

| Istilah Baku Tim (✅ Wajib) | Istilah Kaku (❌ DILARANG) |
| :--- | :--- |
| **user** | ~~pengguna~~ |
| **button** | ~~tombol~~ |
| **field** / **input** | ~~kolom isian / bidang~~ |
| **dropdown** | ~~menu tarik-turun~~ |
| **checkbox** | ~~kotak centang~~ |
| **popup** / **modal** | ~~jendela sembul~~ |
| **download** / **export** | ~~unduh / ekspor data~~ |
| **submit** / **save** | ~~kirim / simpan formulir~~ |
| **mandatory** | ~~wajib diisi~~ *(boleh pakai mandatory/wajib)* |

---

## 📓 8. Sinkronisasi Salinan ke Obsidian Vault

Setiap ada penambahan issue baru atau pembaruan retest:
1. **Single Source of Truth:**
   * Selain membuat folder fisik lokal (`Issue Report/<Menu>/<No> - <Judul>/`), seluruh laporan **WAJIB dicatat salinannya** ke file master tracker di Obsidian:
     `D:\Obsidian\dani\Projects\<Nama Project>\Regression Test - <Nama Project>.md` (atau `Bug Tracker - <Nama Project>.md`).
2. **Format Salinan di Obsidian:**
   * Gunakan format blockquote standar yang seragam dengan seluruh issue sebelumnya:
     ```markdown
     ### 🐞 [BUG] | {Nama Modul} - {Sub Menu}: {Ringkasan Singkat Masalah}

     > * **Menu**: {Modul} → {Sub Menu} (Tab {Nama Tab jika ada})
     > * **Status**: Open
     > * **Deskripsi**: ...
     > * **Expected**: ...
     > * **Actual**: ...
     > * **Evidence Awal**:
     >   * [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
     ```
3. **Pembaruan Hasil Retest:**
   * Saat status issue di Huly di-update (menjadi `Done`, `Re-Open`, atau `Rejected`), perbarui juga baris `> * **Status**:` dan tambahkan `> * **Bukti Retest (Done)**:` beserta link Catbox dan catatan retest di file Obsidian tersebut.
4. **Git Versioning:**
   * Lakukan commit git lokal pada vault `D:\Obsidian\dani` setiap kali selesai menambahkan atau memperbarui status issue:
     `git commit -m "docs(<project>): log new bug <No> - <Judul>"`
