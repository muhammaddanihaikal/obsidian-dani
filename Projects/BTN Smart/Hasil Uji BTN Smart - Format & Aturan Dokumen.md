---
tags:
  - SIT
  - UAT
  - BTN
  - QA
  - Format
  - Word
  - HasilUji
date: 2026-09-18
project: BTN Smart
type: standard
---

# 📄 Hasil Uji BTN Smart - Format & Aturan Dokumen Word

> Standar format dokumen Word Hasil Uji yang digunakan untuk **BTN SMART**.
> Di-generate secara otomatis menggunakan script Python berbasis struktur folder Google Drive.

---

## 📐 Layout Halaman

| Property | Value |
|---|---|
| **Orientasi** | Portrait |
| **Ukuran Kertas** | A4 (21.01 cm × 29.7 cm) |
| **Margin Atas** | 1.48 cm |
| **Margin Bawah** | 0.49 cm |
| **Margin Kiri** | 1.55 cm |
| **Margin Kanan** | 0.35 cm |

---

## 🗂️ Struktur Dokumen Keseluruhan

```
Cover Page
├── Table 0 - Informasi Dokumen (6 baris × 2 kolom)
├── Table 1 - Penandatangan Penyedia Jasa (5 baris × 4 kolom)
├── Table 2 - Diketahui Oleh BTN (4 baris × 1 kolom)
└── Table 3 - Histori Perbaikan (2 baris × 5 kolom)

Isi (per Modul)
├── Heading 1: "Modul [Nama Modul]"
├── Paragraf kosong
├── TC Table PERTAMA (4 baris: header + judul + ss + expected)
├── TC Table KEDUA (3 baris: tanpa header row)
└── ... dst
```

> **Pola kunci:** TC **pertama** per modul punya **header row biru**. TC berikutnya **tidak punya header row** (langsung data).

---

## 📌 Struktur Tiap TC Table

### TC Pertama Per Modul — 4 Rows

| Row | Isi | BG Color | Style |
|---|---|---|---|
| Row 0 (Header) | `No.` / `User Acceptance Testing (UAT)` | `2C5293` (biru tua) | Bold, White, Center |
| Row 1 (Judul TC) | `1.1` / `[Judul TC]` | `D0CECE` (abu-abu) | Normal, Hitam |
| Row 2 (Screenshot) | kosong / gambar | None (putih) | Center (gambar) |
| Row 3 (Expected) | kosong / teks expected | None (putih) | Lihat di bawah |

### TC Kedua dst — 3 Rows (tanpa header)

| Row | Isi |
|---|---|
| Row 0 (Judul TC) | `1.2` / `[Judul TC]` — bg abu D0CECE |
| Row 1 (Screenshot) | gambar — putih |
| Row 2 (Expected) | teks expected — putih |

---

## 🎨 Styling Detail

### Warna
| Elemen | HEX | Keterangan |
|---|---|---|
| Header row bg | `2C5293` | Biru tua |
| Judul TC row bg | `D0CECE` | Abu-abu muda |
| Teks header | `FFFFFF` | Putih |
| Teks No / Judul TC | `000000` | Hitam |
| `"Hasil yang diharapkan [STATUS]:"` | `000000` | Hitam Bold |
| Expected result content | `2C5293` | Biru |

### Font
- **Font family**: Arial (semua elemen)
- **Ukuran**: 10pt (127000 EMU)
- Header row: **Bold**
- Judul TC: Normal
- `"Hasil yang diharapkan [STATUS]:"`: **Bold**
- Expected result content: Normal, warna biru `2C5293`

### Spacing (space_before per paragraf)
- Header row & Judul TC: `5.8pt`
- Screenshot row: `5.8pt`
- `"Hasil yang diharapkan [STATUS]:"`: `5.8pt`
- Expected result content: `6.5pt`

### ⚠️ Aturan Teks "Hasil yang diharapkan [STATUS]:"
- **Sumber Teks Baku**: **WAJIB mengambil teks dari dokumen SIT secara langsung** (berupa ringkasan / 1 kalimat narasi utuh dari SIT).
- **❌ DILARANG KERAS menggunakan penomoran (`1. 2. 3. ...`)** pada cell Hasil yang diharapkan di Dokumen Word!
  - Penomoran `1. 2. 3.` hanya berlaku untuk file panduan `.txt` dan Test Script.
  - Di Dokumen Hasil Uji Word, teks harus mengalir rapi dalam 1 paragraf sesuai template baku BTN.
