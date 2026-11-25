# Review Locator & Test Automation — Aset Baru + Approval Aset Baru

> Selasa, 24 Nov 2026 — untuk review Muhammad.
> Status umum: locator Aset Baru **terverifikasi**, locator Approval **draf** (server sandbox masih down, belum bisa dicocokkan ke DOM asli).
> 13 test baru sudah ditulis, **belum dijalankan** — validasi baru sebatas `pytest --collect-only` (28 test terkumpul, 0 error). Nunggu ACC sebelum run & push.

---

## 1. Locator — Daftar Aset Baru

Halaman: `/internal/stock-management/aset-baru` — status: ✅ terverifikasi (kepakai di test yang sudah PASSED)

| Elemen | Strategi | Locator |
|---|---|---|
| Tombol Input Aset Baru | role | `get_by_role("button", name="Input Aset Baru")` |
| Kolom search | role | `get_by_role("textbox", name="Cari nama aset, kode aset, atau lokasi")` |
| Tombol Reset filter | data-testid | `aset-baru-filter-reset-button` |
| Tab Semua | data-testid | `aset-baru-tab-all` |
| Tab Published | data-testid | `aset-baru-tab-published` |
| Tab Draft | data-testid | `aset-baru-tab-draft` |
| Tab Kurasi | data-testid | `aset-baru-tab-curation` |
| Baris tabel | CSS (AntD) | `tr.ant-table-row` |
| Tombol Edit per baris | data-testid (suffix) | `[data-testid$='-edit-button']` di dalam baris |
| Tombol Detail per baris | data-testid (suffix) | `[data-testid$='-detail-button']` di dalam baris ⚠️ pola mengikuti Edit, belum diverifikasi live |

## 2. Locator — Wizard Create/Edit Aset Baru (6 step)

Status: ✅ terverifikasi (dari Page Object repo)

| Step | Elemen | Locator |
|---|---|---|
| 1 Informasi | Developer | `#developer_id` |
| 1 Informasi | Tipe Aset | `#asset_type` |
| 1 Informasi | Proyek | `#project_id` |
| 1 Informasi | Klaster | `#cluster_id` |
| 1 Informasi | Tipe Unit | `#unit_type` |
| 1 Informasi | Stok Unit | `#stock_unit` |
| 1 Informasi | Luas Tanah / Lantai / KT / KM | `#land_area`, `#floors`, `#bedrooms`, `#bathrooms` |
| 1 Informasi | Deskripsi | `#description` |
| 2 Harga | Harga | `#price` |
| 2 Harga | Switch Promo | `#promo_enabled` |
| 2 Harga | Harga Normal | `#normal_price` |
| 2 Harga | Persen DP | `#dp_percent` |
| 3 Galeri | Input file foto | `input[type='file']` |
| 5 Lokasi | Alamat | `#address` |
| 5 Lokasi | Provinsi / Kota / Kecamatan / Kelurahan | `#province`, `#city`, `#district`, `#sub_district` |
| 5 Lokasi | Kode Pos / Koordinat | `#postal_code`, `#coordinate` |
| 5 Lokasi | Tambah Destinasi + field modal | data-testid prefix `aset-baru-lokasi-destinasi-*` |
| 5 Lokasi | Baris destinasi tersimpan (Edit) | `[data-testid^='aset-baru-lokasi-destinasi-row-']:not([data-testid$='-delete-button'])` |
| 6 Fasilitas | Lebar Jalan | `#road_width` |
| 6 Fasilitas | Arah Mata Angin / Daya Listrik | `#cardinal_point`, `#power_va` |
| 6 Fasilitas | Sumber Air | `#water_source` |
| Umum | Tombol Selanjutnya | `aset-baru-form-next-button` |
| Umum | Tombol Sebelumnya (Edit) | `aset-baru-form-prev-button` |
| Umum | Tombol Simpan sebagai Draft (Edit) | `aset-baru-form-save-draft-button` |
| Umum | Tombol Submit final | `aset-baru-form-submit-button` |
| Edit | Hapus / Ganti foto | `get_by_role("button", name="Hapus foto" / "Ganti foto")` |
| Edit | Lihat File legalitas | `get_by_role("button", name="Lihat File")` |

Catatan: `#coordinate` muncul kembar di modal destinasi — khusus di modal wajib pakai data-testid.

## 3. Locator — Approval Aset Baru

Status: ⚠️ **DRAF — belum terverifikasi live.** Disusun dari dokumentasi eksplorasi 23 Nov 2026 + konvensi modul Aset Baru. Wajib dicek ke DOM aktual setelah server pulih, sebelum test dijalankan.

