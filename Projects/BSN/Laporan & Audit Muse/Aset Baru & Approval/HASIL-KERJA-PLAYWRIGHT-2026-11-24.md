# Hasil Kerja Playwright — Semalam (23→24 Nov 2026)

> Repo: `bsn-automation` (clone lokal Muse) — status: **belum di-commit, belum di-push**, menunggu review & ACC Muhammad.
> Isi: 1 Page Object baru (Approval), 1 Page Object diperbarui (Daftar Aset Baru), 13 test baru, auth login diganti ke TOTP.
> Validasi: `py_compile` OK + `pytest --collect-only` = **28 test terkumpul, 0 error**. Test **belum dijalankan** ke aplikasi.
> Catatan: locator Aset Baru terverifikasi (dari Page Object lama yang testnya PASSED); locator Approval masih draf — belum terverifikasi live karena server sandbox down (SSO 502).

---

## Daftar Isi

1. Page Object BARU — Approval Aset Baru
2. Page Object DIPERBARUI — Daftar Aset Baru (search_aset yang tadinya stub sekarang jalan + helper filter/detail)
3. Test BARU — Search & Filter Aset Baru (TC-INT-STOCK-02 s.d. 06)
4. Test BARU — Edit Aset Baru (TC-INT-STOCK-07)
5. Test BARU — Approval Aset Baru (TC-INT-APPR-01 s.d. 07)
6. Auth — Helper TOTP (pengganti Mailpit untuk login Internal)

---

## 1. Page Object BARU — Approval Aset Baru

`pages/internal/stock_management/approval_aset_baru/approval_aset_baru_page.py`

```python
"""Page Object untuk halaman Approval Aset Baru — Portal Internal BSN.

CATATAN (24 Nov 2026): locator halaman ini disusun dari dokumentasi eksplorasi
23 Nov 2026 + konvensi locator modul Aset Baru (data-testid & Ant Design).
Server sandbox sedang down (SSO 502) saat file ini ditulis, jadi locator
Approval BELUM terverifikasi live — verifikasi saat server pulih, sebelum run.
"""

import re

from playwright.sync_api import Page

from pages.base_page import BasePage


class ApprovalAsetBaruPage(BasePage):
    """Halaman Approval Aset Baru (tab Pengajuan Masuk & Pengurangan Unit)."""

    def __init__(self, page: Page):
        super().__init__(page)
        self.PATH = "/internal/stock-management/approval-aset-baru"

        # === 1. TAB UTAMA ===
        self.tab_pengajuan_btn = self.page.get_by_role(
            "tab", name=re.compile("Pengajuan Masuk")
        )
        self.tab_pengurangan_btn = self.page.get_by_role(
            "tab", name=re.compile("Approval Pengurangan Unit")
        )

        # === 2. PENCARIAN & FILTER (bersama untuk kedua tab) ===
        self.search_input = self.page.get_by_placeholder(
            re.compile("cari", re.IGNORECASE)
        )
        self.filter_btn = self.page.get_by_role("button", name="Filter")
        self.apply_filter_btn = self.page.get_by_role(
            "button", name="Terapkan Filter"
        )
        self.reset_filter_btn = self.page.get_by_role("button", name="Reset")

        # === 3. TAB STATUS PENGAJUAN ===
        self.tab_semua_pengajuan_btn = self.page.get_by_role(
            "tab", name=re.compile("Semua Pengajuan")
        )
        self.tab_disetujui_btn = self.page.get_by_role(
            "tab", name=re.compile("Disetujui")
        )

        # === 4. TABEL ===
        # Pakai tr.ant-table-row karena AntD punya hidden .ant-table-measure-row di baris 0
        self.table_rows = self.page.locator("tr.ant-table-row")
        self.empty_state = self.page.get_by_text(
            re.compile("Tidak ada .* yang cocok dengan filter")
        )

    # =========================================================================
    # ACTION METHODS
    # =========================================================================

    def open_tab_pengurangan(self):
        """Pindah ke tab Approval Pengurangan Unit."""
        self.tab_pengurangan_btn.click()
        self.page.wait_for_load_state("networkidle")

    def search(self, keyword: str):
        """Isi kolom pencarian lalu terapkan (Enter)."""
        self.search_input.fill(keyword)
        self.search_input.press("Enter")
        self.page.wait_for_load_state("networkidle")

    def select_filter_option(self, label: str, option: str):
        """Pilih satu opsi pada field filter Ant Design berdasarkan label field-nya."""
        form_item = self.page.locator(".ant-form-item").filter(has_text=label).first
        form_item.locator(".ant-select").click()
        self.page.get_by_role("option", name=option).click()

    def apply_filter(self):
        """Klik tombol Terapkan Filter pada panel filter."""
        self.apply_filter_btn.click()
        self.page.wait_for_load_state("networkidle")

    def reset_filter(self):
        """Klik tombol Reset untuk mengembalikan filter ke default."""
        self.reset_filter_btn.click()
        self.page.wait_for_load_state("networkidle")

    def click_detail_pengajuan(self, keyword: str):
        """Klik tombol Detail di baris pengajuan yang sesuai kata kunci."""
        target_row = self.table_rows.filter(has_text=keyword).first
        target_row.get_by_role("button", name="Detail").click()

    def open_setujui_modal(self, keyword: str):
        """Klik tombol Setujui di baris yang sesuai kata kunci (modal saja, JANGAN konfirmasi)."""
        target_row = self.table_rows.filter(has_text=keyword).first
        target_row.get_by_role("button", name="Setujui").click()

    def open_tolak_modal(self, keyword: str):
        """Klik tombol Tolak di baris yang sesuai kata kunci (modal saja, JANGAN konfirmasi)."""
        target_row = self.table_rows.filter(has_text=keyword).first
        target_row.get_by_role("button", name="Tolak").click()
```

