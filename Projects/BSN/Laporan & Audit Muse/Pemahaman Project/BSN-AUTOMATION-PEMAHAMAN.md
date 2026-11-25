# Pemahaman Automation BSN (bsn-automation)

> Hasil membaca seluruh file teks repo `bsn-automation` (clone lokal `~/workspace/bsn/bsn-automation/`) pada 2026-11-23 — baca saja, tidak ada kode yang dijalankan. File biner (2 PDF di `data/documents/`, 5 PNG di `data/images/aset rumah baru/`) hanya dicatat keberadaannya. Nilai kredensial tidak disalin ke dokumen ini.

## 1. Stack & cara jalan

- **Stack**: Python ≥ 3.14 + Pytest + Playwright (Sync API) + Allure + uv sebagai package manager. Target aplikasi: BSN "Terasrumah" sandbox — Portal Internal (staff) & Portal External (nasabah) di `terasrumah-sandbox.zegen.app`.
- **Dependensi** (`pyproject.toml`, project name `automation-test` v0.1.0): `allure-pytest>=2.16.2`, `pytest-playwright>=0.10.0`, `python-dotenv>=1.2.4`, `requests>=2.34.2`. Playwright sendiri tidak di-pin langsung — ikut dari `pytest-playwright`.
- **`pytest.ini`**: `base_url = https://terasrumah-sandbox.zegen.app`; marker terdaftar cuma 2: `smoke` (fitur kritis, wajib pass sebelum deploy) dan `regression` (pengujian menyeluruh + edge case).
- **`config.py`**: memuat `.env` sekali via `load_dotenv()`. Isi: `BASE_URL_INTERNAL` (env `INTERNAL_URL`, default sandbox), `HEADLESS` (default `true`), kredensial Superadmin Internal dari env, dan konfigurasi Mailpit (URL, user, pass, tuple `MAILPIT_AUTH`). ⚠️ Catatan keamanan: ada nilai default kredensial Mailpit yang tertulis di `config.py` (bukan hanya dari `.env`) — nilainya sengaja tidak disalin di sini.
- **`main.py`**: sisa bawaan template uv ("Hello from automation-test!"), tidak dipakai test.
- **Perintah jalan** (dari README/CHEATSHEET/AGENTS — dicatat, tidak dijalankan):
  - Setup: `uv sync` lalu `uv run playwright install chromium`; copy `.env.example` → `.env`.
  - Run spesifik ( dianjurkan saat dev/debug): `uv run pytest tests/internal/test_auth.py::TestAuthInternal::test_login_valid -v`
  - Smoke per portal: `uv run pytest tests/internal/ -m smoke -v` / `tests/external/`; semua: `uv run pytest tests/ -v`
  - Allure: `uv run pytest tests/ --alluredir=allure-results -v` lalu `allure serve allure-results`
  - CHEATSHEET tambahan: refresh sesi = jalankan `tests/internal/test_auth.py`; mode visual `--headed`, `--slowmo 500`, debug `PWDEBUG=1`, trace `--tracing on` + `playwright show-trace`, dan Playwright Codegen dengan `--load-storage=.auth/internal_state.json` untuk menangkap locator dalam keadaan sudah login.

## 2. Struktur folder & peran tiap bagian

