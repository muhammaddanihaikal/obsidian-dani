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

## 🔮 Fitur Tambahan yang Bisa Dikembangkan

- [ ] **Merge semua modul** → 1 file per platform (Web all-in-one / Mobile all-in-one)
- [ ] **Update selective** → re-generate modul tertentu saja tanpa overwrite semua
- [ ] **Numbering halaman global** → Page 1 of N (butuh post-processing atau merge)
- [ ] **Warna baris alternating** → zebra striping untuk readability

---

## 🔗 Catatan Terkait

- [[SIT BTN Smart - Overview]]
- [[SIT BTN Smart - Format & Aturan Dokumen]]
