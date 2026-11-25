# Status Automation — Aset Baru + Approval Aset Baru

> 24 Nov 2026 pagi. Repo: `~/workspace/bsn/bsn-automation` (lokal, BELUM di-push).

## Yang dikerjakan

**Diubah:**
- `pages/internal/stock_management/aset_baru/asset_baru_list_page.py` — `search_aset()` diimplementasikan (sebelumnya stub TODO), ditambah `click_detail_aset()`, `open_filter_panel()`, `select_filter_option()`, `apply_filter()`, `reset_filter()` + locator tombol Filter/Terapkan.

**Baru:**
- `pages/internal/stock_management/approval_aset_baru/approval_aset_baru_page.py` (+ `__init__.py`) — Page Object Approval lengkap: 2 tab utama, tab status, search, filter, reset, aksi Detail/Setujui/Tolak per baris (modal saja).
- `tests/internal/stock_management/aset_baru/test_search_filter_aset_baru.py` — 5 test: TC-INT-STOCK-02 s.d. 06 (search valid, search invalid, tab Published, reset, buka detail/Read).
- `tests/internal/stock_management/aset_baru/test_edit_aset_baru.py` — 1 test: TC-INT-STOCK-07 (buka form Edit dari tab Draf, tanpa menyimpan).
- `tests/internal/stock_management/approval_aset_baru/test_approval_aset_baru.py` (+ `__init__.py`) — 7 test: TC-INT-APPR-01 s.d. 07 (halaman terbuka, search valid/invalid, tab Disetujui, filter Tipe Aset Rumah, reset, tab Pengurangan Unit).

Total test baru: **13**. Test yang membuktikan bug ditulis apa adanya (APPR-04 tab Disetujui, APPR-05 filter Rumah, APPR-06 reset — terkait BSN_I-173) — assertion TIDAK diubah agar hijau, TIDAK ada self-healing.

## Validasi struktur (sesuai kesepakatan: tanpa run ke aplikasi)

- `py_compile` semua file baru/ubahan: **OK**
- `uv run pytest --collect-only`: **28 tests collected, 0 error** (13 baru + 15 lama)

## Catatan & deviasi (untuk keputusan Muhammad)

1. **Locator Approval belum terverifikasi live** — server sandbox down (SSO 502 sejak 23 Nov 21:05). Locator disusun dari dokumentasi eksplorasi 23 Nov + konvensi Aset Baru; wajib verifikasi DOM sebelum run pertama. Rinciannya di `LOCATOR.md` bagian 3.
2. **Prioritas locator #id → data-testid → semantik** mengikuti instruksi langsung Muhammad; repo AGENTS.md sebenarnya role-first. Perlu keputusan: ubah standar repo atau khusus modul ini.
3. **Test ditulis lengkap, bukan skeleton** — instruksi langsung Muhammad, menyimpang dari AGENTS.md Rule 5. Auth TOTP (helpers/totp.py + conftest) juga sudah diganti dari Mailpit atas izinnya; AGENTS.md bagian 3 belum diperbarui.
4. **Update (Edit–Save) penuh belum ditulis**: Edit–Save butuh data tumbal sendiri; Aset Baru tidak punya fungsi/API delete, jadi setiap siklus Create–Edit akan meninggalkan Draf baru di sandbox. TC-INT-STOCK-07 baru mencakup buka form Edit. Keputusan: apakah test Update dibuat dengan siklus Create Draft → Edit → biarkan leftover, atau ditunda.
5. Push ke GitHub **ditahan** menunggu ACC Muhammad.