```
bsn-automation/
├── AGENTS.md            ← aturan wajib repo (lihat bagian 7)
├── README.md            ← setup & perintah run ringkas
├── CHEATSHEET.md        ← perintah praktis: run, codegen, debug, trace, allure
├── config.py            ← BASE_URL, HEADLESS, kredensial & Mailpit dari .env
├── conftest.py          ← PUSAT semua fixture (1 file di root, "gaya OrangeHRM")
├── main.py              ← bawaan template, tidak terpakai
├── pytest.ini           ← base_url + markers smoke/regression
├── pyproject.toml       ← metadata + dependensi (uv)
├── helpers/
│   └── mailpit.py       ← ambil OTP dari Mailpit via REST API (polling)
├── api/
│   └── internal_user_api.py ← helper API data tumbal user (masih skeleton/TODO)
├── pages/
│   ├── base_page.py     ← induk Page Object (BasePage.open)
│   ├── internal/        ← login_page, navbar, sidebar, dashboard/, stock_management/aset_baru/, user_management/
│   └── external/        ← baru navbar.py (skeleton kosong)
├── tests/
│   ├── internal/        ← test_auth.py, test_navigation.py, user_management/, stock_management/aset_baru/
│   └── external/        ← KOSONG (hanya __init__.py)
├── testcase/            ← dokumen TC Markdown: tc_template.md + internal/ (auth, user mgmt, aset baru)
├── data/
│   ├── internal/        ← asset_baru_data.json, user_data.json
│   ├── documents/       ← 2 PDF legalitas (akta jual beli, akta kuasa menjual)
│   └── images/          ← folder "aset rumah baru" berisi 5 PNG (tampak depan, living room, dapur, kamar tidur, denah)
└── utils/
    ├── data_factory.py  ← generator nama/username data tumbal
    └── read_data.py     ← pembaca file JSON dari data/
```

## 3. Pola POM (Page Object Model)

- **Filosofi repo**: "File Test = BOS" (skenario tingkat tinggi + assertion saja, tanpa detail HTML), "File Page = PELAYAN" (semua locator + action method). Alur multi-langkah wajib dibungkus jadi satu action method.
- **`BasePage`** sangat tipis: simpan `page`, atribut `PATH` per halaman, dan method `open(base_url=BASE_URL_INTERNAL)` yang `goto(base_url + PATH)`. Tidak ada helper tunggu/assert di base — semua andalkan auto-wait Playwright & `expect()` di test.
- **Konvensi locator**: semua elemen statis didefinisikan sebagai atribut di `__init__`. Prioritas wajib (AGENTS.md): 1) `get_by_role()` 2) `get_by_text()` 3) `get_by_label()` 4) `get_by_placeholder()` 5) `locator()` class/ID sederhana 6) CSS kompleks/XPath = jalan terakhir. Praktik di kode:
  - `LoginPage` & `DashboardPage`: murni `get_by_role` (textbox Email/Password, button "Masuk ke Akun BSN", 6 textbox OTP per karakter, heading Dashboard).
  - `Sidebar`: memakai `get_by_test_id("sidebar-menu-...")` untuk menu/submenu.
  - `CreateAssetBaruPage` (paling lengkap): campuran `get_by_role` untuk tombol langkah wizard, `locator("#id")` untuk field Ant Design (`#developer_id`, `#price`, dll.), `get_by_test_id` untuk tombol navigasi/submit & modal destinasi, dan scoped locator `.ant-select-dropdown:not(.ant-select-dropdown-hidden)` + `.rounded-lg.border` filter(has_text=...) untuk dropdown AntD dan kartu dokumen legalitas.
  - `AssetBaruListPage`: `get_by_role` + `get_by_test_id` untuk tab/filter + `locator("tr.ant-table-row")` untuk baris tabel AntD (dengan komentar alasan menghindari hidden measure-row).
