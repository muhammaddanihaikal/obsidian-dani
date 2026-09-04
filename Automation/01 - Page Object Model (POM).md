---
tags:
  - QA
  - Automation
  - Playwright
  - POM
date: 2026-08-31
---
# 📐 Page Object Model (POM)

POM adalah pola desain dimana setiap **halaman web** direpresentasikan sebagai **class Python**. Semua locator dan aksi yang berhubungan dengan halaman itu dikumpulkan di satu tempat, BUKAN disebar di file test.

## Kenapa Pakai POM?
- **Rapi:** Locator nggak berceceran di file test.
- **Reusable:** Satu page object bisa dipakai di banyak test.
- **Gampang maintenance:** Kalau elemen di website berubah, cukup edit di satu file page object aja, nggak perlu ubah semua file test satu-satu.

## Struktur Folder POM di Project
`
pages/
├── login_page.py          # Halaman Login
├── sidebar.py             # Komponen Sidebar (shared component)
├── dashboard/
│   └── dashboard_page.py  # Halaman Dashboard
└── admin/
    ├── admin_page.py      # Halaman daftar user
    ├── add_user_page.py   # Form tambah user
    └── edit_user_page.py  # Form edit user
`

## Anatomi Sebuah Page Object
Setiap page object punya 2 bagian utama:
1. **`__init__`** — Tempat mendefinisikan semua locator (elemen HTML).
2. **Method** — Fungsi-fungsi aksi yang bisa dilakukan di halaman itu.

### Contoh: LoginPage
`python
from playwright.sync_api import Page
from config import BASE_URL

class LoginPage:
    def __init__(self, page: Page):
        self.page = page
        self.PATH = "/web/index.php/auth/login"

        # --- LOCATORS ---
        self.username = page.get_by_role("textbox", name="Username")
        self.password = page.get_by_role("textbox", name="Password")
        self.login_button = page.get_by_role("button", name="Login")
        self.heading = page.get_by_role("heading", name="Login")
        self.error_message = page.get_by_role("alert")

    # --- METHODS ---
    def open(self):
        self.page.goto(f"{BASE_URL}{self.PATH}")

    def login(self, username, password):
        self.username.fill(username)
        self.password.fill(password)
        self.login_button.click()
`

### Cara Pakai di Test
`python
login_page = LoginPage(page)   # Buat object-nya
login_page.open()               # Panggil method open
login_page.login("Admin", "admin123")  # Panggil method login
`

## Shared Component — Sidebar
Kalau ada komponen yang muncul di **banyak halaman** (misalnya sidebar navigasi), buatkan class terpisah. Jangan copas locator sidebar ke setiap page object.

`python
class Sidebar:
    def __init__(self, page: Page):
        self.admin = page.get_by_role("link", name="Admin")
        self.pim = page.get_by_role("link", name="PIM")
        self.dashboard = page.get_by_role("link", name="Dashboard")
        # ... dst

# Cara pakai di test:
sidebar = Sidebar(page)
sidebar.admin.click()  # Klik menu Admin di sidebar
`

## Tips Penting
- **Jangan hardcode selector di file test.** Semua locator harus di file page object.
- Page object **TIDAK boleh punya assertion (expect)**. Assertion hanya ada di file test.
- Gunakan **subfolder** untuk mengelompokkan page objects per modul (admin/, dashboard/, dsb).
