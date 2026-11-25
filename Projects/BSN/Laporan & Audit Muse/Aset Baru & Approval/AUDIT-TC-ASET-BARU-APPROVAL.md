# Audit TC — Aset Baru + Approval Aset Baru (Portal Internal BSN)

> Tanggal: Selasa, 24 Nov 2026 (pagi)
> Sumber TC: Google Sheets SIT "Script Internal" — 42 TC (Aset Baru baris 190–209, Approval baris 250–271)
> Basis bukti: eksplorasi live Senin 23 Nov 2026 + analisis desk.
> ⚠️ **Verifikasi live ulang TIDAK bisa dilakukan semalam/pagi ini**: SSO sandbox
> `terasrumah-sandbox.zegen.app` error 502 terus-menerus sejak Senin 21:05 WIB
> (host down, bukan masalah kredensial). Poin yang menunggu verifikasi live
> ditandai eksplisit di bagian E — tidak ada yang dianggap terkonfirmasi tanpa bukti.

## A. Sudah benar (28 TC)

TC sesuai dengan perilaku/struktur aplikasi berdasarkan bukti eksplorasi 23 Nov:

- **Aset Baru:** 190 (membuka halaman), 199 (Step 1), 200 (Step 2 — DP terhitung; promo coret belum diuji, lihat E), 202 (Step 4), 203 (Step 5), 206 (simpan Draft), 207 (edit — stok 5→7 terbukti), 208 (detail, 6 tab jangkar), 209 (pengajuan pengurangan terkirim, stok belum terpotong sebelum approval — sesuai desain).
- **Approval:** 250 (halaman terbuka — istilah tab perlu disesuaikan, lihat B), 259 (detail pengajuan tampil), 263 (tab Pengurangan Unit tampil).

### TC benar — aplikasi yang gagal (bug sudah dilaporkan)

- **251** Tab Disetujui menampilkan 0 baris → bug **BSN_I-173**
- **254** Filter Tipe Aset "Rumah" menghasilkan 0 baris → bug **BSN_I-173**
- **256** Reset tidak membersihkan tab status aktif → bug **BSN_I-173**

Expected pada ketiga TC ini sudah benar; yang menyimpang adalah aplikasinya.

## B. Perlu diperbaiki (5 TC)

1. **TC 191** — Label tab status di TC tidak cocok dengan UI: tab menggabungkan status ("NONAKTIF/DRAF 14" = Draf 3 + Menunggu 11) dan ada tab "Stok". Samakan label + angka acuan dengan UI aktual.
2. **TC 192 & 252** — Skenario menyebut pencarian "nama aset"; UI tidak punya nama properti bebas — yang searchable adalah **kode aset, developer & proyek, lokasi**. Ubah redaksi skenario.
3. **TC 250** — Istilah "Approval Input Aset" outdated; nama tab aktual **"Pengajuan Masuk"**.
4. **TC 198** — Langkah ekspor ("Unduh Rekap → titik tiga → ikon download") belum pernah dicocokkan dengan UI aktual; sesuaikan setelah verifikasi live.
5. **TC 260** — Tombol persis "Detail Lengkap Aset" belum terkonfirmasi ada; bila tidak ada, TC ini perlu ditulis ulang mengikuti alur aktual.

## C. Berlebih / outdated

Tidak ada TC yang murni berlebih. Yang outdated hanya istilah pada TC 250, 192, 252 (masuk bagian B). TC 260 berpotensi outdated (menunggu verifikasi).

## D. Kurang — fitur/perilaku belum ada TC-nya (8 kandidat)

1. **Sorting semua kolom** Aset Baru + Approval — fitur ada, rusak total, nol TC (BSN_I-170).
2. **Nilai kolom Spesifikasi Unit & Jumlah Unit** di daftar Approval (BSN_I-171).
3. **Kebenaran angka summary card** (total aset, total nilai, stok tersedia) — TC 190 hanya cek halaman tampil (BSN_I-169).
4. **File bukti pengurangan bisa dibuka/diunduh** (BSN_I-174).
5. **Validasi negatif wizard**: stok 0 (BSN_I-172), DP di bawah minimum yang di-clamp diam-diam, field wajib kosong — semua TC wizard saat ini positif.
6. **Konsistensi angka antar-tab** saat search/filter (kasus bocor antar-tab, BSN_I-173).
7. **Riwayat pengurangan unit** di Detail Aset setelah pengajuan/approval.
8. **Mengajukan ulang aset Draf tersimpan** (dari Edit/list) — TC 205 hanya mencakup pengajuan dari wizard baru.

## E. Belum terverifikasi live (menunggu server pulih)

Eksplorasi ulang untuk poin berikut **belum bisa dijalankan** karena SSO sandbox 502 sejak 23 Nov 21:05 WIB:

- Aset Baru: 191 (count per tab), 193 (teks tabel kosong), 194–195 (hasil filter per kombinasi), 196 (Reset), 198 (alur ekspor), 201 (upload 4–10 foto + kategori), 204 (tambah destinasi), 205 (alur submit final tanpa eksekusi), promo coret Step 2.
- Approval: 253, 255, 264–269 (tab status/search/filter/reset Pengurangan Unit), 260 (tombol Detail Lengkap Aset).
- Verifikasi sampai modal saja: 257, 258, 261, 262, 270, 271 (approve/tolak data existing dilarang).
- Tidak dapat diverifikasi penuh secara desain: 197 (toggle publish data existing).

## F. Keterbatasan

- Data existing read-only total — TC persetujuan/publish tidak dieksekusi penuh.
- Data uji sendiri hanya MKSS-10013 (Draf, stok 7) + 1 pengajuan pengurangan PENDING miliknya; keputusan submit/approve-nya masih di tangan Muhammad.
- Audit ini menggabungkan bukti eksplorasi 23 Nov + analisis desk; bagian E adalah daftar utang verifikasi yang harus ditutup pada eksplorasi pertama setelah server pulih.