- **Konvensi turunan**: `EditAssetBaruPage(CreateAssetBaruPage)` — mewarisi seluruh locator & method wizard Langkah 1–6 dari halaman Create, hanya menambah PATH_PREFIX edit, tombol navigasi edit (prev/save draft), dan locator khusus mode edit (hapus/ganti foto, lihat file, baris destinasi). Ini pola reuse paling menonjol di repo.
- **Penamaan**: file/folder & fungsi/variabel `snake_case`, class `PascalCase` (PEP 8). Docstring 1 baris wajib di setiap fungsi Page & Test (boleh hilang di test bila sudah ada `@allure.title`). Komentar kode wajib 1 baris, ringkas.
- **Assertion hanya di file test**, selalu `expect()` Playwright; dilarang assert di Page Object dan dilarang if-else di test untuk cek hasil.
- **Wait**: dinamis saja (`wait_for_selector`, `wait_for_url`, `expect_response`, `wait_for(state=...)`, `expect(...).to_be_enabled()`); **dilarang keras** `page.wait_for_timeout()` & `time.sleep()` untuk menunggu UI.
- **Status isi Page Object**: yang terisi penuh = `LoginPage` (login + OTP; 2 method masih stub `pass`: `click_other_account`, `click_home_button`), `Sidebar`, `DashboardPage` (baru 1 locator heading), `AssetBaruListPage`, `CreateAssetBaruPage`, `EditAssetBaruPage`. Yang masih **skeleton kosong** (TODO + `pass`, sesuai aturan skeleton di bagian 7): `pages/internal/navbar.py`, `pages/external/navbar.py`, dan ketiga page User Management (`user_list_page.py`, `add_user_page.py`, `edit_user_page.py`).

## 4. Fixtures & auth (conftest, storage state, OTP Mailpit)

Semua fixture di satu `conftest.py` root:

- `guard_environment` (session, **autouse**): environment lock — assert `base_url` pytest mengandung salah satu dari `SAFE_DOMAINS = ["sandbox.zegen.app", "localhost", "127.0.0.1"]`; run di luar domain itu otomatis berhenti.
- `browser_type_launch_args` (session): menimpa args bawaan pytest-playwright agar `headless` mengikuti `HEADLESS` dari `.env`.
- `global_login_internal` (session): login UI **satu kali per pytest run** — buka Chromium, `LoginPage.open()` → `login(email, password)` Superadmin dari `.env` → ambil OTP via `get_otp()` Mailpit → `fill_otp()` → tunggu URL dashboard → simpan `context.storage_state(path=".auth/internal_state.json")`.
- `logged_in_internal` (function): membuat context baru dari `storage_state` file itu, buka halaman dashboard, `yield page`, lalu tutup context. Inilah fixture utama yang dipakai hampir semua test.

**OTP Mailpit** (`helpers/mailpit.py`, fungsi `get_otp(email, subject="Kode Masuk", timeout=30)`):

1. Catat ID email teratas saat ini (query `to:{email} subject:{subject}`, limit 1 ke `GET /api/v1/search`) sebagai pembanding — supaya OTP basi dari run sebelumnya tidak terambil.
2. Polling tiap 1 detik (maks 30 detik): hanya ambil email bila ID-nya **berbeda** dari ID awal.
3. Buka detail pesan (`GET /api/v1/message/{id}`), ekstrak OTP dari body HTML dengan regex `\b(\d{6})\b`.
4. Timeout → `TimeoutError`. Ada helper `_is_fresh_email` (cek umur email ≤ 60 detik) yang terdefinisi tapi tidak dipakai oleh `get_otp` saat ini.
5. **Aturan keras**: Mailpit adalah inbox bersama tim QA & Developer — **DILARANG KERAS menghapus email** di Mailpit (UI maupun API DELETE). Polling adalah satu-satunya mekanisme yang dibenarkan (diulang di AGENTS.md dan `tc_template.md`).

Catatan: sesi External (`external_state.json`) disebut di AGENTS.md sebagai konsep, tapi fixture login external **belum ada** di conftest — baru internal yang terimplementasi.

## 5. Data test (data factory, file data, aturan penamaan)

