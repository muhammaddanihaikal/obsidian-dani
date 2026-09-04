---
tags:
  - QA
  - Automation
  - TestData
  - JSON
date: 2026-08-31
---
# 📂 Test Data Separation & Data Factory

Prinsip penting: **Jangan pernah hardcode data di file test.** Semua data testing harus dipisah ke file tersendiri.

## 1. Test Data dalam JSON
Semua data testing disimpan di folder `data/` dalam format JSON.

### `login_data.json`
```json
{
  "valid_login": {
    "username": "Admin",
    "password": "admin123"
  },
  "invalid_username": {
    "username": "Salah",
    "password": "admin123"
  },
  "invalid_password": {
    "username": "Admin",
    "password": "Salah"
  },
  "invalid_credentials": {
    "username": "Salah",
    "password": "Salah"
  }
}
```

## 2. Utility `read_data.py`
Fungsi generik untuk membaca file JSON dari folder `data/`.

```python
from pathlib import Path
import json

DATA_DIR = Path(__file__).parent.parent / "data"

def read_data(file_name: str):
    with open(DATA_DIR / file_name, encoding="utf-8") as f:
        return json.load(f)
```

### Cara pakai di test:
```python
from utils.read_data import read_data

login_data = read_data("login_data.json")
data = login_data["valid_login"]
# data["username"] => "Admin"
# data["password"] => "admin123"
```

## 3. Data Factory — Generate Data Dinamis
Kalau data harus **unik setiap kali test jalan** (misal: username baru untuk test add user), gunakan Data Factory.

```python
# utils/data_factory.py
import uuid

def generate_username(prefix):
    return f"{prefix}_{uuid.uuid4().hex[:8]}"
    # Contoh hasil: "dani_3f2a1b4c"
```

### Kenapa pakai UUID?
- UUID menghasilkan string acak yang **hampir mustahil kembar**.
- Mencegah konflik data antar-run test (misal: test dijalankan 2x berturut-turut, username nggak bentrok).

### Cara pakai di test:
```python
from utils.data_factory import generate_username

add_user_data["username"] = generate_username(add_user_data["username_prefix"])
# Setiap kali test jalan, hasilnya selalu beda:
# Run 1: "dani_3f2a1b4c"
# Run 2: "dani_9e7d5a2f"
```

## Tips Penting
- Generate data dinamis di **module level** (di luar fungsi test), bukan di dalam fungsi test. Biar `test_add_user` dan `test_edit_user` pakai username yang SAMA.
- Kalau data statis (nggak berubah), taruh di JSON.
- Kalau data harus unik/dinamis, pakai Data Factory.
