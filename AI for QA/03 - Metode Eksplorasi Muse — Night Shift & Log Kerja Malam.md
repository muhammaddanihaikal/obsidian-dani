# Metode Eksplorasi Muse — Night Shift & Log Kerja Malam

> Ditulis oleh Muse (agen AI Meta, "Pak Muse") pada 25 Nov 2026 atas perintah Muhammad, supaya Antigravity bisa membaca dokumen ini dan meniru cara Muse mengeksplorasi aplikasi.
> Baca bagian 1–8 sebelum mengeksplorasi. Bagian 9 adalah log kerja nyata Muse (terutama kerja malam) sebagai contoh penerapan metodenya.

## 0. Model kerja

- **Siang:** Muhammad bekerja di laptop memakai Antigravity.
- **Malam:** Muse bekerja dari cloud (laptop Muhammad mati), mulai ±21:00 WIB, **satu menu per malam** sampai tuntas. Muhammad memberi perintah + batasan dan memberi ACC lewat WhatsApp.
- **Pagi:** Muhammad menerima hasil untuk di-review & di-ACC: laporan eksplorasi, draft test case, inventaris locator, draft automation, dan draft bug report. Tidak ada hasil yang dianggap final sebelum ACC Muhammad.
- Repo ini (obsidian-dani) adalah jembatan bersama: dokumen & tracker tinggal di sini; repo automation terpisah di `muhammaddanihaikal/bsn-automation`.
- Patokan aturan: QA_RULES (test case 7 kolom, automation Playwright + Python POM, bug report standar TC Template 05 / template Huly tim), Aturan Eksplorasi Aplikasi, dan mode kerja — semuanya diringkas di dokumen ini supaya dokumen ini bisa berdiri sendiri.

## 1. Prinsip kerja

1. **Plan dulu → ACC → eksekusi.** Untuk tugas baru selalu buat rencana dulu (file .md, chat cukup ringkasannya), tunggu ACC Muhammad, baru kerja sampai selesai.
2. **Bukti di atas klaim.** Setiap temuan dicatat dengan **nilai persis yang teramati + jam pengamatan**. Tidak mengarang angka, status, atau hasil.
3. **Jujur soal kegagalan.** Run yang gagal, terblokir, atau setengah jadi dilaporkan apa adanya beserta penyebab yang terverifikasi — tidak ditutup-tutupi dan tidak diklaim selesai.
4. **Draft dulu, selalu.** Bug report, revisi TC, dan perubahan kode selalu berbentuk draft yang menunggu ACC. Tidak ada folder/file resmi/Huly/push yang dibuat sebelum ACC, kecuali Muhammad memerintahkan sebaliknya.
5. **Laporan rapi dalam file .md**, chat hanya ringkasan pendek. Muhammad tidak suka membaca teks panjang di chat.

## 2. Aturan eksplorasi (WAJIB, tanpa kecuali)

Dari Aturan Eksplorasi Aplikasi (dikonfirmasi Muhammad 2026-11-08):

1. Data yang sudah ada (existing) = **READ-ONLY mutlak**. Boleh dilihat/dicari/difilter; dilarang diedit, dihapus, atau diproses — termasuk untuk test Update/Delete.
2. Data test baru wajib pakai prefix `AUTO-[tanggal]-[menu]` (di repo BSN formatnya `[AUTO-QA] <Nama> <Timestamp>`) dan **setiap data yang dibuat dicatat nama/ID-nya** di log eksplorasi.
3. Test Update/Delete hanya boleh memakai data dari log tersebut, urutannya: **Create → Update data itu → Delete data itu**.
4. Selesai eksplorasi, **semua sisa data buatan wajib dihapus** dan diverifikasi: search prefix AUTO harus menghasilkan **0 hasil**.
5. Kalau ragu apakah suatu data itu existing atau buatan sendiri: **STOP, jangan disentuh, laporkan** ke Muhammad.
6. Laporan akhir wajib berisi daftar data yang dibuat/diubah/dihapus + status cleanup (bersih / ada sisa + alasannya). Contoh nyata: data tes Aset Baru MKSS-10013 tidak bisa dihapus karena menu Aset Baru memang tidak punya fungsi delete — sisa ini dicatat terbuka di laporan, bukan disembunyikan.

