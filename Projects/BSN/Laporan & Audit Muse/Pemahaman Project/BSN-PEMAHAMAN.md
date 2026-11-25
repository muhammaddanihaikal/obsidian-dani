# Pemahaman Proyek BSN

> Ringkasan hasil membaca seluruh dokumen BSN di vault Obsidian Muhammad (`Projects/BSN/` + `skill/qa-bug-reporting/SKILL.md`), disusun 2026-11-23. Isi hanya berdasarkan dokumen; hal yang tidak ada di dokumen ditandai eksplisit.

## 1. BSN itu apa (produk, domain, tujuan, konteks bisnis)

- **BSN** di dokumen ini adalah **BSN Lelang**: aplikasi berbasis web milik **PT Bank Syariah Nasional**, dibangun oleh vendor **PT Zegen Solusi Mandiri**. Divisi owner: **DBG** (Usein Akbar, Abdul Khaloq Al Bari); divisi user: CAM -- DBG; System Analyst: Muhammad Rayhan Subhi. Jenis pengembangan: **Aplikasi Baru**. Platform: Web App, deployment PaaS, lisensi Perpetual, retensi data 5 tahun, source code dimiliki (YES), kepemilikan "Beli Putus".
- **Domain**: pengelolaan dan pemasaran aset properti bank syariah, dengan 2 kategori aset:
  1. **Aset Lelang** — aset agunan pembiayaan bermasalah (NPF/kredit macet) yang dieksekusi/dijual lewat 5 pola penjualan: **Lelang** (resmi via KPKNL), **Jual Bersama**, **Cessie** (pengalihan hak tagih), **SKM** (Surat Kuasa Menjual), dan **Jual Sukarela**.
  2. **Aset Baru** — aset persediaan (indent atau ready stock) milik bank/mitra developer yang dipasarkan di luar mekanisme penyelesaian kredit macet.
- **Tujuan aplikasi** (FSD): mempercepat proses penjualan aset, menjangkau pasar lebih luas, meningkatkan transparansi transaksi, dan mendukung kepatuhan prinsip syariah di setiap mekanisme penjualan.
- Aplikasi punya 3 muka: **Portal Internal** (backoffice bank, disebut juga "Terasrumah Admin"), **Portal Eksternal** (publik/nasabah), dan **Portal Developer** (mitra pengembang).
- Nama lain yang muncul di dokumen: sandbox automation memakai domain `terasrumah-sandbox.zegen.app` dan tabel integrasi FSD menyebut aplikasi sebagai "BSN Properti" (lihat bagian 10).

## 2. Aktor & role (internal, eksternal, developer, dll + hak akses ringkas)

Dokumen FSD 03 mendefinisikan peran: Admin Pusat, Admin Cabang, Verifikator/Approver, Developer, Nasabah/User External. Matriks CRUD-nya sendiri memakai 9 grup role: **Admin Pusat (Aset Lelang)**, **Admin Pusat (Aset Baru)**, **Helpdesk (Aset Lelang)**, **Helpdesk (Aset Baru)**, **FSO (Aset Baru)**, **CWO (Aset Lelang)**, **DBM Supporting (Aset Lelang)**, **Nasabah**, **Developer** — mencakup 56 fitur (dokumen menyebut total 505 pemetaan hak akses).

Pola hak akses yang penting:

- **Admin Pusat** = pengelola penuh domainnya masing-masing: CRUD di Dashboard, Leads, Stock, Media & Management, User Management, Office Management domainnya; Audit Trail/Log hanya **R**; Report **CR**.
- **Ticket**: Admin Pusat hanya **R**; yang bisa mengubah (RUD) adalah **CWO** (Ticket Aset Lelang) dan **FSO** (Ticket Aset Baru).
- **Approval Aset Lelang**: satu-satunya yang CRUD adalah **DBM Supporting (Aset Lelang)**; Admin Pusat tidak punya akses di matriks. **Approval Aset Baru**: **Admin Pusat (Aset Baru)** CRUD. Catatan workshop menegaskan approve & publish Aset Baru dilakukan Admin Pusat.
- **Helpdesk**: umumnya hanya **R** (Dashboard, Leads, Notifikasi).
- **Nasabah**: di sisi eksternal — Beranda/Panduan/Tentang Kami/FAQ/Artikel/Jadwal Lelang **R**; Aset Lelang & Aset Baru **CR**; Simulasi, Bandingkan, Favorit, Profile **CRU**.
- **Developer**: hanya di Portal Developer — Aset Kelolaan, Form Input Aset, Dashboard Developer **CRUD** (terbatas aset miliknya sendiri / row-level access); Akun **CRU**; Keamanan **RU**.
- Role lain yang disebut di dokumen: **Supervisor** (khusus bisa Edit PIC di Leads), **Sales/CS** (penerima distribusi leads otomatis/load balance), **Superadmin** (akun automation; entitas sakral yang tidak boleh disentuh), **PIC Approval**.

