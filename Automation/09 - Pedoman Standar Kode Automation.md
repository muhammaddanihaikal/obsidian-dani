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
- **Pola AAA (Arrange, Act, Assert):** Setiap fungsi test wajib memiliki komentar pembatas yang jelas:
  - `# ARRANGE`: Persiapan data dan inisiasi halaman.
  - `# ACT`: Eksekusi aksi utama (biasanya cukup 1 baris memanggil Action Method, misal: `admin_page.delete_user(username)`).
  - `# ASSERT`: Validasi hasil yang diharapkan.

## 2. Standar Penamaan (PEP 8 Python)
Mengikuti standar umum *programmer* Python:
- **Nama File & Folder:** Gunakan huruf kecil semua dengan garis bawah (contoh: login_page.py, 	est_login.py).
- **Nama Class:** Gunakan *PascalCase* (contoh: LoginPage, DashboardPage).
- **Nama Fungsi & Variabel:** Gunakan *snake_case* (contoh: 	est_login_valid, error_message, login_button).

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
- **Gunakan Expect:** Selalu gunakan fungsi expect() dari Playwright (contoh: expect(elemen).to_be_visible()).

## 5. Manajemen Data Uji (Test Data)
- **Fleksibel:** Untuk pengujian cepat atau data yang sangat sedikit, diperbolehkan menuliskannya langsung (*hardcode*) di dalam file test demi kecepatan *development*.
- **Data Driven:** Namun, jika skenario tes mulai berulang dengan banyak variasi data (seperti validasi form login dengan berbagai kombinasi), disarankan memindahkannya ke file .json dan menggunakan @pytest.mark.parametrize (DDT).

## 6. Strategi Menunggu (Wait Strategy)
- **Wajib Dinamis:** Gunakan pendekatan tunggu yang fleksibel, seperti:
  - page.wait_for_selector()
  - with page.expect_response("**/endpoint") (sangat direkomendasikan untuk menghindari *flaky tests* akibat *loading* jaringan).
- **Haram:** **DILARANG KERAS** menggunakan waktu tunggu statis (contoh: page.wait_for_timeout(5000) atau 	ime.sleep()).

## 7. Standar Komentar & Dokumentasi (Docstring vs Comment)
- **Docstring (`""" """`):**
  - **WAJIB** ada di setiap fungsi Page dan fungsi Test (cukup 1 baris ringkas).
  - Tujuannya agar saat kursor di-hover di VS Code, muncul *tooltip* penjelasan fungsi tersebut tanpa perlu membuka file aslinya.
- **Komentar Biasa (`#`):**
  - Digunakan untuk pembatas pola **AAA** (`# 1. Arrange`, `# 2. Act`, `# 3. Assert`) dan catatan teknis langkah demi langkah di dalam baris kodingan.
