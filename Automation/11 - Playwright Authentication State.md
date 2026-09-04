# 11 - Playwright Authentication State (Login 1x)

**Konsep Dasar:**  
Menyimpan sesi login (cookies & local storage) ke dalam sebuah file `.json` agar seluruh *test case* berikutnya tidak perlu mengulang proses mengetik username/password dari awal. Ini akan memangkas durasi testing secara drastis!

---

## 1. Langkah Implementasi (di `conftest.py`)

- Buat folder `.auth` dan pastikan folder ini ditambahkan ke `.gitignore` agar token/session tidak bocor ke Git.
- **Fixture 1 (`global_login`):** Diberi `scope="session"` agar jalan 1x saja di awal pengujian. Tugasnya login, lalu menyedot cookies.
- **Fixture 2 (`logged_in_page`):** Diberi scope function (default) agar jalan setiap test dimulai. Tugasnya membuka browser baru, lalu memasangkan cookies dari file `.json`.

```python
import os
import pytest
from playwright.sync_api import Browser, Playwright

@pytest.fixture(scope="session")
def global_login(playwright: Playwright):
    """Jalan 1x saja di awal. Tugasnya murni untuk login dan menyimpan state."""
    os.makedirs(".auth", exist_ok=True)
    browser = playwright.chromium.launch()
    context = browser.new_context()
    page = context.new_page()
    
    # -- Lakukan proses login UI di sini --
    
    # WAJIB: Tunggu sampai benar-benar masuk Dashboard agar cookies terbentuk sempurna
    page.wait_for_url("**/dashboard/index")
    
    # SAKTI: Simpan seluruh cookies dan state ke file JSON
    context.storage_state(path=".auth/state.json")
    browser.close()

@pytest.fixture
def logged_in_page(browser: Browser, global_login):
    """Fixture ini memberikan page yang SUDAH LOGIN untuk dipakai di file test"""
    # Buka context baru sambil MELAMPIRKAN cookies dari state.json
    context = browser.new_context(storage_state=".auth/state.json")
    page = context.new_page()
    
    # (Opsional tapi disarankan) Navigasikan otomatis ke halaman Dashboard
    page.goto("http://localhost:8080/web/index.php/dashboard/index")
    
    yield page
    context.close()
```

---

## 2. Cara Penggunaan di File Test

Di file test, ganti parameter bawaan `(page)` dengan `(logged_in_page)`. 
Gunakan trik alias `page = logged_in_page` agar kamu tidak perlu capek-capek mengubah seluruh nama variabel `page` di baris-baris kode bawahnya.

```python
from playwright.sync_api import Page

def test_fitur_tertentu(logged_in_page: Page):
    # TRIK ALIAS: "Mulai dari sini ke bawah, kalau aku sebut 'page', 
    # yang aku maksud adalah si 'logged_in_page' ya!"
    page = logged_in_page 
    
    # Kodingan langsung mulai dari aksi di dashboard (hemat baris kode)
    sidebar = Sidebar(page)
    sidebar.admin.click()
```

---

## 3. Penjelasan Type Hinting (`: Page` dan `: Browser`)

Pada `logged_in_page: Page` atau `browser: Browser`, teks yang diawali titik dua (:) disebut sebagai **Type Hinting**.

Kenapa ini wajib ditulis?
- Karena *Dependency Injection* di Pytest menyuntikkan *object* secara gaib saat runtime, sehingga editor (VS Code) tidak tahu tipe datanya saat kamu sedang *coding*.
- Type Hint berfungsi sebagai **"KTP" atau "Buku Panduan"** yang memberi tahu VS Code tentang wujud data tersebut.
- Hasilnya: **VS Code bisa menampilkan fitur Auto-Complete (Suggestion)** seperti `.click()`, `.locator()`, `.new_context()`, dll.
- Ingat untuk selalu `import` tipe datanya dari `playwright.sync_api`!

---

## 4. Filosofi Penamaan `logged_in_page`

Tidak ada aturan baku untuk penamaan fixture, namun sangat disarankan menggunakan nama yang deskriptif untuk membedakannya dari fixture bawaan `page` yang polos (tanpa login).

**Best Practice di Industri QA:**
- `logged_in_page`
- `authenticated_page`
- `auth_page`

Dengan memisahkan namanya, kita punya fleksibilitas. Kalau mau ngetes halaman login (seperti skenario gagal login), kita tinggal pakai `(page)`. Kalau mau ngetes Dashboard, pakai `(logged_in_page)`.
