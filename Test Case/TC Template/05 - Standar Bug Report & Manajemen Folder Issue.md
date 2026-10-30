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
📁 Bug Report/
└── 📁 [Nama Modul atau Menu]/
    ├── 📁 01 - [Judul Singkat Issue 1]/
    │   ├── 📄 report.txt
    │   ├── 📄 komentar_huly.txt
    │   ├── 🖼️ evidence_01_halaman_error.png
    │   └── 🖼️ retest_done_01_sukses_logout.png
    ├── 📁 02 - [Judul Singkat Issue 2]/        <-- Nomor otomatis bertambah (+1)
    │   ├── 📄 report.txt
    │   ├── 📄 komentar_huly.txt
    │   └── 🖼️ evidence_01_export_kosong.png
    └── 📁 03 - [Judul Singkat Issue 3]/        <-- +1 untuk issue berikutnya
```

### 📌 Aturan Penamaan & Penomoran Folder (+1 Rule):
1. **Root Folder**: Gunakan nama `Bug Report`.
2. **Folder Menu**: Dikelompokkan berdasarkan nama Menu atau Modul sistem (misal: `User Authority`, `Menu Absent`, `Report Funding`).
3. **Folder Issue**: Dibuat **1 folder khusus untuk 1 issue**.
   * Format nama folder: `[Nomor Issue] - [Judul Singkat Masalah]`
   * **Aturan Penomoran Incremental (+1)**: Nomor folder diawali dari `01`, dan jika ada temuan bug baru di menu yang sama, nomor folder otomatis bertambah **+1** (`01`, `02`, `03`, dst.).
   * *Contoh:*
     * `01 - Validasi Filter Tanggal Tidak Berfungsi`
     * `02 - File Excel Hasil Export Kosong Tanpa Baris Data`
     * `03 - Tombol Reset Filter Tidak Mereset Field Bulan dan Tahun`

### 🛑 Aturan Alur Pembuatan Issue Baru (Review & Approval Gate):
* **AI Dilarang Langsung Eksekusi & Dilarang Upload Catbox Sebelum Di-ACC**:
  Saat ada temuan bug baru atau screenshot baru di folder `tampungan screenshot`, AI **TIDAK BOLEH** langsung membuat folder issue lokal, tidak boleh menghapus/memindahkan file screenshot, dan **DILARANG mengunggah screenshot ke Catbox sebelum di-ACC oleh user** agar tidak membuang waktu jika ada revisi judul/deskripsi.
* **Tahap 1 (Fast Draft - Tanpa Upload Catbox Dulu)**:
  - AI menganalisis screenshot langsung dari file lokal di folder tampungan.
  - Sajikan draft proposal issue lengkap ke chat (`Judul`, `Menu`, `Deskripsi`, `Expected`, `Actual`).
  - Pada bagian Evidence draf chat cukup tulis label bukti / nama file lokal (tunda upload Catbox sampai draf disetujui).
* **Tahap 2 (User Approval)**:
  - AI wajib menunggu persetujuan/ACC eksplisit dari User (contoh: *"gas"*, *"oke"*, *"eksekusi"*).
* **Tahap 3 (Eksekusi Setelah Di-ACC)**:
  - **Baru upload ke Catbox**: AI mengunggah screenshot ke Catbox menggunakan API untuk mendapatkan link publik `[URL](URL)`.
  - Buat folder issue `01/02/+1`, simpan file `report.txt` (dengan link Catbox yang sudah aktif) dan `komentar_huly.txt` (kosong).
  - Pindahkan bukti ke folder issue dan bersihkan file dari `tampungan screenshot`.
  - Update master tracker di Obsidian (`Regression Test - ...md`) dan langsung `git commit` & `push`.

---

## 📄 2. Standar Dua File `.txt` di Dalam Folder Issue

Di dalam setiap folder issue, **WAJIB** terdapat 2 file teks utama:
1. `report.txt` $\rightarrow$ Dokumen sumber utama yang berisi detail lengkap bug untuk di-input sebagai **Issue Baru di Huly**.
2. `komentar_huly.txt` $\rightarrow$ Template teks siap *copy-paste* untuk kolom **Komentar / Update Retest di Huly**.
   * **PENTING**: Saat issue baru pertama kali dibuat, file `komentar_huly.txt` ini **WAJIB DIBIARKAN KOSONG** (karena belum ada aktivitas retest). File ini baru diisi nanti saat proses retest/verifikasi perbaikan bug dilakukan.

---

## 📋 3. Template Baku `report.txt` (Input Issue Baru Huly)

Gunakan template markdown ini saat membuat file `report.txt` (format ini siap langsung di-copas ke deskripsi Huly):

```markdown
🐞 [BUG] | {Ringkasan Singkat Masalah (Simple & Enak Dibaca)}