- **Aturan isolasi data (data tumbal)** — peraturan keras AGENTS.md §11: dilarang memodifikasi/menghapus data existing. Test yang butuh edit/delete **wajib** membuat data tumbal dulu via API, lalu cleanup via API setelah test.
- **Standar penamaan data uji**: format wajib `[AUTO-QA] <Nama> <Timestamp>`, contoh di AGENTS.md: `[AUTO-QA] Role Auditor 20261026_1100`. Tujuannya: data robot mudah dibedakan dari data asli dan aman dibersihkan.
- **Blacklist master data (dilarang disentuh)**: User `Superadmin`, `Terasrumah Admin`, akun PIC QA; Role `Superadmin`, `Admin`, default system roles; Kantor `Root`, `Kantor Pusat`.
- **`utils/data_factory.py`**: `generate_full_name(prefix="Pengguna")` → `[AUTO-QA] <Prefix> <timestamp ddmmyyHHMMSS>`; `generate_username(prefix="autoqa")` → `<prefix>_<8 hex UUID>`.
- **`utils/read_data.py`**: `read_data(file_name)` membaca JSON dari folder `data/` (path relatif terhadap root repo) dan mengembalikan dict; error jelas bila file tidak ada.
- **File data**:
  - `data/internal/asset_baru_data.json` — data lengkap wizard Aset Baru per langkah: `step_1_informasi` (developer, tipe aset, proyek, klaster, tipe unit, stok, subsidi, dimensi, deskripsi), `step_2_harga` (price, promo coret + normal price, persen DP), `step_3_galeri` (path 5 gambar + kategorinya), `step_4_legalitas` (2 dokumen: nama berkas + path PDF), `step_5_lokasi` (alamat, wilayah bertingkat — nilai wilayah wajib HURUF KAPITAL, kode pos, koordinat, 2 destinasi strategis), `step_6_fasilitas` (lebar jalan, arah mata angin, daya listrik, sumber air, pilih semua fasilitas).
  - `data/internal/user_data.json` — masih kerangka: blok `add_user` (prefix nama, prefix username, role & password masih bertanda TODO menunggu reconnaissance) dan blok `edit_user` yang isinya TODO. Tidak ada kredensial sungguhan di file ini — hanya placeholder TODO.
  - Aset file: 2 PDF di `data/documents/` (akta jual beli, akta kuasa menjual) dan 5 PNG di `data/images/aset rumah baru/` (tampak depan, living room, dapur, kamar tidur, denah) — dipakai langkah 3 & 4 wizard.
- **`api/internal_user_api.py`**: class `InternalUserAPI` dengan `create_tumbal_user(payload)` & `delete_tumbal_user(user_id)` — keduanya **masih skeleton**: implementasi request-nya masih berupa contoh ter-komentar + `pass`, menunggu endpoint API backend diketahui.

## 6. Test yang sudah ada

Konvensi ID: `TC-[PORTAL]-[MODUL]-[NOMOR]` di `@allure.title` (INT = Internal, EXT = External). Dokumen TC sumber ada di `testcase/**/*.md`; status eksekusi terakhir diambil dari catatan progress proyek (bukan dari menjalankan test).

| File test | ID TC | Modul / skenario | Status isi |
|---|---|---|---|
| `tests/internal/test_auth.py` | TC-INT-AUTH-01 | Auth Internal — login valid (email+password → OTP Mailpit → dashboard), assert URL dashboard + heading visible | **Terimplementasi penuh; tercatat PASSED** |
| `tests/internal/test_navigation.py` | TC-INT-NAV-01 s/d 03 | Sidebar — accordion Stock Management buka/tutup; navigasi sub-menu Aset Baru; navigasi menu User Management (semua `@pytest.mark.smoke`, pakai `logged_in_internal`) | **Terimplementasi penuh** |
| `tests/internal/stock_management/aset_baru/test_create_asset_baru.py` | TC-INT-STOCK-01 | Aset Baru — buat & ajukan aset baru E2E wizard 6 langkah dari JSON, checkpoint `expect` per transisi langkah, assert akhir URL detail + judul "Proyek - Tipe Unit" + status "Verifikasi" + "Unpublished" (timeout 60s untuk upload PDF) | **Terimplementasi penuh; tercatat PASSED** (±32 detik setelah cleanup static timeout → smart wait) |
| `tests/internal/user_management/test_user.py` | TC-INT-USER-01 s/d 10 | User Management — open, display, add, add-empty (negative), edit, delete, search valid, search invalid, filter, reset filter (smoke: 01,02,03,05,06; regression: 04,07,08,09,10) | **Skeleton AAA kosong** — semua body `pass`; Page Object-nya pun masih TODO |
| — (belum ada file test) | TC-INT-AUTH-02, 03, 04 | Logout; klik "Masuk dengan akun lain"; klik "Halaman Utama" saat sesi berakhir — baru terdokumentasi di `testcase/internal/tc_auth.md`; method pendukung di `LoginPage` masih stub `pass` | **Belum diimplementasikan** |
| `tests/external/` | — | Portal External | **Kosong total** (hanya `__init__.py`) |