## 2. Page Object DIPERBARUI — Daftar Aset Baru

`pages/internal/stock_management/aset_baru/asset_baru_list_page.py`

```python
from playwright.sync_api import Page

from pages.base_page import BasePage


class AssetBaruListPage(BasePage):
    """Halaman Daftar Aset Baru — Portal Internal BSN."""

    def __init__(self, page: Page):
        super().__init__(page)
        self.PATH = "/internal/stock-management/aset-baru"

        # === 1. TOMBOL AKSI ATAS & FILTER ===
        self.input_aset_baru_btn = self.page.get_by_role(
            "button", name="Input Aset Baru"
        )
        self.search_input = self.page.get_by_role(
            "textbox", name="Cari nama aset, kode aset, atau lokasi"
        )
        self.reset_filter_btn = self.page.get_by_test_id(
            "aset-baru-filter-reset-button"
        )

        # === 2. TAB STATUS ASET ===
        self.tab_all_btn = self.page.get_by_test_id("aset-baru-tab-all")
        self.tab_published_btn = self.page.get_by_test_id("aset-baru-tab-published")
        self.tab_draft_btn = self.page.get_by_test_id("aset-baru-tab-draft")
        self.tab_curation_btn = self.page.get_by_test_id("aset-baru-tab-curation")

        # === 2B. PANEL FILTER ===
        self.filter_btn = self.page.get_by_role("button", name="Filter")
        self.apply_filter_btn = self.page.get_by_role(
            "button", name="Terapkan Filter"
        )

        # === 3. TABEL DATA ASET ===
        # Pakai tr.ant-table-row karena AntD punya hidden .ant-table-measure-row di baris 0
        self.table_rows = self.page.locator("tr.ant-table-row")

    def click_input_aset_baru(self):
        """Klik tombol '+ Input Aset Baru' untuk membuka form wizard."""
        self.input_aset_baru_btn.click()

    def click_edit_aset(self, keyword: str):
        """Klik tombol Edit langsung di baris tabel aset yang sesuai kata kunci."""
        # Pakai $= karena tiap baris punya ID aset unik di tengah data-testid
        target_row = self.table_rows.filter(has_text=keyword).first
        edit_btn = target_row.locator("[data-testid$='-edit-button']")
        edit_btn.scroll_into_view_if_needed()
        edit_btn.click()

    def search_aset(self, keyword: str):
        """Mencari aset berdasarkan nama, kode, atau lokasi."""
        self.search_input.fill(keyword)
        self.search_input.press("Enter")
        # Tunggu hasil pencarian selesai dimuat (baris tabel berubah / kosong)
        self.page.wait_for_load_state("networkidle")

    def click_detail_aset(self, keyword: str):
        """Klik tombol Detail di baris tabel aset yang sesuai kata kunci."""
        # Pola sama dengan tombol Edit: data-testid per baris berakhiran '-detail-button'
        target_row = self.table_rows.filter(has_text=keyword).first
        detail_btn = target_row.locator("[data-testid$='-detail-button']")
        detail_btn.scroll_into_view_if_needed()
        detail_btn.click()

    def open_filter_panel(self):
        """Buka panel filter daftar aset."""
        self.filter_btn.click()

    def select_filter_option(self, label: str, option: str):
        """Pilih satu opsi pada field filter Ant Design berdasarkan label field-nya."""
        form_item = self.page.locator(".ant-form-item").filter(has_text=label).first
        form_item.locator(".ant-select").click()
        self.page.get_by_role("option", name=option).click()

    def apply_filter(self):
        """Klik tombol Terapkan Filter pada panel filter."""
        self.apply_filter_btn.click()
        self.page.wait_for_load_state("networkidle")

    def reset_filter(self):
        """Klik tombol Reset untuk mengembalikan filter ke default."""
        self.reset_filter_btn.click()
        self.page.wait_for_load_state("networkidle")
```

