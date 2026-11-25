# Status Automation — Leads Aset Baru + Tiket Aset Baru (Customer Management)

> 24 Nov 2026 malam. Repo: `~/workspace/bsn/bsn-automation` (lokal, BELUM di-commit/push).

## Ringkasan hasil

- **Locator: TERVERIFIKASI LIVE via browser cloud** (24 Nov 2026,
  19:42–19:44 WIB) — setelah jalur Playwright VM gagal (detail di bawah),
  verifikasi diulang lewat browser cloud atas instruksi Muhammad: sesi
  Internal masih login (tidak perlu TOTP), read-only penuh, semua item
  A1–A13 (Leads) + B1–B9 (Tiket) dicek. Hasil: hampir semua locator ✅
  terverifikasi; 5 catatan penyesuaian (tab "Tindak Lanjut" muncul 5×,
  tombol "Tutup" drawer ada 2, placeholder filter Tiket ternyata
  "Contoh: Budi Santoso", kolom Board Proses/Melengkapi Berkas tidak unik
  karena chip ringkasan, header "SALES / PIC" satu kolom + board punya
  8 kolom). PATH Tiket TERKONFIRMASI:
  `/internal/manajemen-peminat/tiket/aset-baru`. Rincian per locator di
  `LOCATOR-LEADS-TIKET.md`. Yang tetap belum bisa dikonfirmasi lewat
  jalur ini: atribut #id/data-testid & struktur DOM persis.
- **Test baru: 19** (10 Leads + 9 Tiket), termasuk 11 test pembukti untuk
  8 issue hard. Validasi struktur: py_compile OK, collect-only 47 test, 0 error.
- **Audit TC selesai**: `~/workspace/bsn/AUDIT-TC-LEADS-TIKET.md`
  (23 TC SIT diaudit — catatan: Ticket berisi 12 TC di sheet, bukan 11).

## Blokir verifikasi live (apa adanya)

Login automation memakai pola repo (LoginPage + TOTP dari `.env` via
`helpers/totp.py`, secret tidak pernah dicetak/ditulis ke log):

1. Chromium (headless shell & full build, dengan/tanpa proxy eksplisit dari
   env): `net::ERR_TUNNEL_CONNECTION_FAILED` ke
   `terasrumah-sandbox.zegen.app` — proxy egress VM menolak tunnel dari
   Chromium (curl ke URL yang sama berhasil 308 via proxy yang sama).
2. Firefox: proxy lolos, tetapi SPA berhenti dirantai redirect OAuth —
   `/internal/` tampil kosong, `/oauth2-internal/userinfo` balas 401,
   interstitial "Loading" SSO tidak pernah sampai ke form login (ditunggu
   >150 detik, dicoba juga navigasi langsung ke `/oauth2-internal/start`).
3. Percobaan lanjutan setelah itu tidak disetujui untuk dijalankan lagi →
   probing dihentikan; pekerjaan dilanjutkan dari bukti eksplorasi sesuai
   fallback pada instruksi tugas.

Catatan: sandbox TIDAK down — sore ini sandbox dibuka normal dari browser
interaktif (eksplorasi 17:35–17:51 WIB). Blokirnya spesifik di jalur
browser-automation VM ini (proxy/SSO), bukan di aplikasi.

**Penyelesaian (24 Nov 2026 malam):** atas instruksi Muhammad, verifikasi
live diulang lewat **browser cloud** — berhasil penuh dalam ±2 menit
(sesi Internal dari eksplorasi sore masih login, jadi tidak ada login
ulang dan tidak ada approval yang perlu diajukan). Semua locator dicek
read-only di UI; hasilnya dicatat per locator di
`LOCATOR-LEADS-TIKET.md` (status ✅ / ⚠️ + koreksi teks persis). Tidak ada
item yang terparkir.

## Yang dikerjakan

**Baru (repo, semua belum di-commit):**
- `pages/internal/customer_management/leads_aset_baru/leads_aset_baru_page.py`
  (+ `__init__.py` paket `customer_management` & subpaket) — Page Object Leads
  lengkap: kartu ringkasan, 6 tab status, search, dropdown Pola Penjualan,
  filter tanggal, reset, tabel, pagination, drawer detail (biodata, chip
  tiket, simulasi, tombol Tutup/Ubah PIC/Lihat di Tiket Leads).