Autentikasi internal maupun eksternal: login email + password + **OTP** (resend limit 15 menit), akun terkunci setelah **3x salah kata sandi**.

## 3. Modul & fitur (per kelompok: internal / eksternal & developer / lainnya — sebutkan nama modulnya)

Daftar fungsi FSD berisi 58 entri fitur.

### Internal (backoffice)
- Autentikasi Internal
- Dashboard / Overview — Aset Lelang, Aset Baru
- Customer Management — Leads Aset Lelang, Leads Aset Baru, Ticket Aset Lelang, Ticket Aset Baru
- Stock Management — Aset Lelang, Aset Baru, Katalog Marketing (Aset Lelang & Aset Baru), Sold Out Asset (Aset Terjual), Favorite (Aset Lelang & Aset Baru), Investor (Aset Lelang & Aset Baru), Approval (Aset Lelang & Aset Baru)
- Developer — List Developer, Approval Developer, Dashboard Developer
- Media & Management — FAQ, Article, Banner Setting
- User Management — User, Role, User External, User Block
- Office Management — Tipe Kantor, Data Kantor, KPKNL
- Audit Trail, Audit Log
- Report — Aset Lelang, Aset Baru
- Notifikasi

### Eksternal (nasabah/publik)
- Autentikasi External, Beranda, Aset Lelang, Aset Baru, Jadwal Lelang, Simulasi Pembiayaan, Bandingkan Aset (maks 4 aset), Panduan (Lelang, SKM, Jual Bersama, Jual Sukarela, Cessie, KPR), Tentang Kami, FAQ, Artikel, Favorit, Notifikasi, Daftar Pesanan, Profile User / Akun

### Portal Developer (eksternal)
- Dashboard Developer, Aset Kelolaan, Form Input Aset, List Leads, Form Input Leads, Akun, Keamanan

## 4. Alur bisnis utama (end-to-end, termasuk alur lelang bila ada)

- **Hirarki entitas (wajib berurutan, tidak bisa di-bypass)**: Developer → Proyek → Cluster/Klaster → Tipe Aset → Unit Aset. Developer harus terdaftar dulu (punya NIB, NPWP, CIF Developer, PIC, KC Pengampu, legalitas & PKS) sebelum aset bisa dibuat.
- **Pendaftaran Developer 2 jalur**: via **Internal** langsung aktif **tanpa approval**; via **Portal Developer (External)** **wajib approval** internal dulu sebelum aktif.
- **Input Aset Lelang (wizard)**: No. Rekening Debitur (inquiry ke Core Banking Syariah) → Informasi Aset → Pola Penjualan (Lelang/Jual Bersama/Cessie/SKM) → Dokumen (AJB, SKM/KUM, APHT, PH, IMB/PBG, PBB, PK, SHGB, video 360, foto) → Lokasi → Fasilitas. Ada indikator **Akurasi Aset** (% kelengkapan data) dan status Draft/Verifikasi/Publish.
- **Input Aset Baru (wizard 6 langkah)**: sama seperti Aset Lelang, tetapi field No. Rekening Debitur diganti **Status Aset (Indent/Ready)**. Di Step Informasi Harga ada konfigurasi **Minimal DP** yang menjadi batas minimal uang muka pembeli. Urutan prioritas dropdown Tipe Aset: 1. Rumah, 2. Apartemen, 3. Ruko, lalu tipe lain bebas.
- **Approval & Publish**: alur berjenjang Checker/Reviewer → Approver (bisa *Return to Maker*), disertai notifikasi push & email. Aset hasil submit developer dari portal eksternal **wajib** lewat Approval Aset internal — tidak ada auto-publish. Ada juga flow Publish & Unpublish (unpublish bila aset laku/ada sengketa).
- **Siklus nasabah Leads → Ticket → Investor**:
  - Leads masuk dari web publik; status pipeline: Semua → Tindak Lanjut → **Processing** → Terverifikasi → Selesai / Batal. Distribusi leads ke Sales/CS otomatis (load balance).
  - Saat leads mencapai **Processing** (catatan workshop) / saat tindak lanjut dikonfirmasi (script SIT), sistem **otomatis membuat Ticket** di menu Ticket.
  - Staging Ticket menurut FSD: Belum Ada Sales → Perlu Follow Up → Berjalan → Selesai. Untuk Aset Lelang tahapannya lebih rinci: New/Open → In Progress/Follow Up → Jadwal Ditetapkan (daftar ke portal KPKNL) → Pemenang Lelang → Closed (Won/Lost). Script SIT memakai istilah kanban New → On Going → Deals → Closing (+ Cancel); perpindahan Deals→Closing terjadi otomatis di backend setelah pembayaran. Validasi Closing: nominal wajib diisi dan tidak boleh melebihi total pokok + tunggakan margin + tunggakan denda.
  - Nasabah yang closing/berhasil beli tercatat di menu **Investor** (Stock Management) sebagai database pembeli resmi; asetnya masuk **Sold Out Asset**.
