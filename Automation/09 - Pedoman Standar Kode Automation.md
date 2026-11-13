# 📖 Pedoman Standar Penulisan Kode Automation (Dani's Style)

Dokumen ini adalah aturan wajib (SOP) untuk penulisan kode automation testing menggunakan **Playwright** dan **Pytest**. Setiap kode baru atau *refactor* harus mematuhi aturan di bawah ini.

## 1. Arsitektur & Struktur File (Page Object Model)
- **Filosofi Page vs Test (Bos vs Pelayan):**
  - **File Test = BOS:** Hanya bertugas mengatur skenario alur tingkat tinggi dan memvalidasi hasil akhir (`ASSERT`). File test tidak boleh dipusingkan oleh detail teknis HTML atau urutan klik tombol.
  - **File Page = PELAYAN:** Tempat seluruh urutan teknis pencarian elemen, pengetikan form, dan penekanan tombol (*Action Methods*) dibungkus rapi.
- **Definisi Elemen di `__init__`:**
  - Semua elemen statis (tombol, input, tabel, header) **WAJIB** didefinisikan sebagai atribut di dalam `__init__` (contoh: `self.add_btn = page.get_by_role("button", name="Add")`).
  - **DILARANG** membuat fungsi terpisah hanya untuk mengembalikan satu locator statis (contoh salah: `def add_button(self): return self.page...`).
