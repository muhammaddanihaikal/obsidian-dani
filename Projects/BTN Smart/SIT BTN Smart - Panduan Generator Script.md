---
tags:
  - SIT
  - BTN
  - QA
  - Python
  - Script
  - Automation
date: 2026-09-17
project: BTN Smart
type: script-doc
---

# 🐍 SIT BTN Smart - Panduan Generator Script

> Script Python untuk otomatis generate dokumen Word SIT dari Excel test case.
> **Dibuat dengan**: Python + `python-docx` + `openpyxl`

---

## 📦 Dependencies

```bash
pip install python-docx openpyxl
```

---

## 📁 File Script

| Script | Path | Fungsi |
|--------|------|--------|
| **generate_all_sit.py** | `C:\Users\acer\.gemini\antigravity\brain\44771ef4-6d15-4766-8b2b-419e6887641c\scratch\generate_all_sit.py` | Generate **semua modul** Web + Mobile sekaligus |

---

## ▶️ Cara Jalankan

```bash
# Generate semua modul (Web + Mobile)
python generate_all_sit.py
```

Output akan masuk ke:
```
d:\Project\BTN\SIT\Document SIT BTN Smart\
├── Web\      → SIT-01 Login.docx, SIT-02 Profile.docx, ...
└── Mobile\   → SIT-01 Profile.docx, SIT-04 Authentication.docx, ...
```

---

## ⚙️ Konfigurasi Path (Edit Jika Diperlukan)

Di bagian atas script `generate_all_sit.py`:

```python
TEMPLATE_PATH = r'd:\Project\BTN\SIT\Form Script - Skenario SIT BTN SMART Upgrade Server.docx'
EXCEL_PATH    = r'd:\Project\BTN\SIT\Test Case.xlsx'
OUTPUT_BASE   = r'd:\Project\BTN\SIT\Document SIT BTN Smart'
```

---

## 🏗️ Arsitektur Script

```
generate_all_sit.py
│
├── load_all_modules(sheet)
│     └── Baca Excel sheet → dict {module_name: [list_of_tc_dicts]}
│
├── build_header_table()
│     └── Clone table 0 dari template
│         → Replace "Page 1" dengan PAGE field (auto-nomor halaman)
│
├── build_info_table(section_num, module_name, submenu_name, platform, count)
│     └── Clone table 1 dari template
│         → Update "Jumlah Script", "Modul", platform_name
│
├── build_data_table(test_cases, section_num)
│     └── Clone table 2 dari template (hanya header)
│         → Tambah baris baru clone dari row[1] template
│         → Set alignment per kolom (lihat tabel di bawah)
│
├── make_title_para(section_num, module_name, submenu_name, platform)
│     └── Clone "List Paragraph" style dari template
│         → Bold, numbered title
│
└── generate_doc(...)
      └── Rakit semua bagian → save .docx
```

---

## 📊 Alignment Kolom Tabel Data

| Kolom | Horizontal | Vertical |
|-------|-----------|---------|
| No | `center` | `center` |
| Test Case | `left` | `center` |
| Scenario | `left` | `top` |
| Expected Result | `left` | `top` |
| Actual Result | `left` | `top` |
| Test Status | `left` | `center` |
| Remarks | `left` | `top` |

---

## 🔑 Key Technical Notes

### 1. Multiline dalam Cell
Text dari Excel yang mengandung `\n` (Enter) diconvert menjadi **paragraf terpisah** di dalam satu cell Word, bukan literal `\n`.

```python
lines = text.split('\n')
# Setiap line → paragraph baru dalam tc_elem
```

### 2. PAGE Field (Auto Nomor Halaman)
Menggunakan Word field `PAGE` (bukan hardcode):

```python
# Struktur XML:
# <w:fldChar w:fldCharType="begin"/>
# <w:instrText> PAGE </w:instrText>
# <w:fldChar w:fldCharType="separate"/>
# <w:t>1</w:t>  ← display fallback
# <w:fldChar w:fldCharType="end"/>
```

### 3. Clone Row dari Template
Setiap baris data adalah `deepcopy` dari `template_data_row._tr` (row ke-1 table 2 di template), sehingga format border, font, dan lebar kolom tetap terjaga.

### 4. Submenu Logic
```python
def get_module_submenu_label(rows):
    submenus = set(r['submenu'] for r in rows)
    if len(submenus) == 1:
        return list(submenus)[0]  # semua sama → pakai itu
    return None  # mixed/multiple → tidak pakai submenu di judul
```

---

## 🔄 Cara Re-generate (Jika Excel Berubah)

1. Update file Excel: `d:\Project\BTN\SIT\Test Case.xlsx`
2. Jalankan kembali script
3. File lama akan **tertimpa** (overwrite)

> [!WARNING]
> File output yang sudah diisi Actual Result/Test Status akan **tertimpa** jika script dijalankan ulang.
> Backup dulu hasil yang sudah diisi sebelum re-generate!

---

---

## 🏛️ Standar Revisi Dokumen SIT (Hasil Review Senior)

Berdasarkan review senior (21 September 2026), terdapat 5 aturan baru yang wajib diterapkan pada dokumen SIT:

1. **Pembagian per Sub Menu (Bukan cuma per Modul):**
   - Format heading: `Modul [Nama Modul] - [Nama Sub Menu]`
   - Jika modul tidak memiliki sub menu (misal: Login, Profile, Menu Target, List Prospek ETB), judul tetap `Modul [Nama Modul]`.
   - Menghasilkan 75 seksi tabel terpisah yang modular dan mudah dibaca.