- **Alur lelang (sisi nasabah)**: nasabah melihat katalog/Jadwal Lelang di portal eksternal → menyatakan minat (leads) → ditindaklanjuti internal via ticket → diarahkan mendaftar lelang resmi KPKNL → pemenang melakukan pelunasan → ticket Closed (Won).
- **Portal Developer**: developer mengelola Aset Kelolaan, submit Form Input Aset (masuk antrian approval internal), melihat List Leads untuk asetnya, dan bisa input leads manual (ditandai sumber "Input Developer", terpisah dari leads organik untuk mitigasi leads fiktif).

## 5. Arsitektur & integrasi (sistem, middleware, pihak ketiga)

- **Stack** (FSD 04): Frontend **Next.js v14 + Node.js v20**; Backend **Echo v4** dengan **Golang v1.27** + JavaScript ES6; Web Service **Nginx v1.27**. Arsitektur modular: Frontend (Web Nasabah & Web Backoffice) — API Gateway — Service Layer — host Bank Syariah Nasional.
- **Integrasi**:
  - **LDAP** — login SSO/AD (direct). BSN mengirim Username, Password, Apps; menerima Status, Nama, Divisi, Kantor, NIP, Email, userAD.
  - **Core Banking Syariah** — inquiry data debitur. BSN mengirim Referensi & No. Rekening Pembiayaan; menerima No. Rekening, Nama Debitur, DPD, Kolektibilitas, Outstanding, Jenis Pembiayaan, Kantor Cabang, Status Rekening, Tunggakan Margin, Tunggakan Denda, Total Kewajiban. Sifatnya inquiry saja — dokumen keamanan menegaskan aplikasi **tidak terintegrasi ke core banking untuk mutasi data**.
  - **API Simulasi KPR** — untuk fitur Simulasi Pembiayaan/KPR.
  - **SMTP** — pengiriman Email OTP.
  - **EDW** — tercantum di matriks integrasi tetapi service-nya tertulis "belum diketahui".
- Middleware/interface antar aplikasi sebagian besar ditulis "direct" atau "-" (belum dirinci).

## 6. Keamanan & pelaporan (poin penting saja)

