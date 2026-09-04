---
tags:
  - QA
  - Automation
  - Playwright
  - Pytest
date: 2026-08-31
---
# 🚀 Masterclass Playwright: DDT, AAA, dan Network Waits

Catatan dari sesi belajar bareng AI membedah kasus Login di OrangeHRM.

## 1. 🥇 Aturan Emas: Pisahkan Test Berdasarkan Assertion!
Jangan pernah menaruh logika (If-Else) di dalam sebuah fungsi test. Fungsi test harus lurus-lurus aja.
**Kenapa?** Biar kalau error, kita langsung tahu spesifik bagian mana yang rusak.

- **Test Positif (Valid Login):** Assertion-nya adalah pindah URL ke Dashboard.
- **Test Negatif (Invalid Login):** Assertion-nya adalah muncul alert "Invalid credentials".
- **Test Edge Case (Form Kosong):** Assertion-nya adalah muncul teks "Required" di bawah form.

Karena **hasil akhirnya berbeda**, maka ketiganya WAJIB dipisah menjadi 3 fungsi yang berbeda (	est_login_valid, 	est_login_invalid, 	est_login_empty_fields).

## 2. 📊 Data-Driven Testing (DDT)
DDT dipakai kalau kita punya satu fungsi (misal: invalid login) yang mau diuji berulang kali pakai banyak variasi data (username salah, password salah, dua-duanya salah).

**Cara pakai di Pytest:**
`python
import pytest

@pytest.mark.parametrize("data_key", [
    "invalid_username", 
    "invalid_password", 
    "invalid_credentials"
])
def test_login_invalid(page, data_key):
    data = login_data[data_key]
    # lanjut testing...
`
*(Pytest akan otomatis menjalankan fungsi ini 3 kali dengan data yang berbeda).*

## 3. 📝 Pola AAA (Arrange, Act, Assert)
Pola ini bikin kode gampang dibaca oleh siapapun (bahkan orang non-programmer). Mirip alur manusia ngetes manual.

`python
# --- ARRANGE (Persiapan data & halaman) ---
data = login_data[data_key]
login_page = LoginPage(page)
login_page.open()

# --- ACT (Lakukan aksi) ---
login_page.login(data["username"], data["password"])

# --- ASSERT (Cek hasil / Validasi) ---
expect(login_page.error_message).to_be_visible()
`

## 4. ⏳ Menunggu Jaringan (Network Interception) vs Timeout Statis
Pas ngetes UI, seringkali *flakiness* (test kadang gagal kadang sukses) terjadi karena server lemot. Daripada nge-set waktu statis (misal: tunggu 10 detik), lebih baik pakai pendekatan dinamis.

**Analogi:** Kita pasang "jebakan" dulu sebelum menekan tombol login, biar Playwright nunggu respon API selesai.

`python
# Minta Playwright stand-by nunggu respon API "auth/validate"
with page.expect_response("**/auth/validate"):
    login_page.login(data["username"], data["password"]) # Tombol di-klik!

# Baris bawahnya baru akan dieksekusi SETELAH loading API selesai
expect(login_page.error_message).to_be_visible()
`

## 5. 🔍 Cara Membaca Locator Kompleks di Playwright
Contoh kode:
self.required_message = page.locator("span").filter(has_text="Required").first

**Cara bacanya seperti perintah ke robot:**
1. page.locator("span"): "Kumpulkan SEMUA elemen <span> di halaman ini."
2. .filter(has_text="Required"): "Saring dan sisakan hanya span yang ada tulisannya 'Required'."
3. .first: "Ambil HANYA urutan yang paling atas (pertama)."

*(Gunakan .first, .last, atau .nth(index) untuk mengatasi error **Strict Mode** kalau Playwright menemukan lebih dari satu elemen yang kembar).*