Aturan khusus project **BSN** (mengalahkan aturan umum):

- **Tidak ada self-healing** dan tidak ada perubahan assertion tanpa izin Muhammad (anti hijau-palsu). Di luar BSN, model umumnya: agent boleh memperbaiki locator/test dan mengulang sampai hijau atau terbukti bug aplikasi asli — bug asli tidak pernah dipaksa lulus.
- Jangan pernah menyentuh data asli atau entitas sakral: **Superadmin, role Admin, Kantor Pusat**.
- **Mailpit hands-off**: jangan pernah menghapus/mengubah email di dalamnya; OTP diambil dengan polling saja supaya tidak mengambil kode basi.
- Bug report lewat gerbang ACC (draft → ACC → folder/Huly). Di Huly, Muse hanya membuat issue + menempel deskripsi rapi; **screenshot tidak pernah dilampirkan/di-insert oleh Muse** — Muhammad menaruh bukti gambar sendiri secara inline.

## 3. Cara Muse mengeksplorasi satu menu (langkah demi langkah)

1. **Baca konteks dulu.** FSD/PRD, test case existing, tracker bug, dan repo automation dibaca sebelum menyentuh aplikasi. Pahami alur bisnis dan hierarki entitasnya (contoh BSN: Developer → Proyek → Cluster → Tipe → Unit; aset masuk lewat wizard 6 langkah → approval bertingkat → publish).
2. **Login & kelola sesi.** Pakai login tersimpan; untuk BSN Internal kode TOTP dibuat sendiri dari secret di .env repo (jangan pernah menulis nilai secret/kode ke file/memory/chat). Saat sesi habis di tengah eksplorasi, **login ulang langsung sendiri** tanpa menunggu Muhammad, lalu lanjutkan sampai menu tuntas. Pola teknis TOTP: buat kode tepat di **awal jendela 30 detik**; kalau submit pertama kena error CSRF, reload sekali lalu ulangi; batasi jumlah percobaan kode per sesi untuk menghindari lockout akun.
3. **Petakan menunya.** Catat struktur halaman: tab dan jumlah per tab, card ringkasan, kolom tabel, tombol aksi, filter yang tersedia, dan path URL-nya.
4. **Cek read-only pada data existing lebih dulu:** membuka list, search (keyword valid / tidak valid / kosong), **setiap field filter** satu per satu + kombinasi + tombol Reset (pastikan Reset benar-benar membersihkan semua state termasuk tab aktif), **sorting semua kolom satu per satu** (audit penuh, bukan sampling), pagination, pilihan page size, dan halaman detail.
5. **Cross-check angka antar tampilan.** Di sinilah bug paling sering ketemu: bandingkan card ringkasan vs tab vs isi tabel vs halaman detail vs portal lain. Hitung manual nilai yang seharusnya (mis. DP 10% dari harga aset) lalu bandingkan dengan yang tampil di semua tempat. Contoh nyata: DP satu peminatan tampil Rp50jt di checkout, Rp25jt di halaman customer, Rp85jt di detail lead Internal — tiga angka untuk satu transaksi.
6. **Alur tulis hanya pada data sendiri.** Buat data test berprefix, ikuti alur bisnisnya end-to-end **lintas menu dan lintas portal** (contoh: submit peminatan dari External → pastikan lead-nya benar-benar masuk ke Leads Internal → proses tindak lanjut → cek apakah tiket terbentuk di menu Tiket). Selesaikan lifecycle Create → Update → Delete pada data itu, lalu cleanup + verifikasi 0.
7. **Uji batas & konsistensi:** nilai 0 bisa disimpan atau tidak, field kosong tanpa validasi, angka sangat besar, filter yang menghasilkan 0 hasil, hitungan yang tidak berubah mengikuti input (indikasi data dummy), tombol yang tidak merespons, file/bukti yang tidak bisa dibuka, dan konten halaman yang bertentangan dengan dirinya sendiri.
8. **Dokumentasikan saat itu juga.** Setiap temuan: screenshot full + versi kotak merah diambil pada saat pengamatan, nilai persis dan jam dicatat. Bedakan tegas **issue hard** (terbukti, bisa direproduksi) vs **catatan** (observasi sampingan). Temuan yang hanya muncul sekali dan gagal direproduksi ulang pada retest **ditahan (HELD)**, tidak dilaporkan — contoh nyata: issue centang otomatis SHM ditahan setelah 2x retest tidak muncul lagi.
9. **Tulis yang TIDAK dites + alasannya.** Aksi destruktif, data milik orang lain, dan fitur yang belum tersedia dicatat eksplisit di laporan sebagai "belum bisa dites" beserta alasannya — bukan diam-diam dilewati.
10. **Self-review sebelum dilaporkan.** Temuan dicek ulang secara live pada sesi terpisah sebelum Muhammad memilih mana yang dilaporkan. Verdict per issue hanya tiga: **MASIH SAMA / BERUBAH (nilai lama → baru) / TIDAK BISA DICEK (alasan)**. Contoh penerapannya di bagian 9 (cek ulang Leads & Tiket).

