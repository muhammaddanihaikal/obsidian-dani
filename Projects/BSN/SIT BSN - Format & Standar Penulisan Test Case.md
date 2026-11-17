---
tags:
  - SIT
  - BSN
  - QA
  - TestCase
  - Standard
date: 2026-11-17
project: BSN Lelang & Aset Baru
type: standard
---

# 📋 SIT BSN - Format & Standar Penulisan Test Case (`Script Test BSN .xlsx`)

> Panduan baku pembuatan dan pembaruan Script Test Case SIT untuk project **BSN (Internal, External, & Portal Developer)**.
> File Master Excel: `D:\Project\BSN\Fase 1\SIT\Script Test BSN .xlsx`

---

## 1. Struktur Workbook & Sheet

Workbook `Script Test BSN .xlsx` terdiri dari **3 sheet utama** mengikuti portal aplikasi:
1. **`Script Internal`** — Admin BSN (`Terasrumah Admin`)
2. **`Script External`** — User / Pembeli publik
3. **`Script Portal Developer`** — Mitra Developer

### Kolom Wajib (9 Kolom Berurutan)
| Kolom | Header | Aturan Isi |
| :---: | :--- | :--- |
| **A** | `No` | Nomor urut modul (`1`, `2`, `3`, ...), di-**merge vertikal** per Menu |
| **B** | `Menu` | Nama menu utama, di-**merge vertikal** per Menu |
| **C** | `Sub Menu` | Nama sub-menu (di-**merge vertikal** per Sub Menu; kosong + di-merge jika Menu tidak punya Sub Menu) |
| **D** | `Test Case` | Judul Test Case dengan kata kerja aktif **`Me-`** |
| **E** | `Scenario` | Langkah pengguna yang singkat & mengikuti **2 Rumus Tim** |
| **F** | `Expected Result` | Hasil yang diharapkan (**tepat 1 kalimat**) |
| **G** | `Actual Result` | **Kosongkan** (diisi saat eksekusi SIT) |
| **H** | `Test Status \n( P = Passed, F = Failed )` | **Kosongkan** (diisi saat eksekusi SIT) |
| **I** | `Remark` | **Kosongkan** |

---

## 2. Aturan Judul (`Test Case`)

* Wajib diawali **kata kerja aktif `Me-`**:
  * `Membuka ...`, `Memilih ...`, `Mencari ...`, `Memfilter ...`, `Mereset ...`, `Menambahkan ...`, `Mengubah ...`, `Melihat ...`, `Menghapus ...`, `Menyetujui ...`, `Menolak ...`, `Mengunduh ...`, `Mengunggah ...`, `Mengajukan ...`, `Menyimpan ...`
* **Simple, natural, dan bebas kata mubazir** (hindari pengulangan nama halaman di setiap judul jika kolom `Sub Menu` sudah jelas).
* Contoh bagus:
  * `Membuka halaman List Developer`
  * `Mencari developer dengan keyword sesuai`
  * `Menambahkan mitra developer baru`
  * `Menyetujui pengajuan mitra developer`

---

## 3. Aturan Penulisan `Scenario` (Pola Asli Tim BSN)

Penulisan `Scenario` mengikuti **2 rumus** berdasarkan jenis aksinya:

### A. Aksi Langsung → **1 Baris Horizontal dengan ` - `**
Berlaku untuk: *Buka halaman, Klik tab, Search, Filter, Reset Filter, Download, Detail, Edit/Approve singkat*.