- `pages/internal/customer_management/tiket_aset_baru/tiket_aset_baru_page.py`
  — Page Object Tiket lengkap: kartu VOA, toggle Board/Tabel, panel Filter,
  kolom Board 6 tahap, tabel + headernya, detail tiket (banner, checklist,
  tenor). Tombol Tolak Pengajuan & Lanjut ke Approved hanya locator —
  tanpa action method, tidak diklik.
- `tests/internal/customer_management/leads_aset_baru/test_leads_aset_baru.py`
  — 10 test: TC-INT-LEAD-01 s.d. 10.
- `tests/internal/customer_management/tiket_aset_baru/test_tiket_aset_baru.py`
  — 9 test: TC-INT-TIKET-01 s.d. 09.
- `testcase/internal/tc_leads_aset_baru.md` & `testcase/internal/tc_tiket_aset_baru.md`
  — dokumentasi TC mengikuti pola `tc_approval_aset_baru.md`.

**Keputusan penomoran & struktur (dari bukti repo):**
- Modul repo mengikuti menu aplikasi: menu induknya adalah **Customer
  Management** (bukan "manajemen-peminat" — itu slug URL), jadi folder
  `customer_management/{leads_aset_baru,tiket_aset_baru}` sejajar
  `stock_management/{aset_baru,approval_aset_baru}`.
- Kode modul TC mengikuti format AGENTS.md `TC-INT-[MODUL]-[NN]`:
  **LEAD** untuk Leads Aset Baru dan **TIKET** untuk Tiket Aset Baru
  (ejaan "Tiket" mengikuti UI aplikasi).
- Tidak ada skeleton leads/tiket yang sudah ada sebelumnya di repo (dicek
  di `pages/`, `tests/`, `testcase/` — nol), jadi semua file baru.

**Daftar test:**

| TC | Judul | Jenis |
|---|---|---|
| TC-INT-LEAD-01 | Halaman Leads tampil + daftar terisi (4 lead) | Fungsional |
| TC-INT-LEAD-02 | Search ID lead tes ketemu | Fungsional |
| TC-INT-LEAD-03 | Filter Pola Penjualan Primary Main | Fungsional |
| TC-INT-LEAD-04 | Reset mengembalikan daftar | Fungsional |
| TC-INT-LEAD-05 | Detail lead tes: data cocok (nama/WA/email/alamat/JKHS-10007) | Fungsional |
| TC-INT-LEAD-06 | Nomor tiket antar-lead unik | Pembukti issue #2 |
| TC-INT-LEAD-07 | Simulasi DP = 10% × harga | Pembukti issue #3 |
| TC-INT-LEAD-08 | Kartu Perlu Tindak Lanjut mengikuti tab | Pembukti issue #4 |
| TC-INT-LEAD-09 | Semua lead terjangkau filter Pola Penjualan | Pembukti issue #5 |
| TC-INT-LEAD-10 | Semua kolom punya kontrol sorting | Pembukti issue #6 |
| TC-INT-TIKET-01 | Halaman Tiket tampil (Board + kartu Elina) | Fungsional |
| TC-INT-TIKET-02 | View Tabel menampilkan tiket Elina | Fungsional |
| TC-INT-TIKET-03 | Filter kata kunci menemukan Elina | Fungsional |
| TC-INT-TIKET-04 | Detail tiket Elina tampil (read-only) | Fungsional |
| TC-INT-TIKET-05 | Lead Terverifikasi harus punya tiket | Pembukti issue #1 |
| TC-INT-TIKET-06 | Banner lengkap konsisten dengan checklist | Pembukti issue #7 |
| TC-INT-TIKET-07 | Tenor 1 tahun = 12 bulan | Pembukti issue #7 |
| TC-INT-TIKET-08 | Kolom Nomor Tiket berisi nomor tiket | Pembukti issue #8 |
| TC-INT-TIKET-09 | VOA sesuai nilai tiket berjalan | Pembukti issue #8 |