## 4. Standar screenshot bukti

- **Full screen ukuran desktop/PC (±1920px, layout PC). Tidak pernah dipotong (crop), tidak pernah ukuran tablet/mobile.** Screenshot hasil print browser tidak diterima karena layout-nya tablet.
- **Kotak merah** digambar tepat pada area masalahnya, supaya jelas konteks kejadiannya dalam satu layar penuh.
- Simpan versi original (tanpa kotak) dan versi redbox. Penamaan: `evidence_[nn]_[deskripsi].png` (retest: `retest_done_[nn]_...` / `retest_reopen_[nn]_...`).
- Format review untuk Muhammad: **daftar bernomor — satu nomor = satu issue dalam satu baris judul, screenshot-nya tepat di bawah nomor itu, tanpa apa pun di antaranya.** Satu screenshot per issue kecuali diminta lebih.

## 5. Deliverable pagi per menu

1. **Laporan eksplorasi (.md):** alur yang dipelajari, daftar yang sudah dicek, issue hard + buktinya, yang belum bisa dites + alasannya, keadaan akhir, dan status cleanup data test.
2. **Draft test case** sesuai template project: kantor = 7 kolom (Module, Sub Menu, Test Case Title, Description Positive/Negative, Priority, Steps, Expected Results; judul berawalan kata kerja "Me-"; urutan business flow); BSN SIT = Excel 9 kolom, 3 sheet portal (judul "Me-", Expected 1 kalimat berawalan "Berhasil..."/"Menampilkan...", kasus negatif hanya untuk Search & Filter, tanpa TC pagination, baris milik rekan tim tidak pernah diedit).
3. **Inventaris locator:** untuk repo BSN prioritasnya **#id / [data-testid] dulu**, fallback semantic role/text. Setiap locator diverifikasi menunjuk **tepat 1 elemen** yang dimaksud. Status verifikasi ditulis jujur per locator: terverifikasi live / belum (dan kenapa).
4. **Draft automation Playwright + Python (POM):** locator statis di `__init__` Page Object, Page Object tanpa assertion, test berpola AAA (`# 1. Arrange / # 2. Act / # 3. Assert`) dengan allure step, ID `TC-[MODUL]-[NN]`, login 1x via storage_state, **waiting selalu dinamis — dilarang keras `wait_for_timeout`/`sleep`**. Urutan aman: tulis dulu → validasi struktur (py_compile + pytest --collect-only) → **full run hanya setelah ACC**.
5. **Audit TC existing (bila diminta):** menu dieksplorasi ulang, tiap TC dibandingkan dengan perilaku aplikasi sebenarnya, dilaporkan dalam ember: (1) sudah benar, (2) perlu diperbaiki + alasannya, (3) belum ada/belum tercakup — plus kategori temuan tersendiri **"TC benar, aplikasi gagal"** (TC-nya sudah tepat, aplikasinya yang tidak sesuai). Muhammad memilih revisinya; Muse membuat draft revisi untuk ACC.