* **Buka halaman (TC #1)**: `Klik menu <Menu> - Klik sub menu <Sub Menu>` *(TC #2 ke bawah jangan mengulang langkah navigasi ini)*.
* **Tab status**: `Klik tab status selain Semua` *(atau sebut nama tabnya, misal `Klik tab Menunggu Approval, Disetujui, atau Ditolak`)*.
* **Search valid**: `Input <objek pencarian>` *(+ `- Klik button Cari` / `- Klik button Terapkan` jika ada tombolnya)*.
* **Search tidak valid**: `Input kata kunci tidak ada pada list` *(+ `- Klik button Cari` jika ada)*.
* **Filter sesuai**: `Pilih <filter 1> - Pilih <filter 2>` *(+ tombol terapkan/cari jika ada)*.
* **Filter tidak sesuai**: `Pilih filter yang tidak sesuai` *(+ tombol terapkan/cari jika ada)*.
* **Reset filter**: `Klik button Reset` / `Klik button Atur Ulang`.
* **Detail / Download / Approve Tabel**: `Klik button Detail`, `Klik button Unduh Laporan`, `Klik button Setujui - Klik button Setujui pada pop up`.

### B. Form Panjang / Multi-Step → **Poin Vertikal `- ...` (2–4 Kata per Baris)**
Berlaku untuk: *Wizard Step 1–6, Create Developer, Tindak Lanjut Leads, Pengurangan Stok, Ubah Profil/Sandi*.

* Tetap jabarkan ke bawah per poin `- ...`, namun **tiap baris cukup 2–4 kata sehari-hari** (tanpa label UI panjang/kaku, tanpa `/`, tanpa `(opsional)`, dan tanpa menumpuk banyak field dalam 1 kalimat).

```text
- Klik button + Input Aset Baru
- Pilih developer
- Pilih tipe aset
- Pilih proyek
- Pilih klaster
- Input stok unit
- Klik button Selanjutnya
```

---

## 4. Aturan `Expected Result`

* Wajib **tepat 1 kalimat** per Test Case.
* Awali dengan **`Berhasil ...`** untuk skenario sukses, atau **`Menampilkan ...`** untuk kondisi kosong (*empty state*) pada Search & Filter.
* Ringkas tanpa mendaftar puluhan detail kecil di UI.
* Contoh:
  * `Berhasil menampilkan halaman Daftar Mitra Developer Terdaftar beserta summary card dan tabel data`
  * `Menampilkan tabel kosong dengan keterangan data tidak ditemukan`
  * `Berhasil menyetujui pengajuan developer dan mengubah status menjadi Disetujui`

---

## 5. Cakupan & Batasan Test Case (Scope Rules)

1. **Zero Negative Case (Kecuali Search & Filter)**:
   * Jangan membuat negative case untuk validasi field wajib/kosong, format file, ukuran file, atau karakter password — kecuali diminta khusus.
   * Negative case hanya dibuat untuk **Search** (`keyword tidak valid` / `tidak ada pada list`) dan **Filter** (`kombinasi filter tidak sesuai`).
2. **Jangan Buat TC untuk**:
   * **Pagination** (baris per halaman / next-prev).
   * Interaksi mikro tidak krusial (misal copy-to-clipboard CIF, clear search kecil, tooltip, atau search sekunder di dalam tab detail).
   * Mengklik tab default saat halaman pertama dibuka (`Cukup 1 TC` pindah ke tab selain default).
3. **Jika Fitur Belum Ada / Masih Kosong di UI**:
   * Misal bagian dokumen masih kosong (`Belum ada dokumen...`) dan belum ada alur unggahnya, hindari membuat TC yang rawan tidak bisa dites saat SIT.

---

## 6. Aturan Keamanan Data & Kolaborasi Tim

1. **Jangan Sentuh Pekerjaan Tim**:
   * Saat menambah atau merapikan script milik sendiri, **dilarang mengubah isi baris milik tim**.
   * Saat menggabungkan sheet/menu baru dari file teman (misal `Script Test BSN 1.xlsx` → `Media & Informasi`), salin **100% utuh apa adanya (as-is)** tanpa mengedit typo atau format tulisannya.
2. **Workflow Perubahan Excel yang Aman**:
   * Selalu buat **backup `.xlsx`** sebelum melakukan edit.
   * Gunakan **Excel COM automation** (`Insert(-4121)`, `Merge()`, `WrapText = True`, `AutoFit()`) agar *merged cells*, border, dan styling sheet tidak rusak (hindari menyalin range yang sedang di-merge ke sel lain karena memicu merge bertumpuk).
   * Setelah selesai, selalu jalankan **verifikasi XML diff** terhadap file backup untuk memastikan **0 perubahan tidak disengaja** pada baris tim maupun sheet lain.
