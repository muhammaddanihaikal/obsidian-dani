# Inventaris Locator — Aset Baru + Approval Aset Baru (Internal)

> 24 Nov 2026. Sumber: Page Object repo `bsn-automation` (sudah terverifikasi saat
> test TC-INT-STOCK-01/NAV-01..03 PASSED) + eksplorasi 23 Nov 2026.
> Prioritas sesuai instruksi Muhammad: **#id → data-testid → semantik (role/teks)**.
> Locator Approval belum terverifikasi live (server down) — ditandai ⚠️.

## 1. Daftar Aset Baru (`/internal/stock-management/aset-baru`)

| Elemen | Strategi | Locator | Unik |
|---|---|---|---|
| Tombol Input Aset Baru | role | `get_by_role("button", name="Input Aset Baru")` | Ya |
| Kolom search | role | `get_by_role("textbox", name="Cari nama aset, kode aset, atau lokasi")` | Ya |
| Tombol Reset filter | data-testid | `aset-baru-filter-reset-button` | Ya |
| Tab Semua | data-testid | `aset-baru-tab-all` | Ya |
| Tab Published | data-testid | `aset-baru-tab-published` | Ya |
| Tab Draft | data-testid | `aset-baru-tab-draft` | Ya |
| Tab Kurasi | data-testid | `aset-baru-tab-curation` | Ya |
| Baris tabel | CSS (AntD) | `tr.ant-table-row` | Koleksi |
| Tombol Edit per baris | data-testid (suffix) | `[data-testid$='-edit-button']` dalam baris | Per baris |
| Tombol Detail per baris | data-testid (suffix) | `[data-testid$='-detail-button']` dalam baris | Per baris ⚠️ pola mengikuti Edit, belum diverifikasi live |

## 2. Wizard Create/Edit Aset Baru (6 step)

| Elemen | Strategi | Locator |
|---|---|---|
| Step 1 — Developer | #id | `#developer_id` |
| Step 1 — Tipe Aset | #id | `#asset_type` |
| Step 1 — Proyek | #id | `#project_id` |
| Step 1 — Klaster | #id | `#cluster_id` |
| Step 1 — Tipe Unit | #id | `#unit_type` |
| Step 1 — Stok Unit | #id | `#stock_unit` |
| Step 1 — LT / Lantai / KT / KM | #id | `#land_area`, `#floors`, `#bedrooms`, `#bathrooms` |
| Step 1 — Deskripsi | #id | `#description` |
| Step 2 — Harga | #id | `#price` |
| Step 2 — Switch Promo | #id | `#promo_enabled` |
| Step 2 — Harga Normal | #id | `#normal_price` |
| Step 2 — Persen DP | #id | `#dp_percent` |
| Step 3 — Input file foto | CSS | `input[type='file']` |
| Step 4 — (centang legalitas + unggah; tombol per card) | role/teks | lihat `create_asset_baru_page.py` |
| Step 5 — Alamat | #id | `#address` |
| Step 5 — Provinsi/Kota/Kecamatan/Kelurahan | #id | `#province`, `#city`, `#district`, `#sub_district` |
| Step 5 — Kode Pos / Koordinat | #id | `#postal_code`, `#coordinate` |
| Step 5 — Tambah Destinasi + field modal | data-testid | prefix `aset-baru-lokasi-destinasi-*` (lihat create page) |
| Step 5 — Baris destinasi tersimpan (Edit) | data-testid (prefix) | `[data-testid^='aset-baru-lokasi-destinasi-row-']:not([data-testid$='-delete-button'])` |
| Step 6 — Lebar Jalan | #id | `#road_width` |
| Step 6 — Arah Mata Angin / Daya Listrik | #id | `#cardinal_point`, `#power_va` |
| Step 6 — Sumber Air | #id | `#water_source` |
| Tombol Selanjutnya | data-testid | `aset-baru-form-next-button` |
| Tombol Sebelumnya (Edit) | data-testid | `aset-baru-form-prev-button` |
| Tombol Simpan sebagai Draft (Edit) | data-testid | `aset-baru-form-save-draft-button` |
| Tombol Submit final | data-testid | `aset-baru-form-submit-button` |
| Tombol Hapus/Ganti foto (Edit) | role | `get_by_role("button", name="Hapus foto" / "Ganti foto")` |
| Tombol Lihat File legalitas (Edit) | role | `get_by_role("button", name="Lihat File")` |

Catatan: `#coordinate` muncul kembar di modal destinasi — di modal wajib pakai data-testid.

## 3. Approval Aset Baru ⚠️ BELUM TERVERIFIKASI LIVE

Disusun dari dokumentasi eksplorasi 23 Nov + konvensi modul Aset Baru. Wajib
dicek ke DOM aktual pada kesempatan pertama setelah server pulih, sebelum test dijalankan.

| Elemen | Strategi | Locator |
|---|---|---|
| PATH halaman | — | `/internal/stock-management/approval-aset-baru` ⚠️ |
| Tab Pengajuan Masuk | role | `get_by_role("tab", name=~/Pengajuan Masuk/)` |
| Tab Approval Pengurangan Unit | role | `get_by_role("tab", name=~/Approval Pengurangan Unit/)` |
| Kolom search | placeholder | `get_by_placeholder(~/cari/i)` ⚠️ |
| Tab Semua Pengajuan | role | `get_by_role("tab", name=~/Semua Pengajuan/)` |
| Tab Disetujui | role | `get_by_role("tab", name=~/Disetujui/)` |
| Baris tabel | CSS (AntD) | `tr.ant-table-row` |
| Teks tabel kosong | teks | `Tidak ada .* yang cocok dengan filter` |
| Tombol Detail per baris | role | `get_by_role("button", name="Detail")` dalam baris |
| Tombol Setujui per baris | role | `get_by_role("button", name="Setujui")` dalam baris |
| Tombol Tolak per baris | role | `get_by_role("button", name="Tolak")` dalam baris |
| Tombol Filter / Terapkan / Reset | role | `get_by_role("button", name="Filter" / "Terapkan Filter" / "Reset")` ⚠️ |
| Field filter (AntD select) | label form-item | `.ant-form-item` filter by label → `.ant-select` → `get_by_role("option", name=...)` |