## 6. Alur bug report & Huly

1. **Judul singkat dan netral** gaya Muhammad: pendek, sekali baca paham, tanpa menyalahkan developer. Pola kata yang dipakai: "Tidak Sesuai", "Belum Tampil", "Tidak Berfungsi". Istilah mengikuti tim: card, filter, tab, button, field.
2. **Draft → ACC Muhammad → folder resmi → Huly.** Folder: `Projects/BSN/Bug Report/[Portal]/[Modul]/[Sub Menu]/[NN - Judul Singkat]/` berisi `report.txt` + `komentar_huly.txt` (kosong untuk issue baru) + screenshot evidence (original & redbox).
3. **Template Huly tim diikuti persis** (koreksi Muhammad 25 Nov 2026):
   - Deskripsi ditempel rapi dan **compact** (tanpa baris kosong antar blok; kolom Field pada tabel Technical Context ±1/4 lebar; Checklist for Fix berupa baris bertumpuk "• [ ] ...", tidak pernah dimampatkan jadi satu baris).
   - Bagian "Logs & Media": baris Screenshots tetap persis `Screenshots: (Drag and drop images here)` **tanpa catatan tambahan apa pun**; Console Logs tetap memakai blok kode bash bawaan template, bukan "-" atau teks kosong.
   - **Priority = satu nilai terpilih** yang ditulis di teks report (contoh: issue "Tiket Tidak Terbentuk" = Urgent).
   - **Steps to Reproduce ditulis dalam Bahasa Indonesia**, struktur 4 langkah sesuai template.
   - **Overview faktual dan dipangkas**: tanpa detail proses verifikasi (mis. "dicek 3x sampai 6 menit") dan tanpa spekulasi penyebab (mis. "dugaan static frontend / API belum tersedia"). Isi multi-poin Overview masuk **di dalam blockquote Overview**, bukan sebagai bullet lepas di bawahnya; Impact/Frequency tetap di luar.
   - Linked Issue/PR tetap `# (If applicable)`.
4. Prefix kode Huly: **Internal = BSN_I-**, **External = HULY-**. Pastikan project-nya benar sebelum membuat (pernah kejadian issue External terbuat di project Internal — harus dihapus dan dibuat ulang di project yang benar).
5. Tracker di repo ini (`Projects/BSN/Regression Test - BSN Fase 1.md`) diperbarui setiap ada issue baru/retest.
6. Push ke GitHub lewat konektor Muse hanya bisa **file teks** — PNG evidence tidak bisa ikut ter-push dan tinggal di clone lokal.

## 7. Mode kerja (perintah singkat Muhammad)

- `/plan` — rencana saja (file .md), tanpa kode/file, tunggu ACC.
- `/grill-me` — tanya satu per satu & tantang asumsi sampai spek solid, lalu buat plan.
- `/team-work` — subagent paralel ringan, koordinator memverifikasi terhadap QA_RULES lalu run & lapor.
- `/swarm` — paralel lebar, 1 subagent per menu, hasil digabung koordinator jadi satu laporan.
- `/teamwork` — pekerjaan besar bertahap: wawancara scope + plan milestone → ACC → eksekusi per milestone dengan pemeriksa independen.
- `/boost` — satu masalah bandel: susun hipotesis bersaing + test pembuktian sebelum menyimpulkan.
- `/eksplor` — perintah eksplorasi malam: menu + batasan masuk; pagi keluar laporan + draft TC/locator/automation, menunggu ACC.
- `/audit-tc` — audit TC existing dengan 3 ember di bagian 5.
- `/bug-report` — dari folder tampungan screenshot Muhammad: draft → ACC → simpan per folder menu.
- `/retest` — jalankan ulang skenario repro bug yang sudah diperbaiki, dengan bukti screenshot.
- Mode lain: `/goal`, `/schedule`, `/learn`, `/browser`, `/btw`, `/plugin`, `/generative_ui`, `/review` (review kode Playwright Muhammad terhadap QA_RULES), `/usage` (laporan plan & jatah token Muse).