- **❌ DILARANG double enter / baris kosong acak**:
  - Teks tidak boleh diselingi baris kosong atau enter yang tidak konsisten.
  - Spacing paragraf: Space Before `5.8pt` (label) dan `6.5pt` (isi narasi).
- **🎨 Standardisasi Warna & Gaya Font (Wajib Konsisten)**:
  - **Label** `"Hasil yang diharapkan [STATUS]:"`: Arial 10pt, **Hitam (`#000000`)**, **Bold**.
  - **Isi Narasi SIT**: Arial 10pt, **Biru BTN (`#2C5293`)**, **Normal / Regular** (Wajib biru, dilarang hitam atau abu-abu).
  - **Tag Status Akhir** (` - [Success]` / ` - [Failed]`): Arial 10pt, **Biru BTN (`#2C5293`)**, **Normal / Regular (JANGAN TEBAL / BUKAN BOLD)**. Seluruh kalimat narasi dan status mengalir seragam tanpa ada font tebal.
- **Contoh Format Baku**:
  > **Hasil yang diharapkan [Success]:**
  > Sistem berhasil menampilkan daftar data pengguna pada tabel User Authority. - [Success]

---

## 🟥 Standar Kotak Merah (Red Bounding Box)

Untuk memperjelas bukti verifikasi pada elemen UI yang diuji:
1. **Spesifikasi Teknis Garis**:
   - **Warna**: Pure Red (`#FF0000` / RGB `(255, 0, 0)`).
   - **Ketebalan (Stroke)**: `3px` solid.
   - **Padding**: Wajib memberi ruang napas yang cukup (padding horizontal `8 - 10px`, vertikal `4 - 6px` dari batas teks/elemen) agar tidak sempit dan garis merah tidak menempel pada teks.
   - **Kualitas Gambar**: Wajib diproses secara **Lossless PNG** (tanpa kompresi lossy JPEG).

2. **Elemen yang Wajib Diberi Kotak Merah**:
   - **Sidebar Menu & Submenu (TC .1)**: Kotak merah pada parent menu yang aktif dan submenu yang sedang dibuka.
   - **Form Pencarian / Filter**: Kotak merah pada search bar/dropdown filter dan tombol cari/submit.
   - **Tombol Aksi Utama**: Tombol aksi yang menjadi fokus pengujian (misal: `Update`, `Simpan`, `Tambah`, `Hapus`, `Export`).
   - **Pesan Validasi & Error Alert**: Tulisan pesan error validasi merah di bawah input textbox serta banner alert error.
   - **Modal Dialog / Pop-up**: Jendela/card modal dialog yang muncul di tengah layar sebagai bukti verifikasi.

---

## ✂️ Standar Pemotongan UI Web (Web Crop Rules)

Standar klasifikasi dan pemotongan screenshot UI Web agar bukti hasil uji tetap utuh konteksnya dan tabel/data ter-zoom maksimal di Word:

1. **Aturan 1: Halaman Awal / TC Pembuka (`.1`, misal `6.1`, `7.1`)**
   - **Tindakan:** **FULL SCREEN** (`0, 0, w, h` - tidak dipotong sama sekali).
   - **Alasan:** Sebagai penanda modul & menu utama yang sedang diakses di sidebar.
2. **Aturan 2: Ada Notifikasi (Alert / Toast di Kanan Atas)**
   - **Tindakan:** Hapus Sidebar saja (`x = 338px` atau `x = 80px`). Navbar atas **TETAP ADA** (`y = 0`).
   - **Alasan:** Menjaga agar pop-up banner notifikasi sukses/gagal di pojok kanan atas tidak terpotong.
3. **Aturan 3: Drawer / Filter dari Samping Kanan**
   - **Tindakan:** Hapus Sidebar saja. Navbar atas **TETAP ADA** (`y = 0`).
   - **Alasan:** Menjaga struktur visual dan proporsi panel drawer samping kanan.
4. **Aturan 4: Drawer dari Bawah**
   - **Tindakan:** Hapus Navbar saja (`y = 72px`). Sidebar **TETAP ADA** (`x = 0`).
   - **Alasan:** Drawer bawah memanjang horizontal, butuh sidebar sebagai penyeimbang layout.
