# Rekap Progress Belajar QA Automation (Dani)

Dokumen ini melacak perjalanan belajar *QA Automation* menggunakan Playwright dan Pytest.

### 📅 31 Agustus 2026
**Fondasi Framework & UI Automation**
- Page Object Model (POM), Pytest Fixtures, Locator & Assertion (AAA Pattern).
- Dynamic Waiting Strategy, Data-Driven Testing (DDT) pakai `user_data.json` & `data_factory`.

### 📅 1 September 2026
**Troubleshooting & Maintenance**
- Debug elemen bermasalah, fixing database PostgreSQL di Docker container.

### 📅 3 September 2026
**Optimasi Kecepatan (Authentication State)**
- Login cuma 1x per sesi pakai `context.storage_state` ➜ cookies disimpan ke `.auth/state.json`.
- Waktu eksekusi terpangkas drastis.

### 📅 4 September 2026
**Test Independence via API Injection**
- `test_edit` & `test_delete` tidak bergantung pada `test_add` (pakai User Tumbal dari API).
- Setup & Teardown pakai `yield` — atas = bikin data, bawah = hapus data.
- Logika `if != 404` biar teardown tidak kasih *error* palsu kalau data sudah terhapus via UI.
- Frontend State Desync: *autocomplete* bisa *invalid* kalau dipaksa pilih nilai yang sama persis.
- Headless Mode: 10 UI test ➜ 22 detik! 🚀

### 📅 5 September 2026
**Negative Test & Container Scoping**
- `test_add_user_empty`: Klik Save tanpa isi form, validasi 5 pesan "Required" muncul.
- `to_have_count(N)`: Assertion untuk elemen kembar (bukan `to_be_visible()` yang strict).
- `exact=True`: Cocokkan teks persis, bukan substring.
- Container Scoping (Bilik Terkecil): Kunci ke wrapper terkecil per field bukan form besar.

### 📅 6 September 2026
**Filter/Search, Loop Validation & Race Condition**
- 4 test filter (Username, User Role, Employee Name, Status) — masing-masing divalidasi secara ketat.
- `rows.all()` + `for loop`: Validasi SETIAP baris di tabel, bukan hanya sampling baris pertama.
- Satpam Loop: `expect(rows.first).to_be_visible()` wajib sebelum loop agar tidak *False Positive*.
- **Race Condition**: Robot lebih cepat dari loading ➜ membaca data lama/stale ➜ test error palsu.
- **`with page.expect_response("**/api/*")`**: Solusi race condition — tahan robot sampai respon API mendarat.

### 📅 7 September 2026
**Decoupling POM, Dynamic State Reset & Multi-Criteria Filter**
- Decoupling POM: Memisahkan pengisian field dan penekanan tombol `search()` & `reset()` agar modular.
- Dynamic State Reset: Menangkap teks jumlah data awal (`initial_records`) untuk validasi pemulihan tabel secara dinamis.
- Atasi Strict Mode Violation: Menambahkan `.first` untuk membedakan label tabel dengan toast popup.
- Filter Kombinasi: Validasi multi-kriteria (Role + Employee + Status) sekaligus per baris tabel.
- Standar Docstring: Wajib `""" """` 1 baris di setiap method Page & fungsi Test.
- Allure Report: Integrasi reporting interaktif Allure (`allure-pytest`) dan dekorator `@allure.title` untuk judul Test Case resmi.
- Rekor Pengujian: Seluruh 17 test suite lulus hijau 100% dalam 35 detik! 🚀
