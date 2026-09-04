---
tags:
  - QA
  - Automation
  - Playwright
  - Locator
date: 2026-08-31
---
# 🔍 Playwright Locator Strategy

Locator adalah cara kita "menunjuk" elemen HTML di halaman web supaya Playwright tahu elemen mana yang harus diklik, diisi, atau dicek.

## Strategi Locator yang Sudah Dipelajari

### 1. `get_by_role()` — Cari berdasarkan peran elemen
Paling direkomendasikan karena mirip cara user melihat halaman.
`python
page.get_by_role("textbox", name="Username")   # Input text berlabel Username
page.get_by_role("button", name="Login")        # Tombol bertulisan Login
page.get_by_role("heading", name="Dashboard")   # Judul halaman Dashboard
page.get_by_role("link", name="Admin")           # Link bertulisan Admin
page.get_by_role("alert")                        # Elemen dengan role alert
page.get_by_role("option", name="ESS")           # Option dropdown bertulisan ESS
page.get_by_role("checkbox", name="Yes")         # Checkbox bertulisan Yes
`

### 2. `locator()` — Cari pakai CSS selector
Dipakai kalau `get_by_role()` nggak bisa nemuin elemen yang kita mau.
`python
page.locator(".oxd-input-group")     # Cari by class CSS
page.locator("i.bi-pencil-fill")     # Cari icon edit (tag <i> + class)
page.locator("i.bi-trash")           # Cari icon delete
page.locator(".oxd-select-text")     # Cari dropdown custom
page.locator("div")                  # Cari semua elemen <div>
`

### 3. `.filter()` — Saring hasil pencarian
Kalau locator nemuin banyak elemen yang mirip, pakai filter untuk mempersempit.

#### `filter(has_text=)` — Saring yang punya teks tertentu
`python
# Dari semua .oxd-input-group, ambil yang ada tulisan "User Role"
page.locator(".oxd-input-group").filter(has_text="User Role")

# Dari semua span, ambil yang tulisannya "Required"
page.locator("span").filter(has_text="Required")
`

#### `filter(has=)` — Saring yang punya child element tertentu
`python
# Dari semua button di row ini, ambil yang di dalamnya ada icon pensil
row.get_by_role("button").filter(has=page.locator("i.bi-pencil-fill"))
`

### 4. Pemilih Urutan — Pilih dari sekumpulan elemen kembar
Kalau elemen yang ditemukan lebih dari satu (kembar), Playwright bakal error (Strict Mode). Solusinya:

| Pemilih | Artinya | Contoh |
|---|---|---|
| `.first` | Ambil yang pertama/paling atas | `locator("div").first` |
| `.last` | Ambil yang terakhir/paling bawah | `locator("div").last` |
| `.nth(index)` | Ambil urutan ke-N (mulai dari 0) | `.get_by_role("cell").nth(2)` = cell ke-3 |

### 5. `get_by_text()` — Cari berdasarkan teks
`python
page.get_by_text("Searching....", exact=True)   # Cari teks persis "Searching...."
page.get_by_text("Password", exact=True)         # exact=True = harus persis, bukan "mengandung"
`

## Chaining (Merangkai Locator)
Locator bisa dirangkai seperti rantai untuk makin spesifik:
`python
# Cara bacanya dari kiri ke kanan:
# 1. Cari semua .oxd-input-group
# 2. Saring yang ada tulisan "Employee Name"
# 3. Dari hasil saringan itu, cari listbox di dalamnya
# 4. Dari listbox itu, cari div di dalamnya
self.field_container.filter(has_text="Employee Name").get_by_role("listbox").locator("div")
`

## Tips Penting
- **Prioritaskan `get_by_role()`** — paling stabil dan paling mirip cara user berinteraksi.
- Kalau `get_by_role()` nggak cukup, baru pakai `locator()` + `.filter()`.
- Kalau nemu error **Strict Mode**, gunakan `.first`, `.last`, atau `.nth()`.