- **Pelaporan**: dokumen FSD 05 menyebut **8 modul laporan**: Overview/Dashboard Laporan, Laporan Peminat/Leads, Laporan Inventory Asset, Laporan Aset Terjual, Laporan Aset Favorit, Laporan Investor, Laporan Audit Trail, Laporan Audit Log (dengan visualisasi dashboard + tabel ekspor). Menu Report internal sendiri berisi Report Aset Lelang & Aset Baru dengan fitur download/export.
- **Profil keamanan**: aplikasi internet-facing (internal & eksternal), mengolah data pribadi pegawai/nasabah (dari LDAP: NIP, email, nama), **bukan** aplikasi settlement (murni pencatatan administrasi), source code on-premise. Konsekuensi skor risiko: Penetration Test menjadi mandatory bila total skor > 4; SAST mandatory bila source code on-premise; DAST mandatory pada skor 0–4.
- **Kontrol utama (STRIDE)**: kebijakan password BSN (min. 10 karakter alfanumerik + simbol, berlaku 90 hari, tidak boleh mengulang 5 password terakhir, dictionary checking); max 3x gagal login; MFA/OTP wajib untuk aplikasi internet-facing (OTP kadaluwarsa & single-use); idle timeout 15 menit (internal & eksternal); reset password via media luar aplikasi dengan token kadaluwarsa & sekali pakai; RBAC least-privilege; session token baru setiap login berhasil & dihancurkan saat logout; audit trail/logging dengan timestamp tersinkron (timestamp, UserID, menu, aktivitas); password disimpan dengan hashing **argon2 dan bcrypt**; enkripsi database untuk data sensitif; TLS 1.2/1.3 dengan sertifikat Public CA; pesan error tidak membocorkan info sensitif.
- **Celah yang diakui dokumen**: fitur disable/deaktivasi otomatis akun dormant **belum didukung**.

## 7. Status pengujian (SIT script internal/eksternal: cakupan; regression tracker Fase 1: jumlah modul, jumlah bug per status — hitung dari tabelnya; modul mana saja yang ada bug Open)

### SIT Script (dokumen hasil konversi .docx, versi 1.0, tanggal 2026-10-27)
- **SIT Script Internal — dinyatakan 181 script, 11 modul**: Login (5 TC), User Authority–Role (7), User Authority–User (18), Dashboard (35), Inventory Aset–Aset (30), Inventory Aset–Approval Aset (43), Inventory Aset–Katalog Marketing (32), Customer Management–Ticket (61), Customer Management–Leads (30), Audit Trail (7), Developer–List Developer (1). Catatan: penjumlahan baris per modul = **269**, tidak sama dengan angka 181 di header dokumen (lihat bagian 10).
  - Status eksekusi di dokumen: baru **Modul Login** yang terisi hasil — 4 Passed, 1 Failed (email tautan reset password tidak pernah masuk ke Mailpit). Modul lain kolom Actual Result/Test Status masih kosong.
- **SIT Script External — 98 script, 12 modul** (angka header cocok dengan penjumlahan baris): Akun–Daftar Akun (9), Akun–Login (8), Akun–Lupa Kata Sandi (8), Beranda–Home Page (9), Beranda–After Search (20), Jenis Agunan (15), Estimasi Lelang (11), Detail Aset–Detail (7), Detail Aset–Favorite (3), Detail Aset–Formulir Pemesanan (3), Detail Aset–Simulasi Pembiayaan (1), Bandingkan (4).
  - Status eksekusi di dokumen: modul Akun sudah dieksekusi — Daftar Akun 7 Passed/2 Failed, Login 7 Passed/1 Failed, Lupa Kata Sandi 6 Passed/2 Failed; ada 3 temuan berstatus "Catatan" (Rekomendasi hunian kosong, dropdown Jenis Agunan blank, Estimasi Lelang langsung empty state). Modul lain belum terisi hasil.
- **Master SIT yang berlaku sekarang** (dokumen standar 2026-11-17): file Excel `Script Test BSN .xlsx` dengan 3 sheet — Script Internal, Script External, **Script Portal Developer** (sheet Portal Developer belum punya dokumen script terpisah di vault).

### Regression Test BSN Fase 1 (PIC QA: Dani, mulai 2026-10-23)
- **Progress Summary**: 20 baris menu/submenu yang sudah dites, semuanya berstatus 🐞 Bug (satu baris, User Management–User, juga 🟢 Done).
- **Total issue: 51 bug** (tabel Status Input Issue ke Huly dan Matriks Status Issue QA konsisten dengan 51 laporan bug detail di file).
- **Jumlah bug per status** (dihitung dari Matriks Status Issue QA dan diverifikasi dari status tiap laporan detail):
  - 🔴 **Open: 46** (29 issue Internal, 17 issue External)
  - 🟢 **Done: 1** — `Internal/User Management/User/01`: Dropdown Kantor pada Form Tambah User Kosong
  - 🟡 **Catatan / Klarifikasi: 2** — Register Nasabah/03 (validasi kata sandi breached/HIBP muncul di akhir) dan Login External/05 (label banner login external tertulis "Sistem Portal Internal")
  - 🔄 **Re-Open: 2** — Aset Baru External: Card Aset/01 dan Filter Pencarian/01
