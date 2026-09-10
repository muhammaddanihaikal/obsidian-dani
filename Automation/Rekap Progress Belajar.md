# Rekap Progress Belajar QA Automation (Dani)

Dokumen ini melacak perjalanan belajar *QA Automation* menggunakan Playwright dan Pytest.

### 📅 10 September 2026
**Bulk Action, Batch Fixture & DOM Pointer Events**
- **Bulk Action POM**: Aksi hapus massal (`bulk_delete`) menerima list user dan konfirmasi modal.
- **Batch Fixture Isolation**: Setup 2 user tumbal via API & efisiensi teardown 1x request `DELETE`.
- **DOM Pointer Events**: Mengatasi `subtree intercepts pointer events` via tag `<label>`.
- **Validasi Multi-Row**: Assertion baris spesifik `to_be_hidden()` tanpa mengganggu data lain.

### 📅 7 September 2026
**Decoupling POM, Multi-Filter & Allure Reporting**
- **Decoupling POM**: Tombol `search()` & `reset()` dipisah dari input filter agar modular.
- **State Reset Dinamis**: Tangkap jumlah data awal (`initial_records`) untuk validasi pemulihan tabel.
- **Filter Kombinasi**: Validasi multi-kriteria (Role + Employee + Status) sekaligus per baris tabel.
- **Allure Report**: Integrasi visual dashboard, judul `@allure.title("[TC-XX] ...")`, dan format seragam AAA.
- **Sinkronisasi Excel**: Format 7 kolom murni (Rule-001) & penyiapan 9 test case modul PIM.

### 📅 6 September 2026
**Filter/Search, Loop Validation & Race Condition**
- **Filter Admin**: 4 skenario filter (Username, Role, Employee, Status) tervalidasi menyeluruh.
- **Loop Validation**: Validasi setiap baris tabel dengan `rows.all()` dan satpam `rows.first`.
- **Race Condition**: Tahan robot dari data stale menggunakan `with page.expect_response("**/api/*")`.

### 📅 5 September 2026
**Negative Test & Container Scoping**
- **Negative Test**: Validasi form kosong muncul 5 pesan "Required" via `to_have_count(5)`.
- **Container Scoping**: Kunci locator ke wrapper bilik terkecil per field agar presisi dan tidak ambigu.

### 📅 4 September 2026
**Test Independence via API Injection**
- **Isolasi Data**: Setup & Teardown user tumbal via API (`yield`) agar test edit & delete mandiri.
- **UI Desync**: Atasi desync pada autocomplete saat pengujian.

### 📅 3 September 2026
**Optimasi Kecepatan (Authentication State)**
- **Global Auth**: Login hanya 1x per sesi, cookies disimpan ke `.auth/state.json`.

### 📅 1 September 2026
**Troubleshooting & Maintenance**
- Debugging elemen UI yang bermasalah dan perbaikan database PostgreSQL di container Docker.

### 📅 31 Agustus 2026
**Fondasi Framework & UI Automation**
- Setup Page Object Model (POM), Pytest Fixtures, dan Pola AAA (Arrange, Act, Assert).
- Data-Driven Testing (DDT) via JSON dan Dynamic Waiting Strategy Playwright.