5. **Aturan 5: Sidebar Diperkecil (Minimized / Collapsed Sidebar ~80px)**
   - **Tindakan:** Sidebar ikon kecil dapat dihapus (`x = 80px`) selama tidak melanggar aturan 1 s/d 4.
6. **Aturan 6: Pop-up / Modal Dialog di Tengah Layar**
   - **Tindakan:** Bisa Hapus Sidebar saja (`y = 0`), atau Hapus Sidebar & Navbar (Full Body Crop `y = 72px`) jika proporsional dan tidak memotong bagian atas dialog modal.
   - **Alasan:** Menjaga agar jendela dialog modal tetap simetris di tengah.
7. **Aturan 7: Halaman Tabel / Data / Form Normal (Kondisi Default)**
   - **Tindakan:** **Full Body Crop** (Hapus Sidebar `x = 338px`/`80px` dan Navbar `y = 72px`).
   - **Alasan:** Area tabel dan form ter-zoom maksimal sehingga data mudah dibaca jelas di dokumen Word.
8. **Aturan 8: Menu / Tabel Vertikal Sangat Panjang (Stitching Atas & Bawah)**
   - **Tindakan:** Potong bagian tengah yang kosong/berulang, lalu gabungkan (stitch) bagian atas dan bagian bawah secara seamless tanpa menurunkan resolusi piksel.
   - **Alasan:** Menghindari gambar yang terlalu panjang/tinggi di dokumen Word tanpa menghilangkan header dan tombol aksi penting di bawah.
9. **Aturan 9: Scrollbar Tepi Kanan (Vertical Browser Scrollbar)**
   - **Tindakan:** Potong (trim) tepi kanan sebesar `14 - 15px` di mana batang abu-abu scrollbar berada.
   - **Alasan:** Menghilangkan artefak scrollbar browser yang mengganggu, membuat padding margin kanan simetris (~20px) dengan margin kiri (~20px), serta menjaga dokumen hasil uji tampak clean dan profesional tanpa memotong tombol aksi (+ Tambah, Export) atau ikon filter di kanan.

> [!CAUTION] 🚨 ATURAN MUTLAK KETIKA RAGU
> Jika script AI bingung atau ragu dalam mengklasifikasikan gambar tertentu (misal tata letak UI tidak biasa atau tumpang tindih), **DILARANG LANGSUNG MEMOTONG**. AI wajib memberikan **Report Klasifikasi / List Gambar** dan meminta **ACC** ke Mas Dani terlebih dahulu sebelum eksekusi pemotongan dilakukan.

---

## 🖼️ Gambar Screenshot

- **Tipe**: Inline image
- **Alignment**: CENTER dalam cell
- **Target lebar maks**: `15.0 cm` (5.400.000 EMU)
- **Tinggi**: Proporsional otomatis sesuai aspek rasio gambar asli

### 📸 Aturan Khusus Screenshot Fitur Filter
- **Filter Inline (Mobile/Web):** Jika filter dan data berada dalam satu layar yang sama, gunakan **2 screenshot (Before & After)**:
  1. `01.png`: Tampilan sebelum filter (kondisi default / form filter kosong).
  2. `02.png`: Tampilan setelah filter dipilih dan data berhasil tersaring.
  - Tujuannya memberikan bukti visual kontras dan otentik bahwa penyaringan data benar-benar berfungsi.

---

## 📊 Ukuran Kolom

| Kolom | Lebar (dxa) | ≈ cm |
|---|---|---|
| Col 0 (No.) | 709 dxa | ~1.25 cm |
| Col 1 (Content) | 9084 dxa | ~16.0 cm |
| **Total** | **9793 dxa** | **~17.25 cm** |

---

## 🔲 Border Tabel

- Style: `single`, sz: `4` (0.5pt), warna: `000000`
- Berlaku untuk semua sisi: top, left, bottom, right, insideH, insideV

---

## 🏷️ Heading 1

- Style name: `Heading 1`
- Format teks: `"Modul [Nama Modul]"`
- Space before: `1.8pt`

---

## 🔗 Referensi Terkait
- [[Hasil Uji BTN Smart - Panduan Generator & Siklus Uji]] — Panduan SOP perubahan TC, script sinkronisasi, dan troubleshooting teknis.