Catatan celah teknis: `test_user.py` memakai fixture `api_create_user` (di TC-INT-USER-05/06/07) yang **belum didefinisikan** di `conftest.py` saat ini — konsisten dengan status skeleton (fixture API tumbal memang belum dibuat, sejalan `InternalUserAPI` yang masih TODO).

Dokumen TC (`testcase/`):
- `tc_template.md` — standar format TC tim (diadaptasi dari `tc_template_v3.md`): header Module/Sub Menu/Description (Positive/Negative Case)/Priority (Critical/High/Normal/Low); Steps & Expected **atomic** (1 nomor = 1 aksi; jumlah baris Steps **harus sama persis** dengan Expected; Expected positive diawali "Berhasil"); urutan skenario mengikuti business flow 10 langkah (open → display → add → add_empty → edit → delete → search valid → search invalid → filter → reset filter) yang tercermin persis di penomoran TC-INT-USER-01..10; plus template skeleton Page & Test yang wajib dikosongkan dan aturan komentar 1 baris.
- `tc_auth.md` (AUTH-01..04), `tc_user_management.md` (USER-01..10), `tc_aset_baru.md` (STOCK-01) — isi skenarionya sama dengan tabel di atas.

## 7. Aturan dari AGENTS.md repo (ringkasan)

AGENTS.md adalah panduan wajib untuk AI/manusia yang mengubah repo ini. Poin-poinnya:

1. **Konteks**: automation untuk 2 portal BSN (Internal staff & External nasabah), stack Python+Pytest+Playwright+Allure+uv; URL sandbox & Mailpit terdokumentasi; kredensial hanya dari `.env`.
2. **Mailpit**: DILARANG KERAS hapus email (inbox bersama tim); OTP wajib polling (lihat bagian 4).
3. **Arsitektur**: 1 `conftest.py` pusat di root (gaya OrangeHRM); POM "Test = BOS, Page = PELAYAN"; locator statis wajib di `__init__`; alur multi-langkah = 1 action method.
4. **Standar kode**: pola AAA di setiap test; prioritas locator semantic (role → text → label → placeholder → locator sederhana → CSS/XPath terakhir); assertion hanya `expect()`; wait hanya dinamis (larang `wait_for_timeout`/`time.sleep()`); PEP 8; docstring 1 baris wajib; komentar wajib 1 baris ringkas. Mengikuti "Pedoman Standar Koding Dani" di Obsidian.
5. **TC ID**: `TC-[PORTAL]-[MODUL]-[NOMOR]` (mis. `TC-INT-AUTH-01`, `TC-EXT-BRNDA-01`) di `@allure.title`.
6. **Markers**: `smoke` & `regression`.
7. **Larangan umum**: hardcode kredensial; locator CSS kompleks/XPath bila ada alternatif semantic; if-else untuk cek hasil di test; 1 fungsi test menguji banyak hal (wajib atomic); assert di Page Object; commit `.env`/`.auth/`.
8. **Data isolation** (§11): wajib data tumbal via API untuk edit/delete; format nama `[AUTO-QA] <Nama> <Timestamp>`; blacklist entitas sakral (Superadmin, Admin, Kantor Pusat, dll.); ada panduan mencari endpoint API sendiri via Network tab browser.
9. **AI Safety Guardrails** (§12) — aturan paling khas repo ini:
   - **Environment Lock**: hanya boleh menembak URL berlabel `sandbox`/`localhost`; dilarang mengganti base_url ke domain lain tanpa izin eksplisit user.
   - **Eksekusi Terarah**: saat dev/debug jalankan test spesifik sampai level 1 fungsi; dilarang `uv run pytest` tanpa filter saat debugging; dilarang loop besar (`--repeat-each=50+`)/parallel worker banyak tanpa instruksi user.
   - **Anti Fake-Green**: test FAIL karena bug aplikasi (mis. Error 415) **dilarang diubah assertion-nya** agar pass — biarkan merah, atau `xfail` hanya bila diminta user.
   - **Dilarang Self-Healing Otomatis Tanpa Izin**: jangan pernah mengubah locator/selector/logika test diam-diam saat test gagal; berhenti, catat trace, laporkan elemen yang hilang + dugaan penyebab, tunggu persetujuan user sebelum mengubah kode.
   - **Modul Baru Wajib Skeleton**: Page Object/Test baru dibuat sebagai kerangka kosong (locator placeholder `# TODO: Dani isi locator`, body `pass`, struktur AAA dengan komentar `1. Arrange / 2. Act / 3. Assert`) — sengaja dikosongkan sebagai ruang belajar user mengisi sendiri setelah reconnaissance UI.

