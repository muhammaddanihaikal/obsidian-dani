# 12 - Test Independence (Data Isolation) via API

**Konsep Dasar:**
Setiap test case harus mandiri (Independent). Artinya, `test_delete` tidak boleh gagal hanya karena `test_add` sedang error. Oleh karena itu, kita harus menyiapkan data pendukung ("User Tumbal") sesaat sebelum test berjalan.

**Mengapa pakai API? Kenapa tidak lewat UI?**
1. **Kecepatan (Speed):** Bikin user lewat UI butuh 5-10 detik. Lewat API hanya 0.1 detik.
2. **Kestabilan (Reliability):** Jika halaman Add User error secara UI, `test_delete` via API akan tetap bisa berjalan lancar.
3. **Fokus:** Kita memisahkan fungsi persiapan data (Setup) dan aksi pengujian yang sebenarnya.

---

## 1. Cara Mencari API (Inspect Element)
Sebagai QA, kita tidak perlu selalu bertanya ke Developer. Kita bisa mencari API sendiri:
1. Buka fitur web secara manual (misal: halaman Add User).
2. Isi data form lengkap, **TAPI JANGAN KLIK SAVE DULU**.
3. Klik kanan ➜ **Inspect** ➜ buka tab **Network** (filter ke Fetch/XHR).
4. Klik *icon* blokir/clear 🚫 agar log kosong.
5. Klik Save di halaman web.
6. Lihat file yang muncul di tab Network (biasanya ber-method `POST`).
7. Klik file tersebut dan buka tab **Payload** untuk melihat bentuk data JSON-nya.

---

## 2. Implementasi di Playwright (conftest.py)

Gunakan fitur `page.request.post()` milik Playwright. Karena kita menggunakan `logged_in_page`, cookies autentikasi otomatis terbawa sehingga API tidak akan menolak permintaan kita (Unauthorized).

```python
import pytest
from playwright.sync_api import Page
from config import BASE_URL

@pytest.fixture
def api_dummy_user(logged_in_page: Page):
    """Membuat user tumbal via API (sangat cepat) sebelum test jalan"""
    
    tumbal_username = "tumbal_api_123"
    
    # Langsung tembak API pakai cookie yang ada di logged_in_page
    response = logged_in_page.request.post(
        f"{BASE_URL}/web/index.php/api/v2/admin/users",
        data={
            "empNumber": 2, 
            "password": "Password_Tumbal1",
            "status": True,
            "userRoleId": 1,
            "username": tumbal_username
        }
    )
    
    assert response.ok, f"Gagal bikin user via API: {response.text()}"
    
    # Berikan username tumbal ini ke test
    yield tumbal_username
```

---

## 3. Cara Penggunaan di Test

Sisipkan parameter `api_dummy_user` ke dalam fungsi pengujian, lalu gunakan string tersebut sebagai kata kunci pencarian.

```python
def test_delete_user(logged_in_page: Page, api_dummy_user: str):
    """Menghapus data user"""
    page = logged_in_page
    admin_page = AdminPage(page)
    sidebar = Sidebar(page)

    sidebar.admin.click()

    # Cari user tumbal yang baru saja dibikin API dan validasi
    admin_page.search(api_dummy_user)
    expect(admin_page.user_row(api_dummy_user)).to_be_visible()

    # Hapus user tumbalnya
    admin_page.delete_user(api_dummy_user)

    # Pastikan berhasil terhapus
    admin_page.search(api_dummy_user)
    expect(admin_page.user_row(api_dummy_user)).to_be_hidden()
```
