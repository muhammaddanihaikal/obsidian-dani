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