## 8. Kesesuaian vs QA_RULES.md Muhammad

Patokan umum: `~/workspace/btn-smart/QA_RULES.md` (dikonfirmasi Muhammad 2026-10-29; fokus: TC baru, automation Playwright+Python, bug report).

**Yang SAMA (repo ini mengikuti patokan umum):**
- POM: 1 halaman = 1 class di `pages/` dengan subfolder per modul; komponen shared (sidebar) class terpisah; locator statis wajib atribut di `__init__`; tidak ada selector hardcoded di file test; Page Object tanpa assertion, assert hanya di test pakai `expect()`; dilarang if-else di test untuk cek hasil.
- Pola AAA dengan komentar bernomor `# 1. Arrange / # 2. Act / # 3. Assert` di setiap fungsi test.
- Prioritas locator identik: role → text → label → placeholder → locator class/ID sederhana → CSS kompleks/XPath terakhir.
- Naming PEP 8 (snake_case file/fungsi, PascalCase class); docstring 1 baris di method Page; docstring test boleh hilang bila ada `@allure.title`.
- Auth: login 1x via fixture session + `storage_state`, fixture function-scope menyediakan page yang sudah login per test (di repo: `global_login_internal` session + `logged_in_internal` function).
- Wait wajib dinamis; larangan keras `wait_for_timeout()` (dan `time.sleep()` untuk UI).
- Marker `smoke`/`regression` terdaftar di `pytest.ini`; perintah run via `uv run pytest -m ...`; Allure dengan `--alluredir=allure-results` + `allure serve`.
- Test data: variasi data via file JSON + utility `read_data` + Data Factory untuk data unik; data edit/delete wajib data tumbal terisolasi yang disiapkan/dibersihkan via API — sejalan dengan prinsip test independence patokan umum dan Aturan Eksplorasi Aplikasi (data existing read-only, hanya data buatan sendiri yang boleh diubah/dihapus).

