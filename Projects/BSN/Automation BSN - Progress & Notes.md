# Automation BSN — Progress & Notes

> Catatan teknis & progress automation testing BSN Internal/External Portal.  
> Repository: [bsn-automation](https://github.com/muhammaddanihaikal/bsn-automation)  
> Folder lokal: `D:\Project\BSN\Fase 1\Automation Test\`

## 🔗 Referensi Terkait

- [[Regression Test - BSN Fase 1]]
- [[09 - Pedoman Standar Kode Automation]]
- [[11 - Playwright Authentication State]]

---

## 📊 Progress Fase

| Fase | Nama | Status | Catatan |
|------|------|--------|---------|
| 0a | Setup project (uv, git, struktur folder) | ✅ Done | Commit pertama pushed |
| 0b | Reconnaisance (inspect live selectors) | ✅ Done | Selector login, OTP, dashboard verified |
| 1 | Internal Auth (login, MFA, logout) | 🔄 In Progress | TC-INT-AUTH-01 PASSED (Login + MFA OTP) |
| 2 | Internal User Management (CRUD) | ⏳ Ready (Skeleton) | 10 TC Skeleton siap diisi Dani |
| 3 | Internal modul lain | 🔲 Todo | - |
| 4 | External Portal | 🔲 Todo | Setelah internal stable |
| 5 | CI/CD Pipeline | 🔲 Todo | GitHub Actions |

---

## 🏗️ Arsitektur & Pola Koding (Gaya OrangeHRM + BasePage)

### 1. Struktur Folder

```
Automation Test/
├── config.py                 ← BASE_URL_INTERNAL, HEADLESS
├── AGENTS.md                 ← AI guardrails (WAJIB DIBACA AI)
├── conftest.py               ← PUSAT SEMUA FIXTURE (Single conftest gaya OrangeHRM)
├── pytest.ini                ← base_url, markers
├── .env                      ← Semua credentials (JANGAN COMMIT)
├── api/
│   └── internal_user_api.py  ← API helper untuk setup/teardown data tumbal
├── data/
│   └── internal/
│       └── user_data.json    ← Data pengujian form (JSON)
├── helpers/
│   └── mailpit.py            ← get_otp(recipient_email)
├── utils/
│   ├── read_data.py          ← Helper pembaca file JSON
│   └── data_factory.py       ← Generator nama & username tumbal unik [AUTO-QA]
├── pages/
│   ├── base_page.py          ← Induk class (open, wait_for_url, get_toast)
│   ├── internal/
│   │   ├── login_page.py     ← Inherit BasePage
│   │   ├── navbar.py         ← Navbar & Logout Internal
│   │   ├── dashboard/
│   │   │   └── dashboard_page.py ← Dashboard Internal
│   │   └── user_management/
│   │       ├── user_list_page.py
│   │       ├── add_user_page.py
│   │       └── edit_user_page.py
│   └── external/
│       └── navbar.py
├── tests/
│   ├── internal/
│   │   ├── test_auth.py      ← TC-INT-AUTH-01..04
│   │   └── user_management/
│   │       └── test_user.py  ← TC-INT-USER-01..10 (Pola AAA)
│   └── external/
└── testcase/
    └── internal/
        ├── tc_auth.md        ← Dokumentasi Test Case Auth
        └── tc_user_management.md ← Dokumentasi Test Case User Management (10 TC)
```

### 2. Pola BasePage & Penggunaannya
Semua Page Object mewarisi `BasePage` untuk menghindari pengulangan fungsi `open()` dan `self.page`:
```python
# Di Page Object:
class UserListPage(BasePage):
    def __init__(self, page: Page):
        super().__init__(page)
        self.PATH = "/internal/users"

# Di Test File:
user_list_page = UserListPage(logged_in_internal)
user_list_page.open()  # Otomatis goto BASE_URL + PATH
```

### 3. Locator Priority (Sesuai Playwright Best Practices)
1. `get_by_role()` (button, link, heading, textbox)
2. `get_by_label()` / `get_by_placeholder()`
3. `get_by_text()`
4. `get_by_test_id()`
5. `locator("css")` *(opsi darurat jika HTML tidak memiliki role semantik)*

---

## ⚙️ Keputusan Teknis

| Keputusan | Pilihan | Alasan |
|-----------|---------|--------|
| Package manager | `uv` | Lebih cepat, deterministic |
| Test runner | `pytest` | Ekosistem luas, fixture powerful |
| Browser automation | Playwright | Lebih reliable dari Selenium |
| Base Architecture | `BasePage` tipis | Menghilangkan duplikasi `open()` & `self.page` |
| Test Case Docs | Markdown (`testcase/**/*.md`) | Cepat, ringan, mengikuti standar tim |
| API Helper | `api/internal_user_api.py` | Fixture conftest tetap ramping (< 50 baris) |
| Session management | `storage_state` → JSON file | Login sekali, reuse semua test |
| Fixture naming | `logged_in_internal` | Eksplisit per portal |
| OTP source | Mailpit API | Sandbox email catcher |
| Naming data tumbal | `[AUTO-QA] <Nama> <Timestamp>` | Isolasi data test |
| Self-healing | ❌ DILARANG tanpa izin user | Anti fake-green |

---

## 🔑 Environment Variables (.env)

```
INTERNAL_URL=https://terasrumah-sandbox.zegen.app
INTERNAL_EMAIL=<email_superadmin_automation>
INTERNAL_PASSWORD=<password_superadmin_automation>
MAILPIT_URL=https://mailpit.zegen.app
MAILPIT_USER=admin
MAILPIT_PASS=P@ssw0rd
```

---

## ⚠️ Checklist Reconnaisance (Phase 0b)

Perlu inspect live di `https://terasrumah-sandbox.zegen.app`:

### Form Login & OTP:
- [ ] OTP input: 1 box atau 6 box?
- [ ] Placeholder / label input OTP
- [ ] Button Verifikasi: text label

### Manajemen Pengguna:
- [ ] URL path halaman list pengguna (default: `/internal/users`)
- [ ] Selector input filter (Nama, Role, Status) & button Cari
- [ ] Selector button Tambah Pengguna
- [ ] URL path form tambah & edit pengguna
- [ ] Selector button Simpan & form fields
- [ ] Selector dialog konfirmasi hapus

---

## 📋 Aturan AI (Ringkasan AGENTS.md)

1. **Dilarang ubah/delete data real** → WAJIB buat data tumbal dulu via API
2. **Dilarang self-healing otomatis** → minta izin user dulu
3. **Dilarang blind mass test** → run test spesifik
4. **Dilarang anti fake-green** → jangan ubah assertion biar test pass
5. **Environment lock** → hanya sandbox/localhost
6. **Entitas sakral yang dilarang disentuh**: Superadmin user, Admin role, Kantor Pusat
7. **Komentar kode wajib 1 baris**: Dilarang panjang/bertele-tele, cukup 1 baris simpel & to the point
8. **Modul baru wajib model skeleton**: Locator dan fungsi dikosongkan untuk diisi user
9. **Dilarang hapus email di Mailpit**: Mailpit adalah inbox bersama seluruh tim, DILARANG hapus email via API/UI. Wajib gunakan polling tunggu pesan baru.

---

## 📅 Log Perubahan

| Tanggal | Perubahan |
|---------|-----------|
| 2026-10-26 | Phase 0a selesai: setup project, git init, commit pertama |
| 2026-10-26 | Adopsi gaya OrangeHRM + BasePage + Skeleton 10 TC User Management & testcase .md |
| 2026-10-26 | TC-INT-AUTH-01 PASSED: Modular Mailpit OTP helper + DashboardPage + MFA login flow (commit `75494f9`) |
