---
tags:
  - QA
  - Automation
  - Pytest
  - DDT
date: 2026-08-31
---
# 📊 Data-Driven Testing (DDT)

DDT = Data-Driven Testing. Intinya: **1 fungsi test, banyak variasi data**. Pytest akan otomatis menjalankan fungsi itu berkali-kali, satu kali per data.

## Kenapa Pakai DDT?
Tanpa DDT, kalau kita mau ngetes login invalid dengan 3 variasi data, kita harus bikin 3 fungsi yang isinya COPAS:
- `test_login_invalid_username()`
- `test_login_invalid_password()`
- `test_login_invalid_credentials()`

Dengan DDT, cukup **1 fungsi** aja.

## Cara Pakai `@pytest.mark.parametrize`
```python
import pytest

@pytest.mark.parametrize("data_key", [
    "invalid_username", 
    "invalid_password", 
    "invalid_credentials"
])
def test_login_invalid(page, data_key):
    data = login_data[data_key]
    login_page = LoginPage(page)
    login_page.open()
    login_page.login(data["username"], data["password"])
    expect(login_page.error_message).to_be_visible()
```

## Apa yang Terjadi di Balik Layar?
Pytest melihat array dan menjalankan fungsi sebanyak **3 kali**:
- **Run 1:** `data_key = "invalid_username"`
- **Run 2:** `data_key = "invalid_password"`
- **Run 3:** `data_key = "invalid_credentials"`

Output terminal kalau pakai `-v`:
```
test_login.py::test_login_invalid[invalid_username]    PASSED
test_login.py::test_login_invalid[invalid_password]    PASSED
test_login.py::test_login_invalid[invalid_credentials] PASSED
```

## Aturan Penting: Kapan Boleh Digabung DDT?
> **Kalau assertion (hasil akhir) SAMA, boleh digabung pakai DDT.**
> **Kalau assertion BEDA, WAJIB bikin fungsi test terpisah.**

### Contoh Pemisahan:
| Fungsi Test | Assertion | Boleh DDT? |
|---|---|---|
| `test_login_valid` | Pindah URL ke Dashboard | Sendiri aja |
| `test_login_invalid` | Muncul alert "Invalid credentials" | DDT (3 variasi data) |
| `test_login_empty_fields` | Muncul teks "Required" | DDT (3 variasi data) |

## Pola AAA (Arrange, Act, Assert)
Setiap fungsi test harus lurus tanpa If-Else, mengikuti pola:

```python
def test_login_invalid(page, data_key):
    # --- ARRANGE (Persiapan) ---
    data = login_data[data_key]
    login_page = LoginPage(page)
    login_page.open()

    # --- ACT (Aksi) ---
    login_page.login(data["username"], data["password"])

    # --- ASSERT (Validasi) ---
    expect(login_page.error_message).to_be_visible()
    expect(login_page.error_message).to_contain_text("Invalid credentials")
```