## 3. Test BARU — Search & Filter Aset Baru

`tests/internal/stock_management/aset_baru/test_search_filter_aset_baru.py`

```python
import re

import allure
import pytest
from playwright.sync_api import Page, expect

from pages.internal.stock_management.aset_baru.asset_baru_list_page import (
    AssetBaruListPage,
)


class TestSearchFilterAsetBaru:
    @allure.title("[TC-INT-STOCK-02] Mencari aset dengan kode yang valid")
    @pytest.mark.regression
    def test_search_kode_valid(self, logged_in_internal: Page):
        page = logged_in_internal
        list_page = AssetBaruListPage(page)

        # 1. Arrange
        list_page.open()

        # 2. Act
        list_page.search_aset("JPMS-10001")

        # 3. Assert
        expect(list_page.table_rows.first).to_be_visible()
        expect(list_page.table_rows.first).to_contain_text("JPMS-10001")

    @allure.title("[TC-INT-STOCK-03] Mencari aset dengan keyword yang tidak ada")
    @pytest.mark.regression
    def test_search_keyword_tidak_valid(self, logged_in_internal: Page):
        page = logged_in_internal
        list_page = AssetBaruListPage(page)

        # 1. Arrange
        list_page.open()

        # 2. Act
        list_page.search_aset("KODE-TIDAK-ADA-XYZ-999")

        # 3. Assert
        expect(list_page.table_rows).to_have_count(0)

    @allure.title("[TC-INT-STOCK-04] Tab Published hanya menampilkan aset terverifikasi")
    @pytest.mark.regression
    def test_tab_published(self, logged_in_internal: Page):
        page = logged_in_internal
        list_page = AssetBaruListPage(page)

        # 1. Arrange
        list_page.open()

        # 2. Act
        list_page.tab_published_btn.click()
        page.wait_for_load_state("networkidle")

        # 3. Assert (per 23 Nov 2026 ada 4 aset Published di sandbox)
        expect(list_page.table_rows.first).to_be_visible()
        expect(list_page.table_rows).not_to_have_count(0)

    @allure.title("[TC-INT-STOCK-05] Reset mengembalikan daftar setelah pencarian")
    @pytest.mark.regression
    def test_reset_setelah_search(self, logged_in_internal: Page):
        page = logged_in_internal
        list_page = AssetBaruListPage(page)

        # 1. Arrange
        list_page.open()
        total_awal = list_page.table_rows.count()

        # 2. Act
        list_page.search_aset("JPMS-10001")
        list_page.reset_filter()

        # 3. Assert
        expect(list_page.table_rows).to_have_count(total_awal)

    @allure.title("[TC-INT-STOCK-06] Membuka detail aset dari daftar (Read)")
    @pytest.mark.regression
    def test_buka_detail_aset(self, logged_in_internal: Page):
        page = logged_in_internal
        list_page = AssetBaruListPage(page)

        # 1. Arrange
        list_page.open()

        # 2. Act
        list_page.click_detail_aset("JPMS-10001")

        # 3. Assert
        expect(page).to_have_url(
            re.compile(r".*/stock-management/aset-baru/detail/.*")
        )
        expect(page.get_by_role("heading", level=1)).to_be_visible()
```

