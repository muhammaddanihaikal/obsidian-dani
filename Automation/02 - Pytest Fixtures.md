---
tags:
  - QA
  - Automation
  - Pytest
  - Fixtures
date: 2026-08-31
---
# 🔧 Pytest Fixtures (conftest.py)

Fixtures adalah fungsi-fungsi "penyedia kebutuhan" yang dijalankan otomatis SEBELUM setiap test dimulai. Ibarat pelayan restoran yang nyiapin meja, piring, dan sendok sebelum kamu duduk.

## Hierarki Fixture di Project
`
playwright  (scope=session)   → 1x selama semua test jalan
  └── browser (scope=session) → 1x browser instance (hemat resource)
        └── context (scope=function) → fresh per test (isolasi)
              └── page (scope=function) → fresh per test (isolasi)
`

## Scope Fixture
| Scope | Artinya | Contoh |
|---|---|---|
| `session` | Dibuat 1x, dipakai bersama sampai SEMUA test selesai | browser (biar nggak buka tutup browser tiap test) |
| `function` | Dibuat baru setiap 1 fungsi test jalan | context & page (biar tiap test punya state bersih) |

## Kode conftest.py Lengkap
`python
import pytest
from playwright.sync_api import sync_playwright

@pytest.fixture(scope="session")
def playwright():
    with sync_playwright() as p:
        yield p

@pytest.fixture(scope="session")
def browser(playwright):
    browser = playwright.chromium.launch(headless=True, slow_mo=0)
    yield browser
    browser.close()

@pytest.fixture(scope="function")
def context(browser):
    context = browser.new_context()
    yield context
    context.close()

@pytest.fixture(scope="function")
def page(context):
    page = context.new_page()
    yield page
    page.close()
`

## Cara Kerjanya
1. Pytest melihat parameter `page` di fungsi test kamu: `def test_login(page)`
2. Pytest cari fixture bernama `page` di `conftest.py`
3. Fixture `page` butuh `context` → Pytest cari fixture `context`
4. Fixture `context` butuh `browser` → Pytest cari fixture `browser`
5. Dst... seperti rantai domino

## Keyword `yield`
- Kode **sebelum** `yield` = setup (persiapan)
- Kode **setelah** `yield` = teardown (bersih-bersih)

`python
@pytest.fixture
def page(context):
    page = context.new_page()  # SETUP: buka tab baru
    yield page                  # Kasih tab ini ke test
    page.close()                # TEARDOWN: tutup tab setelah test selesai
`

## Tips Penting
- **`session` scope untuk browser** = efisiensi (nggak buka/tutup browser tiap test)
- **`function` scope untuk context & page** = isolasi (tiap test punya state bersih, cookies/session nggak bocor ke test lain)
