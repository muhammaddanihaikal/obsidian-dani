---
tags:
  - QA
  - Automation
  - Playwright
  - Assertion
date: 2026-08-31
---
# ✔️ Playwright Assertion (expect)

Assertion adalah cara kita **memverifikasi** apakah hasil aksi kita sesuai ekspektasi. Ibarat ngecek bon belanjaan: ""Bener nggak barangnya sesuai pesanan?""

## Import
`python
from playwright.sync_api import expect
`

## Assertion yang Sudah Dipelajari

### Cek Halaman (Page)
`python
expect(page).to_have_url("https://..../dashboard/index")   # URL halaman sesuai
expect(page).to_have_title("OrangeHRM")                     # Judul tab browser sesuai
`

### Cek Elemen (Locator)
`python
expect(element).to_be_visible()              # Elemen terlihat di layar
expect(element).to_contain_text("...")       # Elemen MENGANDUNG teks tertentu
expect(element).to_have_text("...")          # Elemen punya teks PERSIS seperti ini
`

## Contoh Penggunaan di Test
`python
# Cek login berhasil pindah ke dashboard
expect(page).to_have_url(f"{BASE_URL}/web/index.php/dashboard/index")
expect(dashboard_page.heading).to_be_visible()

# Cek error message muncul saat login gagal
expect(login_page.error_message).to_be_visible()
expect(login_page.error_message).to_contain_text("Invalid credentials")

# Cek data user setelah edit
expect(admin_page.user_role_cell(username)).to_have_text("ESS")
expect(admin_page.status_cell(username)).to_have_text("Enabled")
`

## `to_contain_text` vs `to_have_text`
| Method | Artinya | Contoh |
|---|---|---|
| `to_contain_text("abc")` | Cukup **mengandung** teks "abc" | "Hello abc world" ✅ |
| `to_have_text("abc")` | Harus **persis** teks "abc" | "Hello abc world" ❌, "abc" ✅ |

## Auto-Waiting & Timeout
- Secara default, `expect()` punya **timeout 5 detik**.
- Selama 5 detik itu, Playwright akan terus mengecek berulang-ulang.
- Kalau lewat dari 5 detik dan kondisi belum terpenuhi → Test Failed.
- Timeout bisa diatur manual: `expect(element).to_be_visible(timeout=10000)` (10 detik)
- Tapi lebih baik pakai pendekatan dinamis (lihat catatan Network Interception).