Test pembukti ditulis apa adanya (assertion = Expected yang benar) — akan
FAIL bila dijalankan selama bug belum diperbaiki. Tidak ada self-healing,
tidak ada pelunakan assertion.

## Validasi struktur (sesuai kesepakatan: tanpa run ke aplikasi)

- `py_compile` 4 file baru (2 Page Object + 2 test): **OK**
- `pytest --collect-only`: **47 tests collected, 0 error** (19 baru + 28 lama)
- Full run: **TIDAK dilakukan** (sesuai instruksi). Push/commit: **TIDAK**.

## Audit TC (scope tambahan Muhammad)

Selesai → file: `~/workspace/bsn/AUDIT-TC-LEADS-TIKET.md`
Sumber: `tc-sheet.xlsx` sheet "Script Internal" (Leads baris 69–79 = 11 TC;
Ticket baris 114–125 = **12 TC** — total 23, bukan 22).

| Bucket | Leads | Ticket | Total |
|---|---|---|---|
| Sudah benar | 69, 70, 74, 75, 79 (5) | 114, 115, 116, 117, 120 (5) | 10 |
| TC benar, aplikasi gagal | 73 (issue #5), 77 (issue #1) | — | 2 |
| Perlu diperbaiki redaksinya | 71 | 123 (+ catatan redaksi di 77) | 2 (+1 catatan) |
| Berlebih / outdated | — | 121, 122 berpotensi outdated (belum terbukti) | 0 pasti |
| Belum terverifikasi | 72, 76, 78 | 118, 119, 121, 122, 124, 125 | 9 |
| Kurang (usulan tambahan) | — | — | 8 usulan (bagian D audit) |

## Deviasi & catatan untuk keputusan Muhammad

1. **Locator sudah terverifikasi live via browser cloud** (lihat ringkasan
   di atas) — PATH Tiket terkonfirmasi, placeholder & header terkoreksi.
   Tersisa 5 penyesuaian locator yang DISARANKAN di Page Object (tab
   "Tindak Lanjut" dibatasi role, "Tutup" drawer dibatasi ke tombol
   bawah, placeholder filter Tiket diganti "Contoh: Budi Santoso", kolom
   Board Proses/Melengkapi Berkas dibatasi ke kontainer board, header
   "SALES / PIC" + kolom AKSI + 8 kolom board) — kode BELUM diubah,
   menunggu review Muhammad besok. Atribut #id/data-testid tetap belum
   terkonfirmasi (jalur browser cloud tidak membuka DOM); locator
   role/teks yang ada sudah terbukti menunjuk elemen yang benar.
2. **Prioritas locator #id → data-testid → semantik** mengikuti instruksi
   langsung Muhammad (sama seperti kemarin); AGENTS.md repo sebenarnya
   role-first. Karena tidak ada #id/data-testid yang terbukti untuk modul
   ini, hasil akhirnya tetap semantik — konsisten dengan kedua standar
   untuk sementara.
3. **Test ditulis lengkap, bukan skeleton** — mengikuti instruksi langsung
   Muhammad malam ini (menyimpang dari AGENTS.md Rule 5, sama seperti kemarin).
4. **TC-INT-LEAD-10** memakai selektor kandidat sorter AntD
   (`.ant-table-column-sorter`) karena struktur tabel belum terkonfirmasi;
   sesuaikan setelah verifikasi DOM.
5. **Jumlah TC Ticket di sheet = 12** (baris 114–125), bukan 11 — total
   TC yang diaudit 23. Perlu Muhammad pastikan apakah memang ada 12 atau
   ada baris yang bukan TC Ticket Aset Baru.
6. Script probe sementara ada di `~/workspace/bsn/probe_*.py` dan
   `probe_out.json` (di luar repo, tidak mengotori git) — boleh dihapus.
7. Push ke GitHub **ditahan** menunggu ACC Muhammad (semua perubahan lokal,
   `git status` hanya menambah folder `customer_management` + 2 file
   `testcase/` di atas baseline kemarin).