- **Rincian per kelompok modul** (tabel Huly): Authentication 4, User Management 9, Office Management 3, Developer 3, Media & Information 3, Authentication (External) 13, Beranda (External) 2, User Profile (External) 1, Stock Management 8, Aset Baru (External) 3, Simulasi Pembiayaan (External) 1, Daftar Developer (External) 1. **Total 51.**
- **Status input ke Huly: 0 dari 51 sudah dilaporkan — semuanya masih Pending.**
- **Modul/submenu yang memiliki bug Open**: Authentication (Logout 2, Login, Lupa Kata Sandi), User Management (Role 4, User, User Block 2, User External), Office Management (Office Type 3), Developer internal (List Developer), Media & Information (FAQ, Article, Banner Setting), Stock Management (Aset Baru 8), Authentication External (Register Nasabah, Login, Lupa Kata Sandi), Beranda External (Header), User Profile External (Profile Tabs), Aset Baru External (Detail Aset), Simulasi Pembiayaan External (Form Simulasi), Daftar Developer External (Card Developer). Bug Re-Open ada di Aset Baru External (Filter Pencarian, Card Aset).

## 8. Status automation BSN (progress, stack, catatan penting)

- Repo: `github.com/muhammaddanihaikal/bsn-automation`; folder lokal `D:\Project\BSN\Fase 1\Automation Test\`. Environment: sandbox `terasrumah-sandbox.zegen.app`, OTP dari **Mailpit**.
- **Stack & pola**: Playwright + **pytest** + **uv**; Page Object Model dengan `BasePage` tipis; satu `conftest.py` pusat fixture (gaya OrangeHRM); login sekali via `storage_state` (fixture `logged_in_internal`); prioritas locator `get_by_role` → `get_by_label`/`get_by_placeholder` → `get_by_text` → `get_by_test_id` → CSS darurat; navigasi modul via direct URL (`open()`), navigasi sidebar diuji terpisah sebagai smoke test; data uji dari JSON + `data_factory` dengan nama tumbal `[AUTO-QA] <Nama> <Timestamp>`; API helper (`api/internal_user_api.py`) untuk setup/teardown data tumbal; dokumentasi TC dalam Markdown (`testcase/**/*.md`); pola test AAA.
- **Progress fase**:
  - Fase 0a Setup project — ✅ Done
  - Fase 0b Reconnaissance (inspect selector live) — ✅ Done
  - Fase 1 Internal Auth (login, MFA, logout) — 🔄 In Progress; **TC-INT-AUTH-01 PASSED** (Login + MFA OTP via Mailpit)
  - Fase 2 Internal User Management (CRUD) — ⏳ Ready (skeleton 10 TC siap diisi)
  - Fase 3 Stock Management – Aset Baru (Wizard 6 Langkah) — ✅ Done; **TC-INT-STOCK-01 PASSED** full E2E (6 langkah + submit + detail aset 100%), runtime terakhir ±32 detik setelah cleanup static timeout menjadi smart wait
  - Fase 4 External Portal — 🔲 Todo (setelah internal stabil)
  - Fase 5 CI/CD Pipeline (GitHub Actions) — 🔲 Todo
- **Aturan keras automation (AGENTS.md proyek)**: dilarang ubah/delete data real (wajib data tumbal via API); **dilarang self-healing tanpa izin user** dan dilarang mengubah assertion demi lolos (anti fake-green); dilarang blind mass test (run test spesifik); environment lock hanya sandbox/localhost; entitas sakral yang tidak boleh disentuh: **Superadmin user, Admin role, Kantor Pusat**; modul baru wajib model skeleton (locator & fungsi dikosongkan untuk diisi user); komentar kode wajib 1 baris; **dilarang menghapus email di Mailpit** (inbox bersama tim — wajib polling dengan pembanding initial ID agar tidak mengambil OTP basi dari run sebelumnya).

## 9. Format & standar khusus BSN (format TC SIT BSN, standar bug report bila beda dari umum)

### Format TC SIT BSN (dokumen standar 2026-11-17)
- Workbook master `Script Test BSN .xlsx`, 3 sheet mengikuti portal: Script Internal, Script External, Script Portal Developer.
- **9 kolom berurutan**: A `No` (nomor urut modul, merge vertikal per Menu), B `Menu` (merge vertikal), C `Sub Menu` (merge vertikal), D `Test Case`, E `Scenario`, F `Expected Result`, G `Actual Result` (kosong, diisi saat eksekusi), H `Test Status (P = Passed, F = Failed)` (kosong), I `Remark` (kosong).
- **Judul Test Case**: wajib diawali kata kerja aktif **"Me-"** (Membuka, Memilih, Mencari, Memfilter, Menambahkan, Mengubah, Menghapus, Menyetujui, dll.), simple & natural, tanpa kata mubazir.
- **Scenario mengikuti 2 rumus tim**:
  - Aksi langsung → **1 baris horizontal** dipisah ` - ` (mis. `Klik menu <Menu> - Klik sub menu <Sub Menu>` hanya di TC #1; search valid `Input <objek>`; search tidak valid `Input kata kunci tidak ada pada list`; reset `Klik button Reset`).
  - Form panjang/multi-step → **poin vertikal** `- ...`, tiap baris cukup **2–4 kata** sehari-hari (tanpa label UI panjang, tanpa `/`, tanpa "(opsional)").
- **Expected Result**: wajib **tepat 1 kalimat**; diawali `Berhasil ...` untuk sukses atau `Menampilkan ...` untuk empty state.
- **Scope rules khusus BSN**: **Zero Negative Case** kecuali Search & Filter (jangan buat negative case untuk validasi field wajib/format file/password kecuali diminta khusus); **jangan buat TC pagination**; jangan buat TC interaksi mikro (copy-to-clipboard, tooltip, dll.); jangan buat TC klik tab default; hindari TC untuk fitur yang belum ada alur ujinya di UI.
- **Keamanan data & kolaborasi**: dilarang mengubah baris milik tim; sheet/menu dari file teman disalin **100% as-is** (termasuk typo); workflow edit Excel yang aman: backup `.xlsx` dulu, edit via **Excel COM automation**, lalu **verifikasi XML diff** terhadap backup untuk memastikan 0 perubahan tidak disengaja.

### Standar bug report BSN (skill `qa-bug-reporting`)
- **Struktur folder lokal**: `Bug Report/[Portal: Internal/External]/[Nama Modul]/[Nama Sub Menu]/[NN - Judul Singkat Masalah]/` berisi `report.txt`, `komentar_huly.txt`, dan `evidence_[nn]_[desc].png`. Nomor folder **+1 incremental** per sub menu. `komentar_huly.txt` **wajib kosong** untuk issue baru; baru diisi saat retest (Done/Re-Open).
- **Judul (Golden Formula)**: `🐞 [BUG] | [Komponen/Fitur Spesifik] + [Kondisi Cacat]` — **tanpa nama modul**, Title Case dengan kata hubung/preposisi huruf kecil, tanpa kata pengganjal ("Normal", "Data", "Pesan/Respon", dll.).
- **Format lama `report.txt`** (untuk issue yang sudah dibuat): bullet `* ` berisi Menu, Deskripsi, Expected, Actual, Evidence (link Catbox berlabel 1–2 kata). Aturan clean styling Huly: **dilarang blockquote `>`** (memicu garis kuning/oranye), **dilarang backtick** (memicu badge kuning), dilarang baris `Status:` di dalam report.
- **Template tim BARU untuk issue baru**: format Huly dengan `Priority` (Urgent/High/Normal/Low), `Label` (bug, triage-needed, nama modul), Linked Issue/PR, Overview (blockquote diperbolehkan khusus template ini), Impact & Frequency, **Steps to Reproduce** (selalu sertakan), Technical Context (Expected/Actual/Environment/Device-OS/User Role), Logs & Media (**screenshot drag-and-drop langsung di Huly, bukan link Catbox**), dan Checklist for Fix. Issue lama dibiarkan format lama, tidak dikonversi.
- **Approval gate (aturan mutlak)**: AI dilarang membuat folder, memindahkan screenshot dari folder tampungan, meng-update tracker Obsidian, atau upload Catbox **sebelum draft disetujui user**. Urutan: draft cepat dari screenshot lokal → tunggu ACC user → baru eksekusi (upload Catbox, buat folder, simpan report.txt + komentar_huly.txt kosong, bersihkan tampungan, update tracker Regression Test BSN Fase 1 di Obsidian).

## 10. Hal yang belum jelas / risiko / pertanyaan terbuka dari dokumen

- **Inkonsistensi nama aplikasi**: dokumen memakai tiga nama — "BSN Lelang" (FSD), "BSN Properti" (tabel integrasi FSD), dan "Terasrumah" (nama admin & domain sandbox). Nama resmi final tidak ditegaskan di dokumen.
- **Field FSD yang masih kosong/template**: Kode Nama Aplikasi, Application URL, Implemented Year, dan tanggal dokumen belum diisi; histori perubahan FSD hanya mencatat versi 1.0 (24 September) dengan kolom alasan perubahan kosong.
- **Angka script Internal tidak konsisten**: header SIT Script Internal menyatakan 181 script, tetapi penjumlahan baris TC per modul di dokumen yang sama = 269. Belum jelas angka mana yang benar / apakah header belum diperbarui.
- **Dua sumber kebenaran SIT**: script lama berbentuk dokumen (.docx terkonversi, 181/98 script) vs master Excel baru `Script Test BSN .xlsx` (3 sheet termasuk Portal Developer). Dokumen tidak menyatakan eksplisit kapan script dokumen berhenti berlaku; script Portal Developer hanya ada di Excel, tidak ada dokumen rinciannya di vault.
- **Perbedaan istilah staging Ticket**: FSD memakai Belum Ada Sales → Perlu Follow Up → Berjalan → Selesai (dan varian lelang New/Open → … → Closed Won/Lost), sedangkan script SIT memakai New → On Going → Deals → Closing → Cancel. Pemetaan resminya tidak disebutkan di dokumen.
- **Jumlah langkah wizard tidak seragam**: FSD 01 menyebut "Wizard 4 Tahap" untuk input Aset Lelang, sedangkan kebutuhan fungsional FSD dan automation memakai 6 langkah/tahap (termasuk Pola Penjualan, Lokasi, Fasilitas). 
- **Leads Aset Baru belum terintegrasi penuh**: catatan workshop (2026-11-02) menyebut halaman Leads Aset Baru masih menampilkan data fallback dari Leads Aset Lelang karena endpoint API aset baru masih dalam integrasi backend — risiko regression yang harus dimonitor.
- **Anomali matriks Approval Aset Lelang**: Admin Pusat tidak punya akses sama sekali dan hanya DBM Supporting yang CRUD — perlu konfirmasi apakah ini memang desain atau kesalahan matriks. Baris No. 8 UAM juga berjudul "Stock Management – Aset Lelang" tetapi pola aksesnya (Admin Pusat Aset Baru & FSO) mengindikasikan Aset Baru.
- **Integrasi EDW belum jelas**: service-nya tertulis "belum diketahui" di FSD 04; rincian middleware sebagian besar masih "direct"/"-".
- **Tabel STRIDE terpotong**: dokumen hasil konversi menampilkan 35 baris kontrol lalu diakhiri "…" — daftar kontrol lengkapnya tidak ada di vault. Total skor kuesioner keamanan juga tidak terisi angkanya di dokumen.
- **Backlog Huly**: seluruh 51 issue regression Fase 1 masih Pending untuk diinput ke Huly (0 reported) — risiko temuan tidak tertangani formal bila tracker Obsidian tidak segera disinkronkan.
- **Konflik aturan sinkronisasi Git**: skill `qa-bug-reporting` memerintahkan commit & push vault Obsidian ke `origin/main` setiap update tracker, sedangkan persetujuan akses GitHub untuk repo obsidian-dani yang tercatat adalah **read-only** — push memerlukan persetujuan terpisah.
- **Kredensial di catatan**: file Automation BSN memuat contoh isi `.env` termasuk kredensial Mailpit dalam teks biasa di vault — risiko kebocoran bila vault dibagikan; nilai kredensialnya sengaja tidak disalin ke dokumen ini.