**Yang BEDA / khusus repo ini:**
- **Format ID TC**: patokan umum `TC-[KODE_MODUL]-[NOMOR]`; repo BSN menambahkan portal: `TC-[PORTAL]-[MODUL]-[NOMOR]` (mis. `TC-INT-AUTH-01`).
- **Prefix data uji**: aturan eksplorasi umum memakai `AUTO-[tanggal]-[menu]`; repo automation BSN memakai `[AUTO-QA] <Nama> <Timestamp>` (dengan spasi & timestamp di akhir) — dua konteks berbeda (eksplorasi manual vs automation), jangan dicampur.
- **Guardrail AI eksplisit**: environment lock, larangan blind/mass run, anti fake-green, **larangan self-healing tanpa izin**, dan kewajiban skeleton untuk modul baru — semuanya hanya ada di AGENTS.md repo ini, tidak ada di QA_RULES umum. Ini aturan paling khas BSN.
- **Mailpit bersama tim**: larangan hapus email + polling anti-OTP-basi adalah kekhususan BSN (di patokan umum Mailpit hanya disebut sebagai kanal OTP login).
- **Blacklist entitas bernama**: Superadmin/Terasrumah Admin/PIC QA, role Admin, Kantor Pusat/Root — spesifik BSN; patokan umum hanya melarang menyentuh data existing secara umum.
- **Struktur fixture**: patokan umum membayangkan playwright/browser session + context/page function; repo menyederhanakan jadi 1 conftest root "gaya OrangeHRM" dengan context dibuat di dalam fixture `logged_in_internal` (browser dari pytest-playwright).
- **Allure step**: patokan umum meminta `@allure.step` di method Page dan `with allure.step(...)` mengelilingi assert di test; di repo saat ini **belum diterapkan** — Page Object tidak memakai `@allure.step` dan assert di test ditulis polos dengan komentar AAA (hanya `@allure.title`, plus `@allure.epic/feature` di test_navigation).
- **Dokumen TC**: patokan umum TC berbentuk Excel 7 kolom; repo automation menyimpan TC sebagai Markdown per modul di `testcase/` dengan header Module/Sub Menu/Description/Priority dan aturan Steps=Expected 1:1 (format SIT Excel BSN sendiri berbeda lagi — lihat BSN-STANDAR-TC-DAN-BUGREPORT.md).
- **Penyimpangan kecil dari aturan repo sendiri**: `helpers/mailpit.py` memakai `time.sleep(1)` sebagai interval polling API email (bukan untuk menunggu UI — praktiknya pengecualian yang hidup di helper resmi repo, tapi secara huruf bertabrakan dengan larangan `time.sleep()` di AGENTS.md); dan `config.py` menyimpan nilai default kredensial Mailpit di kode (lihat bagian 1).

## 9. Yang belum ada / todo

Dari README/AGENTS/catatan progress proyek (BSN-PEMAHAMAN.md bagian 8):

- **Fase 1 – Internal Auth**: masih *In Progress*. Yang selesai baru TC-INT-AUTH-01 (login valid, PASSED). Belum: AUTH-02 (logout), AUTH-03 (masuk akun lain), AUTH-04 (halaman utama) — dokumen TC-nya sudah ada, method Page-nya masih stub, file test-nya belum dibuat. Fixture login **External** (`external_state.json`) juga belum ada.
- **Fase 2 – Internal User Management**: status *Ready* (skeleton). 10 TC (USER-01..10) + 3 Page Object masih kerangka kosong berisi TODO/`pass` menunggu reconnaissance UI oleh Dani; `user_data.json` belum diisi data riil; `InternalUserAPI` (create/delete tumbal) belum diimplementasikan; fixture `api_create_user` yang dirujuk test belum dibuat.
- **Fase 3 – Stock Management Aset Baru**: ✅ Done untuk create (TC-INT-STOCK-01 PASSED full wizard). Sisa kecil: `AssetBaruListPage.search_aset()` masih `pass` (TODO), dan belum ada test edit aset walau `EditAssetBaruPage` sudah lengkap terisi.
- **Fase 4 – External Portal**: 🔲 Todo — `tests/external/` kosong, `pages/external/navbar.py` masih skeleton, belum ada Page Object/test external sama sekali (direncanakan setelah internal stabil).
- **Fase 5 – CI/CD Pipeline (GitHub Actions)**: 🔲 Todo — belum ada workflow di repo.
- Lainnya: `pages/internal/navbar.py` (dropdown profil & logout internal) masih skeleton — ini yang menghalangi AUTH-02; helper `_is_fresh_email` di mailpit.py belum terpakai; `main.py` bawaan template belum dibersihkan.
