---
tags:
  - Project
  - QA
  - Automation
  - OrangeHRM
  - Playwright
date: 2026-10-20
status: in-progress
---

# 🚀 Orange HRM Automation

> Hub utama dan ringkasan arsitektur pengujian otomatisasi berbasis web untuk aplikasi **OrangeHRM Demo** menggunakan **Python + Playwright + Pytest**.

---

## 📌 Indeks Dokumen Proyek
- 📊 [[Audit & Evaluasi Proyek|Hasil Audit Kepatuhan & Best Practices (3 Level)]]
- 📘 Link ke Workspace Lokal: `d:\Project\Orange HRM Automation`

---

## 🛠️ Tech Stack & Konfigurasi
- **Language:** Python ≥ 3.14
- **Automation Framework:** Playwright (Sync API)
- **Test Runner:** Pytest + Allure Report
- **Package Manager:** `uv`
- **Target App:** Local Docker OrangeHRM (`http://localhost:8080`)

---

## 📐 Pola Arsitektur Utama
1. **[[page-object-model|Page Object Model (POM)]]:**
   - Struktur halaman dipecah per modul (`pages/admin/`, `pages/pim/`, `pages/dashboard/`, `pages/login_page.py`, `pages/sidebar.py`).
2. **[[fixtures-hooks|Autentikasi Global (`storage_state`)]]:**
   - Menggunakan cookies sesi `.auth/state.json` via fixture `logged_in_page` agar tidak mengulang proses login UI di setiap test CRUD.
3. **[[api-testing|Hybrid Setup/Teardown via API]]:**
   - Data uji disiapkan langsung via API request POST (`api_create_user`, `api_create_employee`) dan dibersihkan via DELETE request, menjaga isolasi pengujian tetap bersih (*self-contained*).
4. **[[assertions-waiting|Web-First & Network Waiting]]:**
   - Sinkronisasi stabil menggunakan `page.expect_response(...)` tanpa static sleep (`time.sleep`).
   - Penanganan *Race Condition* pada SPA Form Edit: Menunggu event respon `personal-details` saat transisi halaman edit sebelum memulai pengisian form agar Vue.js tidak menimpa nilai form yang baru diketik.
5. **File Upload Automation (`set_input_files`):**
   - Mengunggah file/foto profil langsung ke tag `input[type="file"]` (`.oxd-file-input`) menggunakan `.set_input_files()` tanpa memicu dialog file picker Windows explorer OS.
6. **Penanganan Custom UI Controls:**
   - Radio button OrangeHRM: `page.get_by_text("Male", exact=True)` (menghindari substring issue dan hidden input).
   - Dropdown custom Vue.js: Target `.oxd-select-text` lalu pilih opsi via `page.get_by_text(..., exact=True)`.

---

## 📊 Status Pengujian Modul PIM (Employee Management)
- [x] **TC-PIM-01:** `test_open_employee_list` — Membuka halaman Employee List
- [x] **TC-PIM-02:** `test_add_employee` — Menambahkan data Employee (dengan upload foto & user login)
- [x] **TC-PIM-03:** `test_add_employee_empty` — Validasi pesan error field mandatory Add Employee
- [x] **TC-PIM-04:** `test_edit_employee` — Mengubah data Personal Details Employee (Seeding via `api_create_employee` & Network Sync)
- [ ] **TC-PIM-05:** `test_edit_employee_empty` — Validasi mandatory saat edit Employee
- [ ] **TC-PIM-06:** `test_delete_employee` — Menghapus data Employee
- [ ] **TC-PIM-07:** `test_filter_employee_by_name` — Filter berdasarkan Employee Name
- [ ] **TC-PIM-08:** `test_filter_employee_by_id` — Filter berdasarkan Employee Id
- [ ] **TC-PIM-09:** `test_filter_employee_combination` — Filter kombinasi
- [ ] **TC-PIM-10:** `test_reset_filter_employee` — Reset filter Employee

---

## 📑 Modul Tambahan Profile Employee (Otomasi Paralel)
### 1. Personal Details (`pages/personal_details_page.py`)
- [x] **TC-PD-01:** `test_update_personal_details_successfully` — Update seluruh data diri & verifikasi persistensi
- [x] **TC-PD-02:** `test_update_personal_details_empty_mandatory_fields` — Validasi field mandatory
- [x] **TC-PD-03:** `test_update_personal_details_gender_female` — Pemilihan & persistensi radio button gender Female
- [x] **TC-PD-04:** `test_navigate_to_personal_details_from_pim_list` — Navigasi dari Employee List ke Personal Details

### 2. Contact Details (`pages/contact_details_page.py`)
- [x] **TC-PIM-CD-01:** `test_update_contact_details_primary_flow` — Update 11 field kontak (alamat, telp, email) & verifikasi reload
- [x] **TC-PIM-CD-02:** `test_navigate_to_contact_details_via_tab` — Navigasi via link tab Contact Details
- [x] **TC-PIM-CD-03:** `test_contact_details_invalid_email_validation` — Validasi format email tidak valid
- [x] **TC-PIM-CD-04:** `test_contact_details_invalid_telephone_validation` — Validasi format nomor telepon tidak valid
- [x] **TC-PIM-CD-05:** `test_clear_contact_details` — Pengosongan field opsional contact details

---

## 🔗 Keterhubungan Pengetahuan (Graph Knowledge)
- [[SKILL|Playwright Best Practices Master Skill]]
- [[page-object-model|Page Object Model Deep Dive]]
- [[fixtures-hooks|Fixtures & Scopes]]
- [[assertions-waiting|Assertions & Waiting Strategies]]
- [[locators|Locator Best Practices]]