## 8. Teknik menghadapi halangan (dari kejadian nyata)

- **Server down total (SSO 502 semalaman, 23→24 Nov):** jangan berhenti total — alihkan ke pekerjaan yang tidak butuh server (audit TC dari sheet, inventaris locator dari repo, menulis test dengan validasi struktur saja), dan laporkan blokirnya apa adanya di laporan pagi.
- **Auth rusak berkepanjangan (banner "Unable to locate the column", 24 Nov 23:00 → 25 Nov 11:35):** pakai **cek berkala terjadwal** — interval 15–30 menit, maks 2 percobaan kode per run, **diam total di jam tidur Muhammad** kecuali peringatan lockout, dan ada batas waktu keseluruhan yang disepakati (putaran 1: berhenti 07:00 setelah 16 run gagal; putaran 2: tanpa batas sampai pulih, pulih di run ke-5 setelah 4 run halaman /internal blank total). Begitu login berhasil, verifikasi ulang langsung dikerjakan read-only di run yang sama.
- **Kode TOTP kedaluwarsa di perjalanan:** jangan mencantumkan kode di teks tugas ke browser. Pola yang benar: browser berjalan sampai form kode dan **menunggu**, kode fresh dibuat dan dijawabkan saat itu juga, submit tepat 1x. Kode duplikat/kedaluwarsa menghasilkan penolakan eksplisit "kode tidak valid" — bedakan dari pola rusak server (penolakan diam-diam + banner error).
- **Playwright lokal tidak bisa mencapai situs (proxy tunnel mati) sedangkan situsnya hidup:** verifikasi locator dialihkan ke browser cloud secara read-only. Yang tidak bisa diinspeksi dari browser cloud (atribut #id/data-testid di DOM) dicatat sebagai **belum terkonfirmasi**, tidak diklaim terverifikasi.
- **Screenshot gagal tersimpan (cek ulang 25 Nov):** verdict tetap dicatat live lengkap dengan nilai + jam, dan kegagalan penyimpanannya dilaporkan terbuka ke Muhammad di pesan yang sama — hasil cek tidak ditahan hanya karena buktinya kurang.
- **Temuan bisa berubah belakangan:** tiket lead tes yang disimpulkan "tidak terbentuk" ternyata muncul belakangan (issue-nya dihapus dari Huly, BSN_I-182). Karena itu verdict selalu menyebut **jam pengamatan**, dan kesimpulan "tidak ada X" selalu berarti "tidak ada X sampai jam pengamatan terakhir".

## 9. Log kerja Muse (terutama malam) — contoh nyata penerapan metode

### 23 Nov 2026 (sore–malam) — Internal, Stock Management: Aset Baru & Approval Aset Baru
- Eksplorasi tuntas: list, wizard tambah aset 6 langkah, detail, edit, pengurangan stok, halaman Approval. Data tes dibuat: **MKSS-10013** (Draf; stok diedit 5 → 7; marker [AUTO-QA] di Deskripsi). Aset Baru tidak punya fungsi delete → MKSS-10013 tercatat sebagai sisa Draf yang tidak bisa dibersihkan.
- Audit sorting penuh: **0 dari 12 kolom** di tabel Aset Baru + Approval berfungsi.
- 6 issue hard, semua di-ACC dan dibuat di Huly Internal (BSN_I-169 s.d. 174):
  1. Total pada Card Stok Unit Tersedia Tidak Sesuai
  2. Sorting pada Tabel Aset Baru dan Approval Aset Baru Tidak Berfungsi → pada 25 Nov dipecah jadi 2 issue per menu (draft di-ACC; issue gabungan BSN_I-170 akan dihapus)
  3. Value Kolom Spesifikasi Unit dan Jumlah Unit Approval Belum Tampil
  4. Stok 0 Bisa Disimpan sebagai Draf pada Edit Aset Baru
  5. Filter Approval Menampilkan Hasil Kosong (termasuk Reset tidak membersihkan tab aktif)
  6. File Bukti Approval Pengurangan Unit Tidak Bisa Dibuka
- 1 temuan ditahan (HELD): centang SHM otomatis — muncul 1x, gagal 2x retest.

### Malam 23→24 Nov 2026 — server SSO 502, kerja dialihkan
- Live re-eksplorasi tidak bisa jalan (SSO sandbox 502 terus). Pekerjaan dialihkan ke bahan offline:
  - **Audit TC Aset Baru & Approval:** 42 TC dari sheet tim → 28 benar, 3 "TC benar, aplikasi gagal", 5 perbaikan kata, 8 usulan cakupan tambahan; daftar item yang masih berhutang verifikasi live dicatat eksplisit.
  - **Inventaris locator** Aset Baru/wizard dari Page Object repo yang sudah lulus; locator Approval ditandai belum terverifikasi (menunggu DOM live).
  - **13 test baru** ditulis di clone bsn-automation (TC-INT-STOCK-02..07, TC-INT-APPR-01..07) + Page Object Approval — validasi struktur saja, tidak di-run, tidak di-push, menunggu ACC.

### 24 Nov 2026 (siang–sore) — External: katalog & peminatan Aset Baru
- Perbandingan katalog External vs data Internal: aset yang **belum publish ikut tampil dan bisa diajukan** di External (6 tampil vs 4 Published di Internal).
- Peminatan end-to-end terbukti jalan: pengajuan dari External (lead tes [AUTO-QA] Test Peminatan, aset JKHS-10007) **masuk ke Leads Internal** sebagai lead #ENT-01m8-8153.
- 8 temuan hard tercatat (antara lain: data detail aset belum sesuai — developer tampil "PT Sinar Mas Land Tbk" di semua aset, harga coret selalu harga × 1,25, tombol Google Maps mati; DP tidak konsisten Rp50jt/Rp25jt/Rp85jt untuk satu transaksi; dokumen SP3K tidak bisa dibuka; Data Pemohon di detail lead menampilkan identitas profil akun, bukan data form; NIK "123" diterima tanpa validasi; penghitung kelengkapan dokumen mengklaim 11/11 padahal slot wajib masih kosong).
- Keputusan Muhammad: form pengajuan sedang dirombak total mengikuti Figma, jadi yang dilaporkan hanya issue katalog + 1 issue kesesuaian form dengan Figma → **HULY-109 & HULY-110** (project BSN LELANG EXTERNAL). Issue data detail aset **ditahan** menunggu revisi Figma selesai.

### 24 Nov 2026 (sore) — Internal: Leads & Tiket Aset Baru
- Lead tes #ENT-01m8-8153 diproses lewat Input Hasil Tindak Lanjut sampai status **Terverifikasi** (data existing lain hanya dibaca). Alur Leads → Tiket dipelajari penuh (tiket 6 tahap: New → Melengkapi Berkas → Proses → Disetujui → Akad → Booked, plus Ditolak/Cancel).
- 8 issue hard:
  1. Tindak lanjut tidak membuat tiket (KRITIS — flow utama putus; tiket juga tidak bisa dibuat manual, button Create Leads hanya memunculkan toast "Fitur ini belum tersedia, menunggu API tiket aset baru")
  2. Nomor tiket duplikat #TKT-2024-0891 (lead tes & lead Elina sama; tahun 2024)
  3. Simulasi DP & angsuran di drawer Leads = dummy (DP Rp85.000.000 & angsuran Rp6.380.000/bln identik untuk aset Rp500jt dan Rp300jt; seharusnya DP lead tes Rp50.000.000)
  4. Kartu ringkasan "Perlu Tindak Lanjut" tidak berubah (tetap 4 / "2 SLA Kritis")
  5. Filter Pola Penjualan tidak menemukan lead (3 dari 4 lead datanya "-")
  6. Sorting hanya jalan di 2 kolom (ID Pesanan & Kode Asset)
  7. Detail tiket Elina saling bertentangan (banner "Berkas Syarat Lengkap 100%" vs checklist "0 dari 4 Siap"; tenor "1 Thn (15 Bln)")
  8. Kolom "Nomor Tiket" berisi ID lead (ENT-01m7-2727) dan kartu VOA menampilkan Rp0

### 24 Nov 2026 (malam) — Leads & Tiket: locator, automation, audit TC (tulis saja, run besok setelah ACC)
- **Locator terverifikasi live** via browser cloud (read-only, 19:42–19:44): hampir semua locator terkonfirmasi, path Tiket terkonfirmasi `/internal/manajemen-peminat/tiket/aset-baru`; 5 penyesuaian Page Object diusulkan (kode belum diubah, menunggu review). Atribut #id/data-testid tetap belum terkonfirmasi.
- **19 test baru** ditulis (TC-INT-LEAD-01..10, TC-INT-TIKET-01..09 — termasuk test pembuktian untuk issue hard, assertion tidak dilunakkan) + 2 Page Object; validasi struktur lulus (47 test terkumpul, 0 error); tidak di-run, tidak di-push.
- **Audit TC:** 23 TC (Leads 11 + Tiket 12) → 10 benar, 2 "TC benar, aplikasi gagal" (TC 77 = issue 1, TC 73 = issue 5), 2 perbaikan kata, 9 belum terverifikasi, 8 usulan TC tambahan.

### 24→25 Nov 2026 — saga cek ulang (self-review) Leads & Tiket
- 24 Nov 23:00: cek ulang live pertama gagal di login — auth sandbox rusak (banner "Unable to locate the column", kode TOTP valid ditolak diam-diam). Kedelapan issue berstatus TIDAK BISA DICEK; temuan sore berlaku sebagai status terakhir.
- Cek berkala putaran 1: 16 run sampai 25 Nov 07:08 — semua gagal, pola sama; job dihentikan, status akhir dikirim ke Muhammad.
- Putaran 2 (atas perintah Muhammad 25 Nov 10:25, supaya dia tidak perlu cek sendiri): 4 run halaman /internal blank total, **run ke-5 login pulih 11:35** → verifikasi ulang read-only langsung dikerjakan 11:38–11:42. **Hasil: 8 dari 8 issue MASIH SAMA**, tidak ada perubahan sejak 24 Nov. Catatan jujur di laporan: screenshot cek ulang gagal tersimpan ke disk (verdict tetap tercatat live lengkap dengan nilai + jam).
- 25 Nov lanjutan: draft bug report di-ACC untuk issue **1, 2, 3, 4, 6, 8** (issue 5 & 7 ditahan). Di Huly Internal akhirnya tinggal **BSN_I-185 & BSN_I-186** yang dipertahankan; BSN_I-182 dihapus (tiket lead tes ternyata terbentuk belakangan — pelajaran di bagian 8), BSN_I-183/184/187 dihapus atas instruksi Muhammad. Tracker: 10 Reported / 55 Pending.
- Temuan baru terkonfirmasi Muhammad: **bug page size tabel Tiket** — sorting membuat "Per halaman" membengkak (20 → 40 → 80 → 160 → 520 → 2040, dropdown sampai 16080; opsi resmi hanya 10/20/50/100).
- Cek lanjutan (rencana ter-ACC): tiket tes digerakkan New → Booked; Board vs Tabel cocok di setiap tahap, tapi banner tahap mengklaim berkas lengkap 100% padahal checklist 0/12, dan button "Tolak Pengajuan" hilang di tahap Booked. Temuan checklist Berkas Awal yang lama **digugurkan Muhammad** — tidak dikejar/dilaporkan.

### 25 Nov 2026 — Halaman publik: Simulasi KPR (Simulasi Pembiayaan)
- Eksplorasi penuh halaman publik + verifikasi hitungan manual memakai rumus anuitas. Kesimpulan: **simulator rusak — hasil dummy tetap** (Angsuran Rp1.107.111, Lama 180 Bulan, DP Rp10.000.000, Biaya Bank Rp5.950.000, Biaya Notaris Rp9.425.000) untuk input apa pun, termasuk Harga 0 dan Harga 999.999.999.999.
- **15 issue + 3 catatan minor**, antara lain: klik Hitung kedua tidak menghitung ulang; tenor selalu 180 bulan; DP hasil selalu Rp10.000.000 padahal panel kiri halaman yang sama menghitung dengan benar; plafon maksimal tidak masuk akal (Rp1.500.000); tabel Detail Angsuran berbasis pokok tetap Rp140.000.000; biaya produk MRB berupa angka dummy urut (Rp10, 11, 12, 13...); tanpa validasi harga kosong/0; label akad tertukar (Murabahah ≠ MMQ); nama produk "Produk Sub" tampil ke nasabah.
- Status: laporan selesai, **belum didraf ke Huly** — menunggu review Muhammad.

### Berjalan terus
- Laporan mingguan update Google Antigravity: setiap Senin 10:00 WIB ke WhatsApp Muhammad.
- BSN_I-168 (List Developer): draft komentar retest Huly untuk 2 poin filter (opsi gabungan "Subsidi & Non Subsidi" tidak ada di filter Segmen; filter Kantor Wilayah hanya menampilkan 1 kantor — seharusnya mengikuti kantor yang benar-benar ada di tabel).

## 10. Peta file & repo

- **Repo ini (obsidian-dani):** folder resmi bug report di `Projects/BSN/Bug Report/[Portal]/[Modul]/[Sub Menu]/`; tracker di `Projects/BSN/Regression Test - BSN Fase 1.md`; standar TC BSN di `Projects/BSN/SIT BSN - Format & Standar Penulisan Test Case.md`.
- **Repo automation:** `muhammaddanihaikal/bsn-automation` — Playwright + pytest + uv, pola POM, login 1x via storage_state, data test `[AUTO-QA] <Nama> <Timestamp>`, environment terkunci sandbox/localhost.
- **Laporan lengkap di workspace cloud Muse** (bukan di repo ini): `LAPORAN-LEADS-TIKET-2026-11-24.md`, `RECHECK-2026-11-24.md` (riwayat lengkap 21 run cek berkala + hasil verifikasi), `LAPORAN-SIMULASI-KPR-2026-11-25.md`, `AUDIT-TC-ASET-BARU-APPROVAL.md`, `AUDIT-TC-LEADS-TIKET.md`, `LOCATOR.md`, `LOCATOR-LEADS-TIKET.md`, dan ringkasan issue untuk Muhammad `ringkasan-issue-leads-tiket-2026-11-25.md`.
- **Kredensial tidak pernah ditulis di dokumen mana pun.** Login BSN Internal tersimpan di Secure Vault Muse; secret TOTP hanya ada di .env repo automation lokal (gitignored).

---

*Untuk Antigravity: kalau ada konflik antara dokumen ini dan instruksi terbaru Muhammad, instruksi terbaru Muhammad yang menang. Kalau ragu saat eksplorasi: berhenti, jangan sentuh datanya, laporkan.*
