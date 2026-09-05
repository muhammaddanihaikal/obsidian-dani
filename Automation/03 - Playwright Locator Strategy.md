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

## 6. Container Scoping (Bilik Terkecil) ⭐ Teknik Paling Penting!

Ini adalah strategi **paling umum dan paling stabil** saat berhadapan dengan form/filter yang field-fieldnya susah dibedakan.

### Analogi:
Bayangkan sebuah form sebagai **Ruang Kantor Bersama**. Di ruangan itu ada 4 meja (field). Kalau kita bilang *"tolong isi kotak yang ada di ruangan ini"*, Playwright bingung karena ada 4 kotak. **Solusinya: Kunci dulu ke bilik/meja spesifiknya, baru cari input di dalamnya.**

### Kapan Pakai Ini?
Saat `page.get_by_label()` tidak bisa dipakai (artinya developer tidak menghubungkan `<label>` dan `<input>` secara proper di HTML, seperti di OrangeHRM).

### Cara Kerjanya:
```python
# 1. Definisikan wadah bilik (wrapper terkecil per field)
self.field_container = page.locator(".oxd-input-group")  # atau .oxd-grid-item

# 2. Kunci ke bilik spesifik, lalu ambil input di dalamnya
self.username_filter = self.field_container.filter(has_text="Username").get_by_role("textbox")
self.user_role_filter = self.field_container.filter(has_text="User Role").locator(".oxd-select-text")
```

### Cara Membaca Locator (Kiri ke Kanan):
`self.field_container.filter(has_text="User Role").locator(".oxd-select-text")`
1. `self.field_container` ➜ *"Kumpulkan SEMUA bilik yang ada di halaman."*
2. `.filter(has_text="User Role")` ➜ *"Saring, ambil HANYA bilik yang ada tulisan 'User Role'."*
3. `.locator(".oxd-select-text")` ➜ *"Di DALAM bilik itu, ambil dropdown-nya."*

### Cara Menemukan Class Wrapper di Browser:
1. Klik kanan elemen input ➜ **Inspect**.
2. Di tab Elements, **gerakkan mata ke atas** (lihat elemen *parent*-nya).
3. Berhenti saat menemukan elemen yang membungkus **sekaligus label + input** dalam 1 kotak kecil.
4. Catat class-nya (misal `oxd-input-group`, `oxd-grid-item`). Itulah bilik-nya!

### Keuntungan vs Pakai Form Container Besar:
| | Form Container Besar | Bilik Terkecil ✅ |
|---|---|---|
| Berisi | Semua field (5 textbox, 3 dropdown) | 1 label + 1 input |
| Risiko | Strict Mode Error karena banyak elemen kembar | Dijamin unik, tidak mungkin salah sasaran |
| Kegunaan Tambahan | - | Bisa cek error message spesifik per field |

---

## 7. `to_have_count()` — Assertion untuk Elemen Kembar

Dipakai saat kita ingin memastikan **jumlah** elemen yang muncul, bukan cuma 1 elemen.

```python
# Pastikan ada tepat 5 pesan error "Required" (karena ada 5 field yang wajib diisi)
expect(page.get_by_text("Required", exact=True)).to_have_count(5)
```

**Perbedaan dengan `to_be_visible()`:**
- `to_be_visible()` ➜ Dipakai kalau elemen yang dimaksud **hanya ada 1** di layar.
- `to_have_count(N)` ➜ Dipakai kalau elemen **ada banyak / kembar** dan kita ingin memastikan jumlahnya.

Kalau pakai `to_be_visible()` pada elemen yang ternyata ada 5 buah, Playwright akan *crash* karena **Strict Mode Error** (tidak tahu harus ngecek yang mana).

---

## Tips Penting
- **Prioritaskan `get_by_label()`** — paling ideal kalau developer membuat HTML yang accessible.
- Kalau `get_by_label()` nggak ada, pakai teknik **Bilik Terkecil** (Container Scoping).
- **Jangan pakai `nth()`** sebagai locator utama — rapuh dan mudah berubah kalau layout berubah.
- Kalau nemu **Strict Mode Error** di assertion, ganti `to_be_visible()` ➜ `to_have_count(N)`.