## 4. Test BARU — Edit Aset Baru

`tests/internal/stock_management/aset_baru/test_edit_aset_baru.py`

```python
import re

import allure
import pytest
from playwright.sync_api import Page, expect

from pages.internal.stock_management.aset_baru.asset_baru_list_page import (
    AssetBaruListPage,
)
from pages.internal.stock_management.aset_baru.edit_asset_baru_page import (
    EditAssetBaruPage,
)


class TestEditAsetBaru:
    @allure.title("[TC-INT-STOCK-07] Membuka form Edit dari aset berstatus Draf")
    @pytest.mark.regression
    def test_buka_form_edit_draf(self, logged_in_internal: Page):
        page = logged_in_internal
        list_page = AssetBaruListPage(page)
        edit_page = EditAssetBaruPage(page)

        # 1. Arrange (tab Draf — edit hanya aman diinspeksi pada data draf)
        list_page.open()
        list_page.tab_draft_btn.click()
        page.wait_for_load_state("networkidle")

        # 2. Act (buka Edit baris pertama, TANPA menyimpan perubahan apa pun)
        first_row_text = list_page.table_rows.first.inner_text()
        kode_aset = first_row_text.split()[0]
        list_page.click_edit_aset(kode_aset)

        # 3. Assert
        expect(page).to_have_url(
            re.compile(r".*/stock-management/aset-baru/edit/.*")
        )
        expect(edit_page.heading).to_be_visible()
        expect(edit_page.simpan_draft_btn).to_be_visible()
        expect(edit_page.selanjutnya_btn).to_be_visible()
```

## 5. Test BARU — Approval Aset Baru

`tests/internal/stock_management/approval_aset_baru/test_approval_aset_baru.py`