| Elemen | Strategi | Locator |
|---|---|---|
| Path halaman | — | `/internal/stock-management/approval-aset-baru` ⚠️ |
| Tab Pengajuan Masuk | role | `get_by_role("tab", name=~/Pengajuan Masuk/)` |
| Tab Approval Pengurangan Unit | role | `get_by_role("tab", name=~/Approval Pengurangan Unit/)` |
| Kolom search | placeholder | `get_by_placeholder(~/cari/i)` ⚠️ |
| Tab Semua Pengajuan | role | `get_by_role("tab", name=~/Semua Pengajuan/)` |
| Tab Disetujui | role | `get_by_role("tab", name=~/Disetujui/)` |
| Baris tabel | CSS (AntD) | `tr.ant-table-row` |
| Teks tabel kosong | teks | `Tidak ada .* yang cocok dengan filter` |
| Tombol Detail per baris | role | `get_by_role("button", name="Detail")` di dalam baris |
| Tombol Setujui per baris | role | `get_by_role("button", name="Setujui")` di dalam baris |
| Tombol Tolak per baris | role | `get_by_role("button", name="Tolak")` di dalam baris |
| Tombol Filter / Terapkan / Reset | role | `get_by_role("button", name="Filter" / "Terapkan Filter" / "Reset")` ⚠️ |
| Field filter | label form-item | `.ant-form-item` (filter by label) → `.ant-select` → `get_by_role("option", name=...)` |

---

## 4. Test yang dibuat (13 test baru)

File: `tests/internal/stock_management/aset_baru/test_search_filter_aset_baru.py`, `test_edit_aset_baru.py`, `tests/internal/stock_management/approval_aset_baru/test_approval_aset_baru.py`
Page Object baru: `pages/internal/stock_management/approval_aset_baru/approval_aset_baru_page.py`

### Aset Baru

| TC ID | Judul | Yang dicek |
|---|---|---|
| TC-INT-STOCK-02 | Mencari aset dengan kode yang valid | Search "JPMS-10001" → baris pertama tampil & mengandung kode itu |
| TC-INT-STOCK-03 | Mencari aset dengan keyword yang tidak ada | Search keyword ngawur → tabel 0 baris |
| TC-INT-STOCK-04 | Tab Published hanya menampilkan aset terverifikasi | Klik tab Published → ada baris tampil (acuan 23 Nov: 4 aset) |
| TC-INT-STOCK-05 | Reset mengembalikan daftar setelah pencarian | Search lalu Reset → jumlah baris kembali seperti awal |
| TC-INT-STOCK-06 | Membuka detail aset dari daftar (Read) | Klik Detail JPMS-10001 → URL detail + judul aset tampil |
| TC-INT-STOCK-07 | Membuka form Edit dari aset berstatus Draf | Tab Draf → Edit baris pertama → wizard Edit terbuka, tombol Simpan Draft & Selanjutnya tampil (tanpa menyimpan) |

### Approval Aset Baru

| TC ID | Judul | Yang dicek |
|---|---|---|
| TC-INT-APPR-01 | Halaman Approval menampilkan dua tab utama | Tab Pengajuan Masuk & Pengurangan Unit tampil + tabel ada isinya |
| TC-INT-APPR-02 | Mencari pengajuan dengan kode yang valid | Search "JPMS" → baris tampil & mengandung JPMS |
| TC-INT-APPR-03 | Mencari pengajuan dengan keyword yang tidak ada | Search ngawur → 0 baris + teks keterangan kosong tampil |
| TC-INT-APPR-04 | Tab Disetujui menampilkan pengajuan yang sudah disetujui | Klik tab Disetujui → tabel tidak kosong (**pembukti bug BSN_I-173**, ditulis apa adanya) |
| TC-INT-APPR-05 | Filter Tipe Aset Rumah menampilkan hasil yang sesuai | Filter Rumah → tabel tidak kosong (**pembukti bug BSN_I-173**, ditulis apa adanya) |
| TC-INT-APPR-06 | Reset mengembalikan tab Disetujui ke Semua Pengajuan | Dari tab Disetujui klik Reset → daftar kembali penuh (**terkait BSN_I-173**) |
| TC-INT-APPR-07 | Tab Pengurangan Unit menampilkan daftar pengurangan | Pindah tab → tabel tidak kosong (acuan 23 Nov: 2 baris pending) |

---

## 5. Catatan untuk keputusan Muhammad

1. **Test Edit–Save penuh belum dibuat** — Edit–Save butuh data tumbal sendiri; Aset Baru tidak punya fungsi/API delete, jadi siklus Create→Edit akan meninggalkan Draf baru di sandbox setiap run. STOCK-07 baru mencakup buka form Edit.
2. **Prioritas locator** di test baru mengikuti instruksi Muhammad (#id → data-testid → semantik), menyimpang dari standar role-first di AGENTS.md repo. Perlu keputusan: ubah standar repo, atau khusus modul ini saja.
3. **Locator Approval (Bagian 3)** harus diverifikasi ke DOM asli dulu sebelum test Approval dijalankan — menunggu server sandbox pulih dari 502.
4. Push repo automation **ditahan** menunggu ACC.
