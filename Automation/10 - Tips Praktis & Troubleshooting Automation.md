# 🛠️ 10 - Tips Praktis & Troubleshooting Automation (Playwright & Pytest)

Catatan ini merangkum teknik troubleshooting, optimasi koding, dan trik praktis yang dipelajari selama proses pengujian end-to-end (CRUD).

---

## 1. Menangani "Strict Mode Violation"
### Masalah:
Playwright secara *default* menerapkan **Strict Mode**. Jika sebuah locator menemukan lebih dari satu elemen yang sama persis di layar, Playwright akan melempar error dan menolak memilih secara acak.
> Contoh: `get_by_text("No Records Found")` menemukan 2 elemen (1 di dalam tabel, 1 lagi di dalam pesan *toast*).

### Solusi:
Gunakan penunjuk posisi jika memang teks tersebut kembar:
- `.first` : Mengambil elemen pertama yang ditemukan.
  ```python
  expect(page.get_by_text("No Records Found").first).to_be_visible()
  ```
- `.last` : Mengambil elemen terakhir yang ditemukan.
- `.nth(index)` : Mengambil urutan ke-n (0-indexed).

---

## 2. Property vs Method di Playwright Python
Sering timbul pertanyaan kenapa `.first` tidak menggunakan tanda kurung `()`, sedangkan `.nth(0)` atau `.click()` menggunakannya:

| Tipe | Contoh | Alasan Penggunaan |
|---|---|---|
| **Property** (Atribut) | `.first`, `.last` | Sifatnya mutlak, tidak menerima argumen/parameter tambahan. Berfungsi seperti kata benda. |
| **Method** (Fungsi) | `.click()`, `.fill("text")`, `.nth(1)` | Merupakan aksi (kata kerja) atau membutuhkan parameter data agar bisa dieksekusi. |

---

## 3. Menyalakan Autocomplete / Suggestion di VS Code
### Masalah:
Saat mengetik `page.`, VS Code (Pylance) sering tidak menampilkan rekomendasi kode (*No suggestions*). Hal ini terjadi karena parameter `page` di-inject secara otomatis oleh fixture Pytest, sehingga editor tidak tahu tipe data aslinya.

### Solusi (Type Hinting):
Tambahkan *type hint* `Page` pada parameter fungsi pengujian:
```python
from playwright.sync_api import Page, expect

def test_contoh(page: Page):
    # Begitu mengetik page., semua method Playwright akan muncul otomatis!
    page.goto(...)
```

---

## 4. Membaca "Aria Snapshot" Saat Test Gagal
Saat terjadi assertion error, Playwright akan mencetak pohon **Aria Snapshot** di terminal. Ini adalah "hasil rontgen" tampilan website pada detik saat kegagalan terjadi.

### Manfaat Utama:
1. **Melihat Pesan Validasi Tersembunyi:**
   Jika form tidak mau tersimpan, cari teks error merah seperti `Invalid` atau `Required` di dekat textbox yang bersangkutan.
2. **Investigasi Data Asli Website (Khusus Server Demo):**
   Jika autocomplete gagal, cek bagian header/profil di Aria Snapshot (misal melihat nama user yang sedang aktif: `manda user`) untuk mengetahui data apa yang benar-benar ada di database saat itu.

---

## 5. Smart Functional Wait vs Long Timeout
### Prinsip:
Daripada memperpanjang `timeout=10000` pada pengecekan URL redirect yang rentan *flaky*, gunakan **Smart Functional Wait**: tunggu indikator bisnis/UI yang pasti muncul sebelum memeriksa URL.

```python
# ❌ Hindari manipulasi timeout panjang jika tidak terpaksa
expect(page).to_have_url(".../viewSystemUsers", timeout=10000)

# ✅ Rekomendasi: Tunggu indikator suksesnya muncul dulu
expect(page.get_by_text("Successfully Saved")).to_be_visible()
expect(page).to_have_url(".../viewSystemUsers")
```
Cara ini meniru perilaku pengguna asli (melihat konfirmasi sukses terlebih dahulu baru berpindah halaman).
