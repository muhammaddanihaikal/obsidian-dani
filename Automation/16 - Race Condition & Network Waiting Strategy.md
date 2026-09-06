# 16 - Race Condition & Network Waiting Strategy

## 1. Apa itu Race Condition?

**Race Condition** adalah bug yang terjadi karena robot Playwright **lebih cepat dari loading website**.

Setelah tombol Search diklik, browser butuh waktu untuk:
1. Mengirim REQUEST ke server (API).
2. Menunggu server membalas (RESPONSE).
3. Merender data baru ke tabel.

Kalau robot langsung membaca tabel tanpa menunggu, dia akan membaca **data lama/stale** dan test bisa error atau memberikan hasil yang salah.

---

## 2. Kapan Race Condition Sering Muncul?

| Skenario | Kenapa Rawan |
|---|---|
| **Filter/Search** | Setelah klik Search, tabel dirender ulang dari API |
| **Submit Form (Save/Update)** | Setelah klik Save, halaman redirect atau toast muncul |
| **Hapus Data (Delete)** | Setelah klik Yes Delete, baris tabel menghilang |
| **Autocomplete** | Saat mengetik, dropdown muncul setelah request API |
| **Upload File** | Progress upload perlu waktu sebelum preview muncul |
| **Navigasi Halaman** | Perpindahan halaman belum selesai tapi sudah dicek |

---

## 3. Solusi: `expect_response` (Paling Tepat untuk API)

Gunakan `with page.expect_response(...)` untuk menunggu balasan dari server sebelum melanjutkan.

```python
# Nyalakan radar dulu, BARU klik tombolnya
with self.page.expect_response("**/api/v2/admin/users*"):
    self.search_btn.click()
# Di sinilah Playwright akan menunggu sampai response API mendarat
# baru kemudian kode selanjutnya dieksekusi
```

**Cara Membaca `"**/api/v2/admin/users*"`:**
- `**` di depan: Abaikan domain/host-nya, terserah apa.
- `*` di belakang: Abaikan buntut URL-nya (misal: `?limit=50&offset=0`).

---

## 4. Solusi Lain (Berdasarkan Kasus)

| Kasus | Solusi |
|---|---|
| Nunggu elemen **muncul** | `locator.wait_for(state="visible")` |
| Nunggu elemen **hilang** | `locator.wait_for(state="hidden")` |
| Nunggu teks loading hilang | `page.get_by_text("Searching...").wait_for(state="hidden")` |
| Nunggu halaman redirect | `page.wait_for_url("**/target-url**")` |
| Nunggu alert sukses muncul | `expect(page.get_by_text("Successfully Saved")).to_be_visible()` |

---

## 5. False Positive (Hijau Palsu) — Jebakan Loop Kosong

Saat memvalidasi data di tabel menggunakan loop, **WAJIB** pasang "satpam" sebelum loop:

```python
rows = admin_page.user_table.locator(".oxd-table-card")

# SATPAM: Pastikan tabelnya tidak kosong dulu!
# Tanpa ini, kalau tabelnya kosong, loop tidak jalan dan test tetap HIJAU (palsu!)
expect(rows.first).to_be_visible()

# Baru loop semua baris
for row in rows.all():
    expect(row.get_by_role("cell").nth(2)).to_have_text("Admin")
```

**Kenapa `rows.first.to_be_visible()` dan bukan cek Python biasa?**
Karena Playwright punya **Auto-Waiting**: dia akan menunggu sampai baris pertama beneran muncul di layar, bukan hanya ada di DOM. Ini sekaligus mencegah Race Condition saat tabel masih loading.