2. **Hapus Semua TC "Menampilkan Daftar":**
   - Semua TC redundan yang fungsinya hanya menampilkan daftar data langsung setelah membuka halaman dihapus dari SIT.
3. **Semua Cell Tabel Rata Tengah (Center):**
   - Semua kolom (No, Test Case, Scenario, Expected, Actual, Status, Remarks) wajib diset rata tengah secara horizontal (`jc='center'`) dan vertikal (`vAlign='center'`).
4. **Penomoran Langkah & Expected Result (Pemisahan Standar SIT vs Excel/Screenshot):**
   - **Di Dokumen Word SIT**: Generator script otomatis membersihkan penomoran `1. `, `2. ` (`clean_no_numbers`) agar tabel SIT tampil ringkas sesuai format review senior.
   - **Di Excel & File `.txt` Screenshot**: Tetap mempertahankan penomoran lengkap `1. `, `2. ` dari Excel asli agar menjadi panduan runtut dan jelas bagi tim tester saat mengambil bukti screenshot.
5. **Sinkronisasi Info Table (Table 1):**
   - Field `Jumlah Script` wajib akurat mencerminkan total baris TC yang ada (921 TC).
   - Field `Modul :` memuat daftar seluruh 75 Sub Menu dengan bullet point (`w:numId=2`) bawaan template Word.
   - Row 2 Cell 0 wajib dibersihkan agar teks tidak muncul ganda pada sel yang dimerge.
6. **Penomoran Judul Seksi (Manual Numbering, Mencegah Tab Stop Melompat):**
   - Auto-numbering Word bawaan template (`w:numPr numId=1`) memiliki tab stop di 678 dxa. Untuk nomor 2 digit (10 s.d. 75), lebar angka font 20pt melampaui tab stop 678 dxa sehingga Word otomatis melompat ke default tab stop berikutnya (1440 dxa), menyebabkan jarak spasi jadi sangat renggang (`10.       Modul ...`).
   - **Solusi**: Hapus elemen `w:numPr` dan `w:tabs` dari paragraph heading di `build_title_para`, lalu masukkan penomoran langsung ke dalam teks `f"{sec_idx}. Modul {module_name} - {submenu_name}"` dengan indent `<w:ind w:left="259" w:hanging="0"/>`. Jarak setelah titik menjadi 1 spasi konsisten dari nomor 1 sampai 75 (`10. Modul ...`).
7. **Modul Login Tetap Digabung (General / Tidak Mengikuti Pemisahan Tipe):**
   - Skenario pengujian Modul Login dipertahankan sebagai flow umum gabungan (`Membuka halaman Login`, `Melakukan login dengan kredensial valid`, dll.), bukan dikhususkan per tipe akun seperti *"Non Employee"*.
   - Excel (`Test Case.xlsx` sheet `TC BTN SMART Web`) dan dokumen Word (`SIT BTN SMART Web.docx`) kini 100% sinkron dan paralel memuat **921 Test Case** di dalam **75 Sub Menu**.

8. **Penomoran Baris Tabel Wajib Mengikuti Nomor Judul Seksi (`sec_idx.tc_idx`):**
   - Kolom `No` pada tabel mengikuti format `{nomor_seksi}.{nomor_tc_dalam_seksi}`. Contoh: Seksi 4 (`4. Modul Overview - Overview Lend`) barisnya adalah `4.1` s.d. `4.5`; Seksi 6 (`6. Modul User Authority - User`) adalah `6.1` s.d. `6.9`; Seksi 10 (`10. Modul User Authority - Keamanan Akun`) adalah `10.1` s.d. `10.37`.
9. **Eliminasi Halaman Kosong (Clean Page Breaks Tanpa Blank Page):**
   - Tidak menggunakan trailing `empty_para()` setelah tabel atau manual `page_break_para()`.
   - Menggunakan `<w:pageBreakBefore/>` pada elemen `pPr` judul seksi untuk `sec_idx > 1`.
   - Paragraf pemisah section break (`p_break`) dan trailing paragraph akhir dibuat `zero_height_para` (spacing 0, font size 2 dxa) agar tidak menyebabkan overflow halaman kosong baru saat tabel selesai di ujung bawah halaman.
10. **Sinkronisasi Folder Screenshot per Sub Menu (75 Sub Menu & 921 TC):**
    - Folder screenshot di Local (`d:\Project\BTN\Hasil Uji\Screenshot\Web`) dan Google Drive (`H:\My Drive\Zegen\BTN Smart\Refactor\Hasil Uji\Screenshot\Web`) disusun per sub menu: `01. Login` s.d. `75. Export data management - Persetujuan export`.
    - Di dalamnya terdapat folder per TC: `{sec_idx}.{tc_idx} {tc_title}` lengkap dengan file `.txt` deskripsi langkah pengujian & expected result.
    - Screenshot tester dipetakan dan dipindahkan ke nomor baris baru (5 gambar modul User tersimpan aman di `06. User Authority - User/6.1`, `6.2`, dan `6.4`).

---

## 🔗 Catatan Terkait

- [[SIT BTN Smart - Overview]]
- [[SIT BTN Smart - Format & Aturan Dokumen]]
- [[Hasil Uji BTN Smart - Panduan Generator & Siklus Uji]]

