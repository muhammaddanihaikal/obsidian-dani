# 15 - Strategi Pengujian & Pengelompokan (Markers)

## 1. Test "Borongan" vs "Fokus per Case"

**❌ Bad Practice (Anti-Pattern): End-to-End Borongan**
Membuat satu fungsi raksasa yang menjalankan semua skenario sekaligus.
*Contoh:* `test_e2e_user()` ➜ Buka web ➜ Login ➜ Add User ➜ Edit User ➜ Delete User ➜ Logout.
*Kelemahan:* Jika langkah "Add User" gagal (misal server timeout), maka langkah Edit dan Delete tidak akan pernah dieksekusi. Kita jadi kehilangan informasi apakah fitur Edit/Delete sebenarnya rusak atau tidak.

**✅ Best Practice: Independent/Atomic Tests**
Memecah test menjadi fungsi-fungsi kecil yang mandiri (fokus pada 1 *Assertion* utama).
*Contoh:* 
- `test_add_user` (Fokus ngetes Add)
- `test_edit_user` (Fokus ngetes Edit, data disuntik via API agar tidak bergantung pada test_add)
*Keuntungan:* Jika `test_add` gagal, `test_edit` tetap berjalan dan memberikan laporan yang akurat.

---

## 2. Mengelompokkan Test (Pytest Markers)

Dalam *real project*, kita memiliki ratusan *test case*. Kita tidak mungkin menjalankan semuanya setiap saat. Kita bisa mengelompokkannya menggunakan "Stiker" atau **Markers** di Pytest.

**Contoh Kategori Umum:**
- `@pytest.mark.smoke` ➜ **Smoke Test:** Pengujian fitur-fitur super kritis (Jantung aplikasi). Jika gagal, aplikasi tidak boleh di-deploy. (Contoh: Login, Checkout, Add Employee).
- `@pytest.mark.regression` ➜ **Regression Test:** Pengujian menyeluruh ke semua fitur (termasuk *edge cases* dan form *error validation*) untuk memastikan tidak ada fitur lama yang rusak.

**Cara Penggunaan di Kode:**
```python
import pytest

@pytest.mark.smoke
def test_add_employee(login):
    # Kode test nambah pegawai
    pass

@pytest.mark.regression
def test_add_employee_tanpa_nama(login):
    # Kode test ngecek pesan error kalau nama kosong
    pass
```

**Cara Menjalankan di Terminal:**
- Jalankan hanya *smoke test*: `uv run pytest -m smoke`
- Jalankan hanya *regression test*: `uv run pytest -m regression`

*(Catatan: Untuk menghilangkan warning saat pakai marker buatan sendiri, daftarkan nama marker tersebut di file `pytest.ini`)*
