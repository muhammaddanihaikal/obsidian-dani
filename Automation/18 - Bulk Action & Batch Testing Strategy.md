# 🗑️ 18 - Bulk Action & Batch Testing Strategy

## 1. Filosofi Bulk Action di QA Automation

Pengujian aksi massal (*bulk/batch actions* seperti bulk delete, bulk approve, bulk export) adalah salah satu fitur krusial yang sering diuji di dunia kerja karena menyangkut performa backend, integritas data, dan manipulasi tabel multi-baris.

Tantangan utama pengujian massal:
- **Data Isolation**: Aksi massal berpotensi menghapus data yang salah jika tidak diisolasi dengan cermat.
- **Interaksi DOM Dinamis**: Tombol aksi massal (misal: "Delete Selected") seringkali bersifat kontekstual (baru muncul jika ada minimal 1 baris yang dicentang).
- **DOM Pointer Event Interception**: Checkbox kustom pada framework modern (Vue.js, React) sering menutupi elemen `<input>` asli.

---

## 2. Strategi Penyiapan Data Tumbal (Batch Fixture)

Prinsip dasar: **Setiap test destruktif massal wajib membuat dan membersihkan datanya sendiri.**

### Pola Fixture Batch:
```python
@pytest.fixture
def api_create_bulk_users(logged_in_page: Page):
    """Menyiapkan 2 user via API dan membersihkannya setelah test."""
    prefix = "bulk_user_"
    usernames = [f"{prefix}1", f"{prefix}2"]
    created_user_ids = []

    # 1. Setup: Buat 2 user via API
    for username in usernames:
        post_response = logged_in_page.request.post(
            f"{BASE_URL}/web/index.php/api/v2/admin/users",
            data={
                "userRoleId": 1,
                "empNumber": 2,
                "username": username,
                "password": "JagungManis_9192",
                "status": True,
            },
        )
        assert post_response.ok
        created_user_ids.append(post_response.json()["data"]["id"])

    # 2. Pinjamkan list username ke test
    yield usernames

    # 3. Teardown: Hapus sekaligus dalam 1 request API
    delete_response = logged_in_page.request.delete(
        f"{BASE_URL}/web/index.php/api/v2/admin/users",
        data={"ids": created_user_ids},
    )
    if delete_response.status != 404:
        assert delete_response.ok
```

> [!TIP]
> **Efisiensi API Delete**: Endpoint `DELETE` di arsitektur RESTful modern umumnya menerima array ID `{"ids": [1, 2]}`. Manfaatkan payload array agar proses teardown hanya membutuhkan 1 kali HTTP request tanpa perlu perulangan (*looping*).

---

## 3. Menghadapi Pointer Event Interception di Checkbox Modern

Pada framework web modern (seperti Vue.js di OrangeHRM), developer sering menyembunyikan input asli dan menampilkan styling kustom:

```html
<div class="oxd-checkbox-wrapper">
    <label>
        <input type="checkbox"> <!-- Tersembunyi / opacity 0 -->
        <span class="oxd-checkbox-input">
            <i class="oxd-icon bi-check"></i>
        </span>
    </label>
</div>
```

### Masalah:
Jika Playwright memanggil `get_by_role("checkbox").click()`, Playwright akan melempar error:
> 💥 `subtree intercepts pointer events`

Elemen visual `<span>` dan icon `<i>` menutupi `<input>` asli di lapisan atas, sehingga Playwright menolak klik karena menganggap interaksi terhalang.

### Solusi Emas:
Klik elemen pembungkus terluar yaitu **`<label>`**:
```python
self.user_row(username).locator("label").click()
```
Secara spesifikasi standar HTML, mengklik tag `<label>` otomatis mencentang elemen `<input type="checkbox">` di dalamnya tanpa memicu interception error.

---

## 4. Dua Pendekatan Pemilihan Baris Data

| Pendekatan | Cara Kerja | Kapan Digunakan? |
| :--- | :--- | :--- |
| **Filter + Select All** | Filter keyword tertentu sehingga tabel hanya menampilkan data tumbal, lalu centang *Header Checkbox*. | Saat backend pencarian mendukung *partial/wildcard search*. |
| **Selective Direct Check** ⭐ | Langsung centang baris data spesifik berdasarkan nama tanpa filter: `user_row(name).locator("label").click()`. | Saat backend menggunakan *exact match*, atau saat data tumbal sudah terjamin berada di halaman pertama (urutan abjad). |

---

## 5. Pola AAA pada Skenario Bulk Delete

```python
# 1. Arrange (persiapan)
# Buka menu admin dan pastikan data tumbal ada di tabel
sidebar.admin.click()
for username in usernames:
    expect(admin_page.user_row(username)).to_be_visible()

# 2. Act (aksi)
# Centang seluruh user tumbal, klik Delete Selected, lalu konfirmasi modal
admin_page.bulk_delete(usernames)

# 3. Assert (validasi)
# Pastikan seluruh user tumbal sudah lenyap dari tabel
for username in usernames:
    expect(admin_page.user_row(username)).to_be_hidden()
```

> [!WARNING]
> Jangan lakukan assertion `expect("No Records Found").to_be_visible()` jika tabel masih memiliki baris data lain. Cukup validasi bahwa data-data spesifik yang dihapus telah berstatus `to_be_hidden()`.
