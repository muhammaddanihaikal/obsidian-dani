# Rekap Progress Belajar QA Automation (Dani)

Dokumen ini melacak perjalanan belajar *QA Automation* menggunakan Playwright dan Pytest.

<details>
<summary><b>📅 7 September 2026</b></summary>

**Decoupling POM, Multi-Filter & Allure Reporting**
- **Decoupling POM**: Tombol `search()` & `reset()` dipisah dari input filter agar modular.
- **State Reset Dinamis**: Tangkap jumlah data awal (`initial_records`) untuk validasi pemulihan tabel.
- **Filter Kombinasi**: Validasi multi-kriteria (Role + Employee + Status) sekaligus per baris tabel.
- **Allure Report**: Integrasi visual dashboard, judul `@allure.title("[TC-XX] ...")`, dan format seragam AAA.
- **Sinkronisasi Excel**: Format 7 kolom murni (Rule-001) & penyiapan 9 test case modul PIM.
- **Rekor Pengujian**: 17 test suite lulus 100% hijau dalam 35 detik! 🚀

</details>

<details>
<summary><b>📅 6 September 2026</b></summary>

**Filter/Search, Loop Validation & Race Condition**
- **Filter Admin**: 4 skenario filter (Username, Role, Employee, Status) tervalidasi menyeluruh.
- **Loop Validation**: Validasi setiap baris tabel dengan `rows.all()` dan satpam `rows.first`.
- **Race Condition**: Tahan robot dari data stale menggunakan `with page.expect_response("**/api/*")`.

</details>

<details>
<summary><b>📅 5 September 2026</b></summary>

**Negative Test & Container Scoping**
- **Negative Test**: Validasi form kosong muncul 5 pesan "Required" via `to_have_count(5)`.
- **Container Scoping**: Kunci locator ke wrapper bilik terkecil per field agar presisi dan tidak ambigu.

</details>

<details>
<summary><b>📅 4 September 2026</b></summary>

**Test Independence via API Injection**
- **Isolasi Data**: Setup & Teardown user tumbal via API (`yield`) agar test edit & delete mandiri.
- **UI Desync & Headless**: Atasi desync pada autocomplete dan optimasi eksekusi headless mode (22 detik).

</details>

<details>
<summary><b>📅 3 September 2026</b></summary>

**Optimasi Kecepatan (Authentication State)**
- **Global Auth**: Login hanya 1x per sesi, cookies disimpan ke `.auth/state.json`.
- Waktu eksekusi seluruh test terpangkas drastis.

</details>

<details>
<summary><b>📅 1 September 2026</b></summary>

**Troubleshooting & Maintenance**
- Debugging elemen UI yang bermasalah dan perbaikan database PostgreSQL di container Docker.

</details>

<details>
<summary><b>📅 31 Agustus 2026</b></summary>

**Fondasi Framework & UI Automation**
- Setup Page Object Model (POM), Pytest Fixtures, dan Pola AAA (Arrange, Act, Assert).
- Data-Driven Testing (DDT) via JSON dan Dynamic Waiting Strategy Playwright.

</details>
