---
tags:
  - QA
  - Automation
  - Playwright
  - WaitFor
date: 2026-08-31
---
# ⏳ Playwright Waiting Strategy

Salah satu tantangan terbesar di automation testing adalah **timing**. Elemen di halaman web nggak langsung muncul, kadang perlu loading dulu. Kalau test kita terlalu cepat ngecek, pasti gagal. Kalau nunggu terlalu lama, test jadi lambat.

## 1. `wait_for()` — Tunggu elemen berubah state
Dipakai kalau kita perlu nunggu elemen muncul atau menghilang.

`python
# Tunggu teks "Searching...." MENGHILANG (artinya loading selesai)
page.get_by_text("Searching....", exact=True).wait_for(state="hidden")

# Tunggu dropdown option MUNCUL (artinya data udah ke-load)
self.employee_options.first.wait_for(state="visible")
`

| State | Artinya |
|---|---|
| `"visible"` | Tunggu sampai elemen MUNCUL di layar |
| `"hidden"` | Tunggu sampai elemen MENGHILANG dari layar |

### Contoh Kasus Nyata (Dropdown Employee Name)
`python
# 1. Ketik keyword di textbox
self.employee_name.fill(data["employee_keyword"])

# 2. Tunggu teks "Searching...." hilang (loading selesai)
page.get_by_text("Searching....", exact=True).wait_for(state="hidden")

# 3. Tunggu option pertama muncul
self.employee_options.first.wait_for(state="visible")

# 4. Baru klik option-nya
self.employee_options.first.click()
`

## 2. `expect_response()` — Tunggu API selesai merespon
Dipakai kalau kita perlu nunggu server selesai memproses request (misal: login, save data).

`python
# Pasang "jebakan" API dulu, baru klik tombol
with page.expect_response("**/auth/validate"):
    login_page.login(data["username"], data["password"])

# Baris ini baru jalan SETELAH server membalas
expect(login_page.error_message).to_be_visible()
`

### Kenapa Harus Pakai `with`?
Karena `with` memastikan Playwright **pasang posisi duluan** sebelum aksi dilakukan. Kalau nggak pakai `with`, bisa jadi respon server udah lewat sebelum Playwright sempat menangkapnya.

### Pola URL: `**`
`"**/auth/validate"` artinya:
- `**` = nggak peduli domain/URL depannya apa
- `auth/validate` = yang penting ujungnya mengandung ini

## Kapan Pakai Yang Mana?
| Situasi | Gunakan |
|---|---|
| Nunggu elemen muncul/hilang di layar | `wait_for(state=...)` |
| Nunggu server selesai merespon sebuah request | `with page.expect_response(...)` |
| Nunggu statis (nggak disarankan!) | `timeout=10000` di `expect()` |
