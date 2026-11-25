# Inventaris Locator — Leads Aset Baru + Tiket Aset Baru (Internal)

> Disusun 24 Nov 2026 malam dari laporan + screenshot eksplorasi.
> **DIVERIFIKASI LIVE 24 Nov 2026, 19:42–19:44 WIB** lewat browser cloud
> (sesi Internal masih login sebagai M dani Haikal / Superadmin — tidak perlu
> login ulang / TOTP), read-only penuh: tanpa submit, tanpa klik Tindak
> Lanjut / Create Leads / Tolak Pengajuan / Lanjut ke Approved / Ubah PIC /
> Segarkan / Download Data.
>
> Arti status:
> - ✅ **Terverifikasi live** — elemen ditemukan di UI persis seperti locator
>   (teks/placeholder/label sama) dan tunggal pada konteksnya.
> - ⚠️ **Terverifikasi tapi perlu penyesuaian** — elemen ada, tetapi tidak
>   unik / teksnya berbeda dari tebakan awal; locator wajib dibatasi atau
>   diganti sebelum run (rinciannya di catatan kolom Status).
> - Verifikasi ini level UI (yang terlihat & bisa diklik). Atribut DOM
>   (#id / data-testid / role persis / struktur tabel) TIDAK bisa
>   dikonfirmasi lewat jalur browser ini — bila nanti ada akses DOM, cek
>   atribut tetap dianjurkan, tetapi locator role/teks di bawah sudah
>   terbukti menunjuk elemen yang benar di UI.
>
> Riwayat: verifikasi via Playwright VM gagal total malam yang sama
> (Chromium `ERR_TUNNEL_CONNECTION_FAILED` lewat proxy egress; Firefox
> nyangkut di rantai redirect OAuth) — blokir jalur VM, bukan aplikasi.

## 1. Leads Aset Baru (`/internal/manajemen-peminat/leads/aset-baru`)

PATH terkonfirmasi. Page Object:
`pages/internal/customer_management/leads_aset_baru/leads_aset_baru_page.py`

| Elemen | Strategi | Locator | Status |
|---|---|---|---|
| Heading halaman | role | `get_by_role("heading", name="Leads Aset Baru")` | ✅ Terverifikasi live — heading tunggal (teks sama juga muncul di breadcrumb & sidebar, jadi pakai role heading) |
| Kartu Total Leads Terdaftar | teks | `get_by_text("TOTAL LEADS TERDAFTAR")` | ✅ Terverifikasi live — nilai saat verifikasi: 4 |
| Kartu Perlu Tindak Lanjut | teks | `get_by_text("PERLU TINDAK LANJUT")` | ✅ Terverifikasi live — nilai 4 + "2 SLA Kritis" (issue hard #4 masih terbukti) |
| Kartu Selesai / Terkonversi | teks | `get_by_text("SELESAI / TERKONVERSI")` | ✅ Terverifikasi live — nilai 0 |
| Kartu Batal / Ditolak | teks | `get_by_text("BATAL / DITOLAK")` | ✅ Terverifikasi live — nilai 0 |
| Tab Semua | role tab + regex | `get_by_role("tab", name=~/^Semua/)` | ✅ Terverifikasi live — label "Semua 4" |
| Tab Tindak Lanjut | role tab + regex | `get_by_role("tab", name=~/^Tindak Lanjut/)` | ⚠️ Tab-nya sendiri tunggal ("Tindak Lanjut 2"), TAPI teks "Tindak Lanjut" muncul 5× di halaman: 1 tab + 2 chip status + 2 tombol per baris. Locator WAJIB dibatasi role tab — jangan `get_by_text` polos |
| Tab Processing | role tab + regex | `get_by_role("tab", name=~/^Processing/)` | ✅ Terverifikasi live — label "Processing 0" |
| Tab Terverifikasi | role tab + regex | `get_by_role("tab", name=~/^Terverifikasi/)` | ✅ Terverifikasi live — label "Terverifikasi 2" |
| Tab Selesai | role tab + regex | `get_by_role("tab", name=~/^Selesai/)` | ✅ Terverifikasi live — label "Selesai 0" |
| Tab Batal | role tab + regex | `get_by_role("tab", name=~/^Batal/)` | ✅ Terverifikasi live — label "Batal 0" |
| Kolom search | placeholder | `get_by_placeholder("Cari ID Pesanan...")` | ✅ Terverifikasi live — placeholder persis |
| Tombol Cari | role | `get_by_role("button", name="Cari")` | ✅ Terverifikasi live |
| Tombol Reset (ikon) | CSS ikon Lucide | `button:has(svg.lucide-refresh-ccw)` | ✅ Terverifikasi live secara UI — tombol ikon panah refresh melingkar di kanan tombol Cari, label "Reset filter" (kandidat locator lebih aman: role button name "Reset filter"; kelas `lucide-refresh-ccw`-nya sendiri belum terkonfirmasi atribut). Fungsi reset terbukti: setelah search, klik ikon ini mengembalikan daftar ke 4 lead |
| Dropdown Pola Penjualan | teks + regex | `get_by_text(/Pola Penjualan:/)` | ✅ Terverifikasi live |
| Opsi pola (Primary Main / Primary Discount) | teks exact | `get_by_text(option, exact=True)` setelah dropdown dibuka | ✅ Terverifikasi live — opsi persis: "Primary Discount", "Primary Main" (default terpilih "Semua") |
| Filter tanggal awal / akhir | placeholder | `get_by_placeholder("Tanggal awal")` / `("Tanggal akhir")` | ✅ Terverifikasi live — dua kotak terpisah, placeholder persis |
| Tombol Segarkan | role | `get_by_role("button", name="Segarkan")` | ✅ Terverifikasi live (locator saja, tidak diklik) |
| Tombol Download Data | role | `get_by_role("button", name="Download Data")` | ✅ Terverifikasi live (locator saja, tidak diklik) |
| Baris tabel | CSS | `tbody tr` | ⚠️ UI terverifikasi (tabel + baris terbaca normal); struktur DOM (native table vs grid) belum terkonfirmasi atribut |
| Info pagination | teks + regex | `get_by_text(/dari \d+ total leads/)` | ✅ Terverifikasi live — teks persis "Menampilkan 10 dari 4 total leads"; setelah search lead tes: "Menampilkan 10 dari 1 total leads" |
| Teks tabel kosong | teks | `get_by_text("Belum ada leads")` | ⚠️ Belum terverifikasi — kondisi hasil 0 tidak direproduksi pada sesi verifikasi ini |
| Tombol Detail per baris | role dalam baris | `row.get_by_role("button", name="Detail")` | ✅ Terverifikasi live — di baris lead tes hanya ada tombol "Detail" |
| Tombol Tindak Lanjut per baris | role dalam baris | `row.get_by_role("button", name="Tindak Lanjut")` | ✅ Terverifikasi live — ada di baris berstatus Tindak Lanjut (2 baris). Locator saja — JANGAN diklik oleh automation (memproses lead) |
| Sorting header ID Pesanan & Kode Asset | — | ikon sort terlihat di screenshot | ✅ Terverifikasi live — ikon ⇅ HANYA di header "ID PESANAN" dan "KODE ASSET" (header lengkap: NO, ID PESANAN, PEMINAT, KODE ASSET, WAKTU PEMINATAN, STATUS LEAD, AKSI). Selektor DOM sorter-nya sendiri belum terkonfirmasi (dipakai TC-INT-LEAD-10) |
| Sorting header Peminat / Waktu Peminatan / Status Lead | — | TIDAK ADA di UI (issue hard #6) | ✅ Terkonfirmasi live lagi — ketiga header tanpa ikon sorting |

### Drawer detail lead (masih di halaman yang sama)

| Elemen | Strategi | Locator | Status |
|---|---|---|---|
| Kontainer drawer | role/ARIA | `[role='dialog']` | ⚠️ Drawer terbukti terbuka dari tombol Detail; atribut `role=dialog`-nya belum terkonfirmasi (UI ✅) |
| Nama peminat (lead tes) | teks | `get_by_text("[AUTO-QA] Test Peminatan")` | ✅ Terverifikasi live |
| Bagian Biodata Peminat | teks | `get_by_text("Biodata Peminat")` | ✅ Terverifikasi live |
| Nomor WhatsApp | teks | `get_by_text("088976972688")` | ✅ Terverifikasi live |
| Email | teks | `get_by_text("customer@terasrumah.dev")` | ✅ Terverifikasi live |
| Alamat domisili | teks | `get_by_text("Jl. AUTO-QA Test No. 1")` | ✅ Terverifikasi live |
| Kode aset diminati | teks | `get_by_text("#JKHS-10007")` | ✅ Terverifikasi live — tampil persis "#JKHS-10007" |
| Chip nomor tiket | teks + regex | `get_by_text(/#TKT-\d+-\d+/)` | ✅ Terverifikasi live — persis "#TKT-2024-0891" (label "Tiket: #TKT-2024-0891") — issue hard #2 |
| Bagian simulasi | teks | `get_by_text("Rencana Skema Pembiayaan & Angsuran")` | ✅ Terverifikasi live |
| Nilai DP simulasi | teks | `get_by_text("Rp85.000.000")` (aktual, dummy — issue #3) | ✅ Terverifikasi live — labelnya "Rencana Uang Muka (DP 10%)", harga aset di drawer Rp500.000.000 |
| Nilai angsuran simulasi | teks | `get_by_text("Rp6.380.000")` (aktual, dummy — issue #3) | ✅ Terverifikasi live — tampil persis "Rp6.380.000/ bulan" |
| Tombol Ubah PIC | role | `get_by_role("button", name="Ubah PIC")` | ✅ Terverifikasi live (locator saja — tidak diklik) |
| Tombol Tutup | role | `get_by_role("button", name="Tutup")` | ⚠️ TIDAK unik — ada 2 kontrol: "Tutup"/X di header drawer + tombol "Tutup" di bagian bawah drawer. Locator wajib dibatasi (mis. tombol bawah / di dalam footer drawer) |
| Tombol Lihat di Tiket Leads | role | `get_by_role("button", name="Lihat di Tiket Leads")` | ✅ Terverifikasi live (locator saja — tidak diklik) |

## 2. Tiket Aset Baru (`/internal/manajemen-peminat/tiket/aset-baru`)

PATH ✅ TERKONFIRMASI live (sebelumnya tebakan pola): view Tabel menambah
`?view=list`; detail tiket di
`/internal/manajemen-peminat/tiket/aset-baru/<ULID>` (contoh tiket Elina:
`01M7SBTCMN892C5Q1THVZC7J1F`). Page Object:
`pages/internal/customer_management/tiket_aset_baru/tiket_aset_baru_page.py`

| Elemen | Strategi | Locator | Status |
|---|---|---|---|
| Heading halaman | role | `get_by_role("heading", name="Daftar Tiket Aset Baru")` | ✅ Terverifikasi live — heading tunggal (breadcrumb: "Ticket Aset Baru") |
| Kartu VOA (label) | teks | `get_by_text("VOA NILAI TIKET ASET BARU")` | ✅ Terverifikasi live |
| Kartu VOA (nilai aktual) | teks exact | `get_by_text("Rp.0", exact=True)` | ✅ Terverifikasi live — "Rp.0", "+0%", "vs Oktober 2026 (Rp.0)" — issue hard #8 |
| Label Aktivitas Tiket Berjalan | teks | `get_by_text("Aktivitas Tiket Berjalan")` | ✅ Terverifikasi live — nilai 1 |
| Tombol Board | role | `get_by_role("button", name="Board")` | ✅ Terverifikasi live (terpilih secara default) |
| Tombol Tabel | role | `get_by_role("button", name="Tabel")` | ✅ Terverifikasi live |
| Tombol Filter | role | `get_by_role("button", name="Filter")` | ✅ Terverifikasi live |
| Tombol Create Leads | role | `get_by_role("button", name="Create Leads")` | ✅ Terverifikasi live (locator saja — TIDAK diklik; toast-nya sudah terbukti di eksplorasi) |
| Input kata kunci di panel Filter | placeholder + regex | `get_by_placeholder(/cari/i)` | ⚠️ Placeholder tebakan LAMA SALAH — placeholder persisnya **"Contoh: Budi Santoso"**; di panel yang sama ada dropdown "Cari Berdasarkan" (default "Nama Pembeli"). Locator wajib diganti |
| Tombol Terapkan (panel Filter) | role | `get_by_role("button", name="Terapkan")` | ✅ Terverifikasi live |
| Tombol Reset (panel Filter) | role | `get_by_role("button", name="Reset")` | ✅ Terverifikasi live |
| Kolom Board: New | teks exact | `get_by_text("New", exact=True)` | ✅ Terverifikasi live |
| Kolom Board: Melengkapi Berkas | teks exact | `get_by_text("Melengkapi Berkas", exact=True)` | ⚠️ TIDAK unik di halaman — teks yang sama muncul sebagai chip ringkasan aktivitas "Melengkapi Berkas (0 · 0%)". Locator wajib dibatasi ke area board |
| Kolom Board: Proses | teks exact | `get_by_text("Proses", exact=True)` | ⚠️ TIDAK unik di halaman — juga muncul sebagai chip ringkasan "Proses (1 · 100%)". Locator wajib dibatasi ke area board |
| Kolom Board: Disetujui | teks exact | `get_by_text("Disetujui", exact=True)` | ✅ Terverifikasi live |
| Kolom Board: Akad | teks exact | `get_by_text("Akad", exact=True)` | ✅ Terverifikasi live |
| Kolom Board: Booked | teks exact | `get_by_text("Booked", exact=True)` | ✅ Terverifikasi live — hanya sebagian terlihat; perlu scroll horizontal |
| Kolom Board: Ditolak & Cancel | teks exact | `get_by_text("Ditolak", exact=True)` / `("Cancel", exact=True)` | ✅ Terverifikasi live — board punya **8 kolom** (6 tahap + Ditolak + Cancel); dua kolom terakhir perlu scroll horizontal. Inventory lama hanya mencatat 6 |
| Kartu tiket Elina (ID) | teks | `get_by_text("ENT-01m7-2727")` | ✅ Terverifikasi live — berada di kolom "Proses" (Elina, JKHS-10003, Rp.300.000.000, PIC fujianingsih) |
| Teks board/tabel kosong | teks | `get_by_text("Belum ada tiket")` | Terbukti dari screenshot eksplorasi (tidak direproduksi pada sesi verifikasi ini — board berisi 1 tiket) |
| Header tabel NOMOR TIKET | teks | `get_by_text("NOMOR TIKET")` | ✅ Terverifikasi live |
| Header tabel lainnya | teks | `get_by_text("PEMBELI")` dst. | ✅ Terverifikasi live dengan KOREKSI: urutan persis NOMOR TIKET, PEMBELI, HARGA ASET, TAHAP, **SALES / PIC** (SATU kolom gabungan, bukan dua kolom), DIBUAT, **AKSI**. Pagination tabel: "Menampilkan 1 - 1 dari 1 tiket" |
| Baris tabel | CSS | `tbody tr` | ⚠️ UI terverifikasi; struktur DOM belum terkonfirmasi atribut |
| Isi kolom Nomor Tiket (aktual) | teks dalam sel | `ENT-01m7-2727` (ID lead — issue #8) | ✅ Terverifikasi live — persis "ENT-01m7-2727" dengan subteks "JKHS-10003" |
| Tombol mata (detail) per baris | ikon dalam baris | belum ada locator pasti | ⚠️ Kolom AKSI terkonfirmasi ada; isi tombolnya belum dicatat persis. Pada verifikasi ini detail dibuka lewat klik teks ID — jalur itu terbukti jalan |

### Detail tiket (halaman terpisah, breadcrumb … / Ticket Aset Baru / ENT-01m7-2727)

| Elemen | Strategi | Locator | Status |
|---|---|---|---|
| Banner Berkas Syarat Lengkap | teks | `get_by_text("Berkas Syarat Lengkap")` | ✅ Terverifikasi live |
| Teks banner lengkap 100% | teks | `get_by_text("telah lengkap 100%")` | ✅ Terverifikasi live — kalimat persis "Seluruh berkas persyaratan telah lengkap 100%." |
| Checklist Berkas Awal | teks | `get_by_text("Checklist Berkas Awal")` | ✅ Terverifikasi live |
| Ringkasan checklist | teks + regex | `get_by_text(/\d+ dari 4 Siap/)` (aktual "0 dari 4 Siap") | ✅ Terverifikasi live — persis "0 dari 4 Siap" (issue hard #7) |
| Status dokumen Pending | teks exact | `get_by_text("Pending", exact=True)` (4 item) | ✅ Terverifikasi live — 4 item: Formulirkpr, Shminduk, Izinpbg, Ktppemohon |
| Keterangan tenor | teks + regex | `get_by_text(/Tenor:/)` (aktual "Tenor: 1 Thn (15 Bln)") | ✅ Terverifikasi live — persis "Tenor: 1 Thn (15 Bln)" (issue hard #7) |
| Tombol Tolak Pengajuan | role | `get_by_role("button", name="Tolak Pengajuan")` | ✅ Terverifikasi live (locator saja — JANGAN diklik) |
| Tombol Lanjut ke Approved | role | `get_by_role("button", name="Lanjut ke Approved")` | ✅ Terverifikasi live (locator saja — JANGAN diklik) |

## 3. Sisa cek & penyesuaian sebelum run pertama

Sudah terjawab oleh verifikasi live 24 Nov malam: PATH Tiket ✅, label tab +
angka ✅, placeholder search Leads ✅, placeholder filter Tiket ✅ (dengan
koreksi), header sorting ✅, isi kolom Nomor Tiket ✅, tenor ✅, header tabel
Tiket ✅ (dengan koreksi SALES / PIC).

Penyesuaian locator yang DISARANKAN di Page Object (menunggu review
Muhammad — kode belum diubah malam ini):
1. Tab "Tindak Lanjut": pertahankan pembatasan role tab (teksnya muncul 5×
   di halaman).
2. Tombol "Tutup" drawer: batasi ke tombol bawah/footer — ada 2 kontrol
   bernama sama.
3. Placeholder input filter Tiket: ganti dari `/cari/i` menjadi
   "Contoh: Budi Santoso".
4. Kolom Board "Proses" & "Melengkapi Berkas": batasi ke kontainer board
   (teks sama muncul di chip ringkasan aktivitas).
5. Header tabel Tiket: sesuaikan ekspektasi "SALES / PIC" (satu kolom) dan
   tambahkan kolom AKSI; board punya 8 kolom (tambah Ditolak & Cancel).

Yang tetap belum bisa dikonfirmasi lewat jalur browser cloud: atribut
#id / data-testid, role persis elemen tab, struktur DOM tabel & drawer,
dan selektor DOM kontrol sorting (untuk TC-INT-LEAD-10). Ini hanya bisa
dicek dengan akses DOM langsung; locator role/teks di atas sudah terbukti
menunjuk elemen yang benar secara UI.