- **Gunakan Action Method (Anti-Micro-Functions):**
  - Jika suatu alur terdiri dari beberapa langkah berurutan (misal: klik hapus di baris tabel lalu klik tombol konfirmasi "Yes, Delete" di popup), **WAJIB** disatukan menjadi satu *Action Method* di Page (contoh: `def delete_user(self, username):`).
  - Ini membuat kode menjadi **DRY (Don't Repeat Yourself)** dan mudah dirawat jika UI aplikasi berubah di masa depan.
- **Kompas 3 Pertanyaan Emas (Locator vs Action Method):**
  1. *Apakah elemen dipakai untuk Validasi (ASSERT)?* ➜ **Tetap Locator murni** (contoh: `error_message`, `user_row`, `table_rows`). Playwright butuh objek locator untuk `expect(locator).to_be_visible()`.
  2. *Apakah ada logika teknis di baliknya?* ➜ **Wajib Action Method** (contoh: network waiting `expect_response`, autocomplete wait, looping).
  3. *Apakah aksinya berdiri sendiri atau bagian dari alur utuh?*
     - *Aksi Mandiri (Standalone):* Begitu diklik tujuannya langsung tercapai (buka form, reset, search) ➜ Buat method mandiri (`click_add()`, `reset()`, `search()`).
     - *Aksi Perantara (Part of Flow):* Rangkaian klik modal/checkbox yang tak terpisahkan ➜ Satukan ke dalam *Composite Action Method* (`bulk_delete()`). Dilarang *over-engineering* memecah tombol modal konfirmasi jika tidak ada skenario pembatalan.
- **Pola AAA (Arrange, Act, Assert):** Setiap fungsi test wajib memiliki komentar pembatas yang jelas:
  - `# 1. Arrange (persiapan)`: Persiapan data dan inisiasi halaman.
  - `# 2. Act (aksi)`: Eksekusi aksi utama (biasanya cukup 1 baris memanggil Action Method, misal: `admin_page.delete(username)`).
  - `# 3. Assert (validasi)`: Validasi hasil yang diharapkan dibungkus dengan `with allure.step("..."):`.

## 2. Standar Penamaan (PEP 8 Python)
Mengikuti standar umum *programmer* Python:
- **Nama File & Folder:** Gunakan huruf kecil semua dengan garis bawah (contoh: `login_page.py`, `test_login.py`).
- **Nama Class:** Gunakan *PascalCase* (contoh: `LoginPage`, `DashboardPage`).
- **Nama Fungsi & Variabel:** Gunakan *snake_case* (contoh: `test_login_valid`, `error_message`, `login_btn`).

### 2.1 Konvensi Akhiran Variabel Locator (Suffix Dictionary)
Untuk membedakan jenis elemen secara visual tanpa harus membaca definisi lokatornya, gunakan akhiran baku berikut:

| Tipe Elemen UI | Suffix Baku | Contoh Variabel | Alasan / Standar |
|---|---|---|---|
| **Button / Tombol** | `_btn` | `submit_btn`, `tambah_destinasi_btn`, `batal_btn` | Singkat, standar umum dev & QA |
| **Input Text / Number** | `_input` | `alamat_input`, `koordinat_input`, `email_input` | Jelas untuk field ketik |
| **Dropdown / Select** | `_select` | `provinsi_select`, `kota_select`, `role_select` | Khusus elemen dropdown/combo |
| **Checkbox** | `_checkbox` | `syarat_ketentuan_checkbox`, `dokumen_checkbox` | Khusus kotak centang |
| **Radio Button** | `_radio` | `gender_male_radio`, `pembayaran_cash_radio` | Khusus pilihan radio |
| **Toggle / Switch** | `_switch` | `promo_switch`, `aktif_switch` | Khusus on/off switch |
| **Textarea (Multiline)** | `_textarea` | `catatan_textarea`, `deskripsi_textarea` | Membedakan dari input 1 baris |
| **File Upload Input** | `_file_input` | `dokumen_file_input`, `foto_file_input` | Input tersembunyi `type="file"` |
| **Modal / Dialog** | `_modal` | `destinasi_modal`, `konfirmasi_modal` | Kontainer popup/dialog |
| **Card / Box / Wrapper** | `_card` | `dokumen_card`, `aset_card` | Komponen kartu pembungkus |
| **Table** | `_table` | `user_table`, `aset_table` | Elemen tabel data |
| **Link / Hyperlink** | `_link` | `lupa_password_link`, `bantuan_link` | Elemen anchor navigasi |
| **Tab Bar / Menu Tab** | `_tab` | `informasi_tab`, `riwayat_tab` | Tab navigasi form/halaman |
| **Toast / Alert Banner** | `_toast` / `_alert` | `success_toast`, `warning_alert` | Notifikasi mengambang/banner |

## 3. Strategi Pencarian Elemen (Locator)
Pencarian elemen **WAJIB** mengikuti urutan prioritas di bawah ini (dari yang paling diutamakan sampai pilihan terakhir):
1. `page.get_by_role()` (Paling utama! Karena merepresentasikan cara user & *screen reader* melihat elemen, misal: *button*, *heading*).
2. `page.get_by_text()` (Untuk mencari elemen berdasarkan teks yang terlihat).
3. `page.get_by_label()` (Untuk input form yang punya label).
4. `page.get_by_placeholder()` (Untuk input yang punya teks *placeholder*).
5. `page.locator()` menggunakan atribut spesifik seperti class atau ID sederhana (jika elemen tidak punya teks/role jelas).
6. **(Jalan Terakhir)** Penggunaan *selector* CSS yang kompleks atau XPath. Sebisa mungkin hindari karena rapuh jika UI berubah.

## 4. Validasi (Assertion)
- **Tanpa Percabangan:** **DILARANG** menggunakan logika if-else di dalam file test hanya untuk mengecek hasil. Pisahkan skenario yang berbeda (sukses vs gagal) menjadi fungsi test yang berbeda.
- **Gunakan Expect:** Selalu gunakan fungsi `expect()` dari Playwright (contoh: `expect(elemen).to_be_visible()`).
- **Logical Grouping Allure Step:** Bungkus validasi terkait ke dalam satu blok `with allure.step("..."):` agar laporan Allure rapi dan tidak penuh sesak.

## 5. Manajemen Data Uji (Test Data)
- **Fleksibel:** Untuk pengujian cepat atau data yang sangat sedikit, diperbolehkan menuliskannya langsung (*hardcode*) di dalam file test demi kecepatan *development*.
- **Data Driven:** Namun, jika skenario tes mulai berulang dengan banyak variasi data (seperti validasi form login dengan berbagai kombinasi), disarankan memindahkannya ke file `.json` dan menggunakan `@pytest.mark.parametrize` (DDT).

## 6. Strategi Menunggu (Wait Strategy)
- **Wajib Dinamis:** Gunakan pendekatan tunggu yang fleksibel, seperti:
  - `page.wait_for_selector()`
  - `with page.expect_response("**/endpoint")` (sangat direkomendasikan untuk menghindari *flaky tests* akibat *loading* jaringan).
- **Haram:** **DILARANG KERAS** menggunakan waktu tunggu statis (contoh: `page.wait_for_timeout(5000)` atau `time.sleep()`).

## 7. Standar Komentar & Dokumentasi (Docstring vs Comment)
- **Docstring (`""" """`):**
  - **WAJIB** ada di setiap fungsi Page (cukup 1 baris ringkas) untuk *hover tooltip* di VS Code.
  - Di fungsi Test, jika sudah ada `@allure.title(...)`, docstring dihilangkan agar tidak redundan.
- **Komentar Biasa (`#`):**
  - **Comment the WHY, Not the WHAT (Wajib 1 Baris):** Jangan mengulang hal yang sudah jelas dari nama variabel (contoh salah: `# Isi harga` di atas `self.harga_input.fill()`). Tulis komentar HANYA untuk menjelaskan alasan teknis non-obvious (seperti tabrakan ID modal, index array non-nol, atau formatting backend).
  - Digunakan untuk pembatas pola **AAA** (`# 1. Arrange (persiapan)`, `# 2. Act (aksi)`, `# 3. Assert (validasi)`) dan pengelompokan blok langkah logis di Page Object.
