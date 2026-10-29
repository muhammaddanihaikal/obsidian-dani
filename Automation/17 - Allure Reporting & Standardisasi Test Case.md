# 📊 17 - Allure Reporting & Standardisasi Test Case

## 1. Mengapa Allure Report?

Dalam pengujian profesional, laporan pengujian (*test report*) adalah jembatan komunikasi antara QA Engineer, Developer, Product Owner, dan Manajemen.

- **`pytest-html` (Standar Biasa)**: Hanya menyajikan tabel statis satu halaman. Cocok untuk verifikasi cepat, namun kurang representatif untuk portofolio atau presentasi manajerial.
- **`Allure Report` (Standar Emas Industri QA) ⭐**:
  - Dashboard analitik visual modern (grafik *pie chart*, persentase kelulusan, tingkat keparahan/*severity*).
  - Tampilan *Timeline* untuk memantau durasi eksekusi per test case dari awal hingga akhir.
  - Pengelompokan *Suites*, *Behaviors* (Epic, Feature, Story), dan *Packages*.
  - Riwayat pengujian (*History & Retries*) saat diintegrasikan dengan CI/CD.

---

## 2. Setup & Perintah Eksekusi

### A. Instalasi Plugin
```bash
uv add allure-pytest
```

### B. Menjalankan Test & Merekam Hasil
Tambahkan argumen `--alluredir` untuk menyimpan hasil pengujian mentah (file JSON):
```bash
uv run pytest --alluredir=allure-results
```

### C. Menjalankan Dashboard Interaktif
```bash
allure serve allure-results
```
*(Perintah ini menggunakan Allure CLI untuk membuat web server lokal dan otomatis membuka browser).*

### D. Menjalankan dari Luar Project
Perintah `allure serve` menerima *absolute path*, sehingga bisa dijalankan dari direktori terminal mana pun di komputer:
```bash
allure serve "D:\Project\orange-hrm-automation\allure-results"
```

### E. Kebersihan Git (`.gitignore`)
Folder `allure-results/` dan `allure-report/` berisi file sementara yang terus bertambah setiap eksekusi. **Wajib** dimasukkan ke `.gitignore`:
```gitignore
allure-results/
allure-report/
```

---

## 3. Dekorator Allure & Standar Judul

### A. `@allure.title` dengan Prefix ID (Best Practice) ⭐
Menaruh nomor ID test case langsung di depan judul `@allure.title`:
```python
import allure

@allure.title("[TC-ADMIN-01] Menambahkan data System Users")
def test_add_user(logged_in_page: Page):
    # ...
```
**Keuntungan:**
1. **Pencarian Cepat di UI:** Kotak pencarian Allure secara bawaan membaca teks judul. Mengetik `admin`, `TC`, atau nomor `01` akan langsung menyaring test case secara instan.
2. **Keterbacaan:** Di daftar panel kiri (*Suites*), nomor test case berjejer rapi mendampingi judul berbahasa manusia.

### B. Hubungan `@allure.title` vs Docstring `""" """`
- **Di File Test**: Jika sudah ada `@allure.title(...)`, docstring di dalam fungsi test **sebaiknya dihapus** agar tidak redundan (*duplicate text*).
- **Di File Page Object (POM)**: Docstring `""" """` **wajib dipertahankan** karena fungsi Page Object tidak memakai Allure dan docstring berguna untuk *hover tooltip* di VS Code.

### C. `@allure.id` vs `@allure.tag`
- **`@allure.id("...")`**: Merupakan metadata sistem internal (`as_id`) yang dirancang untuk sinkronisasi dengan **Allure TestOps** (aplikasi komersial Allure). Pada Allure Report open-source gratisan, nilai ini tidak muncul sebagai badge visual.
- **`@allure.tag("...")`**: Dirender secara langsung sebagai **badge/kapsul visual** di laporan Allure dan dapat difilter menggunakan sintaks `tag:<nama_tag>`.

---

## 4. Pytest Markers vs Allure: Sinergi Dua Dunia

Sering muncul pertanyaan: *"Smoke dan Regression itu miliknya Pytest atau Allure?"*

| Aspek | Pytest (`@pytest.mark`) | Allure (`allure`) |
| :--- | :--- | :--- |
| **Fokus Utama** | **Eksekusi & Filter Terminal** | **Visualisasi & Pelaporan** |
| **Cara Kerja** | Menentukan test mana yang dieksekusi | Menyajikan hasil dalam grafik & dashboard |
| **Contoh Perintah** | `uv run pytest -m smoke` | `allure serve allure-results` |

**Sinergi Otomatis:**
Allure secara cerdas membaca marker Pytest! Jika kita menempelkan `@pytest.mark.smoke` pada fungsi test:
- Pytest akan menggunakannya untuk filter eksekusi di terminal.
- Allure otomatis membuatkan badge tag `smoke` di dashboard tanpa perlu kodingan tambahan.

---

## 5. Standar Penamaan ID Test Case di Industri

Pola yang paling populer dan seimbang (*sweet spot*) di industri pengujian perangkat lunak:

$$\text{Format:} \quad \mathbf{TC\text{-}[KODE\_MODUL]\text{-}[NOMOR]}$$

### Contoh Penerapan:
- `TC-AUTH-01` ➜ Modul Authentication (Login/Logout)
- `TC-ADMIN-01` ➜ Modul Admin (User Management)
- `TC-PIM-01` ➜ Modul PIM (Employee Management)

### Mengapa Pola Ini Unggul?
1. **Konteks Instan**: Membaca `TC-PIM-03` langsung memberi tahu penguji bahwa ini adalah modul karyawan, tanpa perlu membuka tiket atau file lain.
2. **Penomoran Independen**: Setiap modul memulai urutannya dari `01`. Penambahan fitur di modul Admin tidak merusak urutan penomoran di modul PIM.
3. **Mudah Difilter**: Memudahkan pencarian cepat di Allure Report, Jira, maupun file spreadsheet.

---

## 6. Allure Test Steps (`@allure.step` & `with allure.step`)

Jika `@allure.title` adalah judul buku pengujian, maka **Allure Steps** adalah bab dan langkah-langkah di dalamnya. Tanpa step, laporan Allure hanya menampilkan status *Passed/Failed* secara gelondongan tanpa alur kronologis.

### A. Pola Hybrid (Standar Emas QA Senior) ⭐
Untuk menjaga kode tetap bersih (*clean code*) dan tidak mengotori file test dengan terlalu banyak indentasi, gunakan **Pola Hybrid**:

1. **Di Page Object (Aksi & Interaksi Form)**: Gunakan dekorator `@allure.step("...")` tepat di atas *Action Method*.
   ```python
   # File: pages/admin/admin_page.py
   import allure

   @allure.step("Mengeklik tombol Add User")
   def click_add(self):
       self.add_btn.click()

   @allure.step("Mengisi filter Username dengan '{username}'")
   def filter_by_username(self, username: str):
       self.username_filter.fill(username)
   ```
   - **Keuntungan**: Didefinisikan 1x di Page Object, otomatis seluruh test case yang memanggil method tersebut memiliki laporan step yang rapi (*DRY - Don't Repeat Yourself*).

2. **Di File Test (Validasi / Assert)**: Gunakan context manager `with allure.step("..."):` khusus untuk memayungi fase Assert.
   ```python
   # File: tests/test_user.py
   # 3. Assert (validasi)
   with allure.step("Memvalidasi data user baru berhasil disimpan dan muncul di tabel"):
       expect(page.get_by_text("Successfully Saved")).to_be_visible()
       expect(page).to_have_url(f"{BASE_URL}/web/index.php/admin/viewSystemUsers")
       admin_page.filter_by_username(username)
       admin_page.search()
       expect(admin_page.user_row(username)).to_be_visible()
   ```

### B. Standar Tata Bahasa Step (Kata Kerja Aktif Awalan "Me-")
Gunakan kata kerja aktif berawalan **"Me-"** agar selaras dengan tata bahasa SOP formal dan judul test case:

$$\text{Rumus:} \quad \mathbf{[Kata\ Kerja\ "Me\text{-}"] + [Objek\ /\ Elemen] + [Nilai\ Parameter\ (jika\ ada)]}$$

| Kategori Aksi | Kata Kerja Baku | Contoh Penulisan Step |
| :--- | :--- | :--- |
| **Navigasi** | **Membuka / Mengakses** | `@allure.step("Membuka halaman System Users")` |
| **Tombol** | **Mengeklik** | `@allure.step("Mengeklik tombol Add User")` |
| **Input Teks** | **Mengisi / Mengosongkan** | `@allure.step("Mengisi field Username")` |
| **Pilihan / Dropdown** | **Memilih** | `@allure.step("Memilih opsi filter User Role")` |
| **Checkbox** | **Mencentang / Menghapus centang** | `@allure.step("Mencentang checkbox baris user")` |
| **Validasi (Assert)** | **Memvalidasi / Memastikan** | `with allure.step("Memvalidasi data user telah terhapus"):` |

> [!WARNING]
> **JANGAN PERNAH** menaruh password atau token rahasia ke dalam placeholder `{password}` karena teks asli akan terpampang jelas di web dashboard! Gunakan teks umum: `@allure.step("Mengisi field Password")`.

### C. Anatomi UI Allure: Arti Tanda Panah `>` vs Centang `✔`
Di dalam panel *Test body* pada laporan Allure:
- **Ikon `>` (Expandable Dropdown)**: Otomatis muncul jika method menerima **argumen / parameter** (disertai label kecil `1 parameter`). Jika diklik, panel akan membuka detail data riil yang diinput robot (misal: `username: 'dani'`).
- **Ikon `✔` (Centang Bulat Hijau)**: Muncul pada method yang murni berupa aksi atau blok assertion tanpa parameter fungsi (seperti `search()`, `reset()`, atau `with allure.step(...)`).

### D. Prinsip Pengelompokan Assertion (*Logical Grouping*)
- **DILARANG** membungkus setiap 1 baris `expect` ke dalam 1 `with allure.step` (*overkill/clutter*).
- **CUKUP 1 STEP** untuk 1 kesatuan tujuan validasi yang menaungi 2–4 baris `expect` terkait. Jika salah satu `expect` gagal, Allure otomatis menandai step tersebut dengan warna merah 🔴 dan menunjuk baris assertion yang gagal.