```python
import allure
import pytest
from playwright.sync_api import Page, expect

from pages.internal.stock_management.approval_aset_baru.approval_aset_baru_page import (
    ApprovalAsetBaruPage,
)


class TestApprovalAsetBaru:
    @allure.title("[TC-INT-APPR-01] Halaman Approval Aset Baru menampilkan dua tab utama")
    @pytest.mark.smoke
    def test_halaman_approval_terbuka(self, logged_in_internal: Page):
        page = logged_in_internal
        approval_page = ApprovalAsetBaruPage(page)

        # 1. Arrange & Act
        approval_page.open()

        # 2. Assert
        expect(approval_page.tab_pengajuan_btn).to_be_visible()
        expect(approval_page.tab_pengurangan_btn).to_be_visible()
        expect(approval_page.table_rows.first).to_be_visible()

    @allure.title("[TC-INT-APPR-02] Mencari pengajuan dengan kode yang valid")
    @pytest.mark.regression
    def test_search_pengajuan_valid(self, logged_in_internal: Page):
        page = logged_in_internal
        approval_page = ApprovalAsetBaruPage(page)

        # 1. Arrange
        approval_page.open()

        # 2. Act
        approval_page.search("JPMS")

        # 3. Assert
        expect(approval_page.table_rows.first).to_be_visible()
        expect(approval_page.table_rows.first).to_contain_text("JPMS")

    @allure.title("[TC-INT-APPR-03] Mencari pengajuan dengan keyword yang tidak ada")
    @pytest.mark.regression
    def test_search_pengajuan_tidak_valid(self, logged_in_internal: Page):
        page = logged_in_internal
        approval_page = ApprovalAsetBaruPage(page)

        # 1. Arrange
        approval_page.open()

        # 2. Act
        approval_page.search("KODE-TIDAK-ADA-XYZ-999")

        # 3. Assert
        expect(approval_page.table_rows).to_have_count(0)
        expect(approval_page.empty_state).to_be_visible()

    @allure.title("[TC-INT-APPR-04] Tab Disetujui menampilkan pengajuan yang sudah disetujui")
    @pytest.mark.regression
    def test_tab_disetujui(self, logged_in_internal: Page):
        page = logged_in_internal
        approval_page = ApprovalAsetBaruPage(page)

        # 1. Arrange
        approval_page.open()

        # 2. Act
        approval_page.tab_disetujui_btn.click()
        page.wait_for_load_state("networkidle")

        # 3. Assert (per 23 Nov 2026 ada 4 pengajuan Terverifikasi/Disetujui di sandbox)
        expect(approval_page.table_rows).not_to_have_count(0)

    @allure.title("[TC-INT-APPR-05] Filter Tipe Aset Rumah menampilkan hasil yang sesuai")
    @pytest.mark.regression
    def test_filter_tipe_aset_rumah(self, logged_in_internal: Page):
        page = logged_in_internal
        approval_page = ApprovalAsetBaruPage(page)

        # 1. Arrange
        approval_page.open()
        approval_page.filter_btn.click()

        # 2. Act
        approval_page.select_filter_option("Tipe Aset", "Rumah")
        approval_page.apply_filter()

        # 3. Assert
        expect(approval_page.table_rows).not_to_have_count(0)

    @allure.title("[TC-INT-APPR-06] Reset mengembalikan tab Disetujui ke Semua Pengajuan")
    @pytest.mark.regression
    def test_reset_filter_approval(self, logged_in_internal: Page):
        page = logged_in_internal
        approval_page = ApprovalAsetBaruPage(page)

        # 1. Arrange
        approval_page.open()
        approval_page.tab_disetujui_btn.click()
        page.wait_for_load_state("networkidle")

        # 2. Act
        approval_page.reset_filter()

        # 3. Assert
        expect(approval_page.table_rows).not_to_have_count(0)

    @allure.title("[TC-INT-APPR-07] Tab Pengurangan Unit menampilkan daftar pengurangan")
    @pytest.mark.regression
    def test_tab_pengurangan_unit(self, logged_in_internal: Page):
        page = logged_in_internal
        approval_page = ApprovalAsetBaruPage(page)

        # 1. Arrange
        approval_page.open()

        # 2. Act
        approval_page.open_tab_pengurangan()

        # 3. Assert (per 23 Nov 2026 ada 2 baris pengurangan pending di sandbox)
        expect(approval_page.table_rows).not_to_have_count(0)
```

## 6. Auth — Helper TOTP

`helpers/totp.py` (stdlib murni, tanpa dependency baru; conftest.py sekarang memakai ini untuk login Internal, Mailpit tidak diubah untuk External)

```python
"""Helper TOTP (RFC 6238) untuk login Internal BSN via authenticator app."""

import base64
import hashlib
import hmac
import struct
import time


def get_totp(secret: str, digits: int = 6, period: int = 30) -> str:
    """Hasilkan kode TOTP saat ini dari secret base32 (SHA1, 6 digit, 30 detik)."""
    key = base64.b32decode(secret.strip().upper())
    counter = int(time.time()) // period
    # Sisa waktu < 3 detik: pakai jendela berikutnya agar kode tidak kedaluwarsa saat di-submit
    if period - (time.time() % period) < 3:
        counter += 1
    msg = struct.pack(">Q", counter)
    digest = hmac.new(key, msg, hashlib.sha1).digest()
    offset = digest[-1] & 0x0F
    code = (struct.unpack(">I", digest[offset : offset + 4])[0] & 0x7FFFFFFF) % (
        10**digits
    )
    return str(code).zfill(digits)
```