* **Menu**: {Modul} → {Sub Menu} (Tab {Nama Tab jika ada})
* **Deskripsi**: {Jelaskan alur masalah secara runut, padat, dan to the point (1–2 kalimat)}
* **Expected**: {Kondisi ideal/seharusnya sesuai PRD atau aturan bisnis}
* **Actual**: {Kondisi error, cacat sistem, atau penyimpangan yang terjadi saat ini}
* **Evidence**:
  * {Label 1-2 Kata}: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
```

> [!IMPORTANT]
> ### 🚫 BEBAS KUNING-KUNING (FORMAT BERSIH & RAPI)
> 1. **Dilarang Menggunakan Blockquote (`> `)**:
>    - Jangan gunakan prefiks `> ` di awal baris karena di Huly akan memunculkan **garis vertikal kuning/oranye**. Gunakan bullet point biasa (`* `) agar tampilan rapi dan bersih.
> 2. **Dilarang Menggunakan Backticks (`` `...` ``)**:
>    - Jangan gunakan tanda kutip miring (backticks) karena di Huly akan berubah menjadi **badge/kotak kuning**.
>    - Untuk menyebutkan nilai, nama tombol, atau pesan toast/error, gunakan tanda kutip dua biasa (`"..."`) atau plain text.

> [!IMPORTANT]
> ### 🚫 ATURAN STATUS DI `report.txt` VS OBSIDIAN
> - **Di file `report.txt` DILARANG memasukkan baris `Status:`**: Karena di aplikasi Huly status sudah memiliki dropdown tersendiri di panel kanan (Open, In Progress, Closed, dll.), sehingga tidak boleh ada tulisan status di dalam teks deskripsi issue!
> - **Di file Master Tracker Obsidian (`Regression Test - ...md`) BARIS STATUS TETAP WAJIB ADA**: Status (`Open`, `Done`, `Re-Open`, `Rejected`) tetap dicatat di Obsidian untuk melacak rekapitulasi pengujian.

> [!TIP]
> ### 🎯 PRINSIP PENULISAN: SIMPLE & ENAK DIBACA (NATURAL FLOW, BEBAS KATA MUBAZIR)
> 1. **Aturan Judul Baku - The Golden Formula QA Profesional (Simple & Enak Dibaca)**:
>    - **Format Wajib**: `🐞 [BUG] | [Komponen / Fitur Spesifik] + [Kondisi Cacat Sistem]` (TANPA mencantumkan nama modul/menu di judul).
>    - **Filosofi Panjang & Ritme (Natural Flow)**:
>      * 🎯 **Fokus Utama**: **Simple, To The Point, dan Enak Dibaca**. Judul harus mengalir secara alami dan langsung dipahami dalam sekali baca oleh Developer atau PM.
>      * 🚫 **Bebas Kuota Kaku & Anti-Mubazir**: Jangan memaksakan kuota jumlah kata dengan menyelipkan kata pengganjal (*filler words*) seperti *"Normal"*, *"Tanpa Data"*, *"Data"*, atau *"Pesan/Respon"*.
>      * 📏 **Panjang Fleksibel**: Boleh 5–7 kata jika sudah padat dan jelas, atau 8–10 kata jika memang membutuhkan konteks lokasi/alur yang spesifik. Panjang berapapun diperbolehkan selama tidak bertele-tele dan enak dibaca.
>    - **Aturan Tipografi & Besar-Kecil Huruf (Title Case Headline)**:
>      * **Wajib Huruf KAPITAL di Awal Kata**: Huruf pertama judul dan seluruh **Kata Utama** (Kata Benda, Kata Kerja, Kata Sifat, Istilah Teknis). Contoh: `Button`, `Halaman`, `Form`, `Gagal`, `Redirect`, `Logout`, `Kosong`, `Error`.
>      * **Wajib Huruf KECIL (*lowercase*)**: Seluruh **Kata Hubung & Preposisi**: `dan`, `atau`, `ke`, `di`, `pada`, `dari`, `saat`, `dengan`, `untuk`, `yang`.
>      * *Contoh:*
>        - ✅ `Button Halaman Utama Gagal Redirect ke Login Internal` ('ke' kecil).
>        - ✅ `Button Masuk dengan Akun Lain Tidak Berfungsi` ('dengan' kecil).
>        - ✅ `Button Hapus Tetap Aktif pada Parent Root Kantor` ('pada' kecil).
>    - **Prinsip Utama**:
>      * ✅ **Objektif & Profesional**: Menyebutkan komponen spesifik dan kondisi cacatnya secara ringkas.
>      * ❌ **Bukan Bahasa Curhat/Komplain Nasabah**: Hindari format keluhan pengguna (*"Belum bisa..."*, *"Gak bisa..."*).
>      * ❌ **Bukan Salinan Toast Mentah**: Teks lengkap toast cukup ditaruh di bagian **Actual Result**.
> 2. **Penyebutan Akun / Role User**:
>    - **HANYA sebutkan role/akun user JIKA User memberi tahu di chat** (misal User bilang: *"ini aku test pakai superadmin"* $\rightarrow$ baru tulis *"Saat user login sebagai Superadmin..."*).
>    - Jika User **TIDAK** menyebutkan akun apa yang dipakai, **JANGAN MENGARANG ROLE**. Cukup gunakan kata umum: *"Saat user menekan button Keluar..."*.
> 3. **Label Singkat pada Evidence (1–2 Kata)**:
>    - Setiap link screenshot pada bagian **Evidence** (baik di `report.txt` maupun di master tracker Obsidian) **WAJIB** diawali label ringkas 1–2 kata untuk menjelaskan apa tangkapan layar tersebut sebelum link Catbox-nya.
>    - *Contoh:*
>      * `* Halaman Error: [https://files.catbox.moe/abc123.png](https://files.catbox.moe/abc123.png)`
>      * `* Modal Konfirmasi: [https://files.catbox.moe/def456.png](https://files.catbox.moe/def456.png)`
>      * `* Respons Error: [https://files.catbox.moe/ghi789.png](https://files.catbox.moe/ghi789.png)`
>    - Dilarang menaruh link polosan tanpa label penjelas.
> 4. **Ringkas & Padat**:
>    - Isi `Deskripsi`, `Expected`, dan `Actual` harus langsung menusuk ke inti masalah (maksimal 1–2 kalimat per bagian).
> 5. **Aturan Langkah Reproduksi (Steps to Reproduce / STR)**:
>    - **DILARANG membuat STR jika langkahnya sedikit / pendek**: Jika masalahnya langsung muncul dalam 1–2 klik (misal: klik button Logout langsung error, klik button Export file kosong, klik button Reset field tidak tereset), **JANGAN** membuat section Steps to Reproduce. Cukup jelaskan aksinya langsung di bagian **Deskripsi**.
>    - **HANYA gunakan STR jika alurnya panjang / kompleks**: Tambahkan `* **Langkah Reproduksi**:` hanya ketika bug membutuhkan skenario bertahap lintas halaman atau multi-aksi.

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
> - **Super Ringkas & To The Point (Maksimal 1–2 kalimat saja)**, tanpa basa-basi pembuka/penutup, mudah dimengerti.
> - **Bebas Kuning-Kuning (Zero Backticks)**: DILARANG menggunakan tanda petik miring (backticks) baik pada report maupun komentar retest. Gunakan plain text biasa atau tanda kutip dua `"..."` agar tampilan bersih dan elegan tanpa badge kuning.
> - **Clickable Link**: Link bukti Catbox **WAJIB** berupa markdown link ganda `[URL](URL)` agar langsung bisa diklik di Huly.

### A. Kondisi 1: Retest Berhasil (Done)
```markdown
Retest: Done

Fitur Export pada seluruh tab Daily Sales Agenda sudah terintegrasi dengan drawer Export Center dan status export tercatat normal.

Bukti Retest:
* Daily Sales Agenda Funding: [https://files.catbox.moe/3rpt87.png](https://files.catbox.moe/3rpt87.png)
* Daily Sales Agenda Lending: [https://files.catbox.moe/6gznpn.png](https://files.catbox.moe/6gznpn.png)
```

### B. Kondisi 2: Retest Masih Ditemukan Masalah (Re-Open)
```markdown
Retest: Re-Open

Saat tombol Reset ditekan, field Fee Based, Info Bulan, dan Info Tahun belum ter-reset dan masih mempertahankan nilai sebelumnya.

Bukti Retest:
* Kondisi Filter Setelah Reset: [https://files.catbox.moe/a9ssv5.png](https://files.catbox.moe/a9ssv5.png)
```

---

## 🖼️ 5. Standar Tangkapan Layar (Screenshot) & Catbox

1. **Aturan Baku Penamaan File Screenshot Lokal (WAJIB RAPI & DESKRIPTIF):**
   * File screenshot yang disimpan ke dalam folder issue **DILARANG KERAS** dibiarkan dengan nama acak bawaan sistem/clipboard (seperti `image.png`, `Screenshot 2026-10-23.png`, `media_xxx.png`, hash UUID, atau nama acak WhatsApp/Telegram).
   * **Format Wajib:** Gunakan huruf kecil (`lowercase`), pemisah underscore (`snake_case`), diawali nomor urut 2 digit (`01`, `02`), dan sertakan kata deskriptif isi gambar:
     * **Bukti Temuan Bug Awal:**
       - Format: `evidence_[nomor]_[penjelasan_singkat].png` (atau `evidence_awal_[nomor]_[penjelasan].png`)
       - *Contoh:*
         - `evidence_01_halaman_error_logout.png`
         - `evidence_02_toast_error_validasi.png`
         - `evidence_03_response_network_500.png`
     * **Bukti Retest (Verifikasi QA):**
       - Format Retest Sukses: `retest_done_[nomor]_[penjelasan_singkat].png`
         - *Contoh:* `retest_done_01_sukses_logout.png`, `retest_done_02_data_tersimpan.png`
       - Format Retest Masih Masalah: `retest_reopen_[nomor]_[penjelasan_singkat].png`
         - *Contoh:* `retest_reopen_01_field_masih_kosong.png`

   | Status Gambar | ✅ Format Nama Rapi (Wajib Digunakan) | ❌ Contoh Nama DILARANG |
   | :--- | :--- | :--- |
   | **Bukti Awal 1** | `evidence_01_halaman_error.png` | `image.png`, `Screenshot 2026-10-23 140021.png` |
   | **Bukti Awal 2** | `evidence_02_modal_konfirmasi.png` | `media_1792736426107_75eeb5de.png` |
   | **Retest Done** | `retest_done_01_sukses_logout.png` | `ss_selesai.png`, `bukti.jpg`, `retest.png` |
   | **Retest Re-Open** | `retest_reopen_01_filter_belum_reset.png` | `error_lagi.png`, `image(1).png` |

2. **Highlight Red Box:**
   * Beri penanda kotak merah pada area yang membuktikan error (misal pesan error toast, kolom yang salah, atau data yang hilang) agar developer langsung memahami konteks masalah.
3. **Upload Otomatis ke Catbox (API cURL):**
   * Upload file screenshot ke Catbox menggunakan command cURL:
     ```bash
     curl.exe -s -F "reqtype=fileupload" -F "fileToUpload=@<path_file_gambar>" https://catbox.moe/user/api.php
     ```
   * Perintah di atas akan langsung mengembalikan URL publik (misal: `https://files.catbox.moe/abc123.png`).
4. **Format Link di Huly:**
   * Di dalam Huly, link **WAJIB** diawali label ringkas 1–2 kata dan berupa clickable markdown format ganda:
     `* {Label Singkat}: [https://files.catbox.moe/abc123.png](https://files.catbox.moe/abc123.png)`

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
   * **Tentukan Nomor (+1):** Cek folder menu di direktori laporan (`Bug Report/<Nama Menu>/`), hitung nomor issue berikutnya (+1 dari nomor terakhir, misal `01`, `02`, `03`...).
   * **Buat Folder Issue:** Buat folder dengan format `[Nomor Issue] - [Judul Singkat Masalah]`.
   * **Simpan & Upload Screenshot:**
     * **Rename Menjadi Rapi**: Ganti nama file screenshot sesuai standar Section 5 (misal: `evidence_01_halaman_error.png` atau `retest_done_01_sukses_logout.png`). **DILARANG KERAS** membiarkan nama default acak atau timestamp. Simpan ke folder issue tersebut.
     * **Upload ke Catbox**: Upload file gambar yang sudah rapi tersebut ke Catbox via cURL API (`https://catbox.moe/user/api.php`) untuk mendapatkan URL Catbox publik.
   * **Generate Dokumen Lokal (Fase 1: Issue Baru):**
     * Tulis file `report.txt` lengkap (berisi Judul, Menu, Deskripsi, Expected, Actual, dan link Catbox). **DILARANG memasukkan baris Status**.
     * Buat file `komentar_huly.txt` dalam kondisi **KOSONG** (file ini baru diisi nanti saat sesi retest).
   * **Simpan Salinan ke Obsidian (Master Tracker):**
     * Tambahkan blok issue bug tersebut ke dalam file master tracker project di Obsidian:
       `D:\Obsidian\dani\Projects\<Nama Project>\Regression Test - <Nama Project>.md` (sertakan baris `Status: Open`).
     * Update tabel rekapitulasi status jika tersedia di file tersebut.
     * Buat `git commit` di `D:\Obsidian\dani` agar riwayat perubahan aman tercatat.
4. **Sajikan ke User (Aturan Output Chat Sesuai Fase):**
   * **Saat Lapor Issue Baru**: AI **HANYA menampilkan teks `report.txt`** (dalam format markdown code block) agar User bisa langsung copy-paste ke issue baru Huly. DILARANG menampilkan komentar di fase ini!
   * **Saat Selesai Retest**: AI **HANYA menampilkan teks `komentar_huly.txt`** (dalam format markdown code block) agar User bisa langsung copy-paste ke kolom komentar Huly! Isi file `komentar_huly.txt` lokal baru di-update pada fase ini.

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
   * Selain membuat folder fisik lokal (`Bug Report/<Menu>/<No> - <Judul>/`), seluruh laporan **WAJIB dicatat salinannya** ke file master tracker di Obsidian:
     `D:\Obsidian\dani\Projects\<Nama Project>\Regression Test - <Nama Project>.md` (atau `Bug Tracker - <Nama Project>.md`).
2. **Format Salinan di Obsidian:**
   * Gunakan format blockquote standar yang seragam dengan seluruh issue sebelumnya:
     ```markdown
     ### 🐞 [BUG] | {Ringkasan Singkat Masalah (5–7 Kata)}

     > * **Menu**: {Modul} → {Sub Menu} (Tab {Nama Tab jika ada})
     > * **Status**: Open
     > * **Deskripsi**: ...
     > * **Expected**: ...
     > * **Actual**: ...
     > * **Evidence Awal**:
     >   * {Label 1-2 Kata}: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
     ```
3. **Pembaruan Hasil Retest:**
   * Saat status issue di Huly di-update (menjadi `Done`, `Re-Open`, atau `Rejected`), perbarui juga baris `> * **Status**:` dan tambahkan `> * **Bukti Retest (Done)**:` beserta link Catbox dan catatan retest di file Obsidian tersebut.
4. **Git Versioning:**
   * Lakukan commit git lokal pada vault `D:\Obsidian\dani` setiap kali selesai menambahkan atau memperbarui status issue:
     `git commit -m "docs(<project>): log new bug <No> - <Judul>"`
