# Laporan Eksplorasi — Leads & Tiket Aset Baru (Internal)

**Tanggal:** Selasa, 24 Nov 2026, 17:35–17:51 WIB
**Lead tes:** #ENT-01m8-8153 ([AUTO-QA] Test Peminatan, aset JKHS-10007, Rp500.000.000)
**Login:** danihaikal@gmail.com (M dani Haikal, Superadmin). Login sempat gagal 1x (403 CSRF mismatch di callback OAuth), berhasil di percobaan ke-2 dengan kode TOTP baru.

## Cara kerja alur Leads → Tiket (yang dipelajari)

1. Pengajuan dari External masuk sebagai **Lead** di Leads Aset Baru, status awal **Tindak Lanjut**.
2. Staff buka lead, isi **Input Hasil Tindak Lanjut**: Klasifikasi Minat (Hot/Warm/Cold/Batal), Kanal & Waktu Kontak (wajib), Durasi, Catatan (maks 500 karakter), Checklist Verifikasi, dokumen pendukung (opsional).
3. Setelah disimpan (toast "Hasil tindak lanjut tersimpan"), lead jadi **Terverifikasi**. Seharusnya di titik ini terbentuk **Tiket** di Tiket Aset Baru — tapi untuk lead tes ini **tidak terbentuk** (lihat issue 1).
4. Tiket bergerak lewat 6 tahap: New → Melengkapi Berkas → Proses → Disetujui → Akad → Booked. Ada juga tahap terminal Ditolak / Cancel, dan aksi "Tolak Pengajuan" / "Lanjut ke Approved" di detail tiket.
5. Data lead tes cocok dengan yang disubmit dari External: nama, WA 088976972688, email customer@terasrumah.dev, alamat Jl. AUTO-QA Test No. 1, aset JKHS-10007 Harmoni Garden Residence – Maple Garden – Tipe 36/72, 12 dokumen dummy. **NIK tidak tampil di mana pun di halaman Leads**, jadi tidak bisa dicocokkan dari sini.

## Yang sudah dicek

- **Leads:** 4 lead total. Search (ID), tab status, filter Pola Penjualan, filter tanggal, Reset — jalan. Sorting hanya 2 kolom (lihat issue 6). Pagination 1 halaman (4 lead, 10 per halaman).
- **Tindak Lanjut (hanya di lead tes):** Hot Lead, WhatsApp, 24 Nov 2026 17:43, 2 checklist dicentang. Hasil: status jadi Terverifikasi, tab berubah jadi Tindak Lanjut 2 / Terverifikasi 2, log "Tindak Lanjut Peminat Selesai, 24 Nov 2026 17:44 WIB".
- **Tiket:** dicek 3x (17:45, 17:47, dan cek ulang 17:50 — 6 menit setelah tindak lanjut disimpan): tetap hanya 1 tiket (Elina). Cari "Test Peminatan" = 0 hasil. Tombol "Create Leads" di halaman Tiket hanya menampilkan toast "Fitur ini belum tersedia, menunggu API tiket aset baru".
- **Detail tiket Elina (baca saja):** tahap Proses, DP Rp30.000.000, Plafon Rp270.000.000, angsuran Rp2.413.500/bln — angka di sini benar, beda dengan simulasi di drawer Leads (lihat issue 3).

## Issue hard

### 1. Tindak lanjut tidak membuat tiket (KRITIS)
Lead tes sudah Terverifikasi, tapi tidak ada tiketnya di Tiket Aset Baru (Board, Tabel, dan pencarian — semua 0). Tiket juga tidak bisa dibuat manual (tombol Create Leads belum tersedia, menunggu API).

![Tiket tidak terbentuk](evidence/evidence_01_tiket-tidak-terbentuk_redbox.png)

### 2. Nomor tiket duplikat: #TKT-2024-0891
Lead tes dan lead Elina menampilkan nomor tiket yang sama persis, dan tahunnya 2024 padahal sekarang 2026.

![Nomor tiket duplikat](evidence/evidence_02_nomor-tiket-duplikat_redbox.png)

### 3. Simulasi DP dan angsuran di drawer Leads itu data dummy
Harga aset Rp500.000.000 tapi DP (10%) tertulis Rp85.000.000 dan angsuran Rp6.380.000/bulan — angka yang sama persis dengan lead Elina yang harganya Rp300.000.000. Yang benar: 10% dari Rp500jt = Rp50jt. Detail tiket Elina sendiri menampilkan angka yang benar (DP Rp30jt), jadi dua halaman ini tidak cocok.

![Simulasi DP dummy](evidence/evidence_03_simulasi-dp-dummy_redbox.png)

### 4. Kartu ringkasan "Perlu Tindak Lanjut" tidak berubah
Sesudah tindak lanjut disimpan, kartu masih menampilkan 4 (dengan "2 SLA Kritis"), padahal tab sudah benar: Tindak Lanjut 2. Kartu ringkasan juga tidak berubah saat filter dipakai (tetap 4 walau hasil filter 0 lead).

![Kartu tidak update](evidence/evidence_04_kartu-tindak-lanjut-tidak-update_redbox.png)

### 5. Filter Pola Penjualan tidak menemukan lead
Filter "Primary Discount" = 0 lead, "Primary Main" = 1 lead. 3 lead lain (termasuk lead tes) datanya "-" di Pola Penjualan, jadi tidak bisa ditemukan lewat filter ini.

![Filter Pola Penjualan kosong](evidence/evidence_05_filter-pola-penjualan-kosong_redbox.png)

### 6. Sorting hanya jalan di 2 kolom
Hanya ID Pesanan dan Kode Asset yang bisa di-sort. Kolom Peminat, Waktu Peminatan, dan Status Lead tidak ada kontrol sorting-nya.

![Sorting terbatas](evidence/evidence_06_sorting-terbatas_redbox.png)

### 7. Detail tiket isinya saling bertentangan (Elina, dibaca saja)
Banner bilang "Berkas Syarat Lengkap" / "telah lengkap 100%", tapi Checklist Berkas Awal "0 dari 4 Siap" dan keempatnya Pending. Tenor tertulis "1 Thn (15 Bln)" — 1 tahun itu 12 bulan, bukan 15.

![Detail tiket kontradiktif](evidence/evidence_07_detail-tiket-kontradiktif_redbox.png)

### 8. Kolom "Nomor Tiket" isinya ID lead, dan VOA Rp0
Di tabel Tiket, kolom Nomor Tiket menampilkan ENT-01m7-2727 (itu ID lead, bukan nomor tiket). Kartu "VOA Nilai Tiket Aset Baru" menampilkan Rp.0 padahal ada tiket Rp300.000.000 tahap Proses.

![Nomor tiket ID lead, VOA nol](evidence/evidence_08_nomor-tiket-id-lead-voa-nol_redbox.png)

## Yang belum bisa dites + alasannya

- **Aksi di tiket** (ubah status, respon, tutup, "Tolak Pengajuan", "Lanjut ke Approved", drag-and-drop board): tidak ada tiket tes — tiket Elina tidak boleh diubah (data existing, read-only).
- **"Batal Peminatan", "Ubah PIC", preview/download/upload dokumen, "Download Data", "Segarkan", pilih banyak (bulk):** tidak dites — Batal bersifat merusak walau di lead tes; sisanya di luar alur yang diminta.
- **Pagination multi-halaman dan sorting tabel Tiket:** tidak bisa dites, hanya ada 4 lead / 1 tiket dalam 1 halaman.
- **Cocokkan NIK dengan data External:** NIK tidak tampil di halaman Leads (baru muncul di detail tiket, dan tiket tes tidak ada).

## Catatan (bukan issue hard)

- Rangkuman Elina: Waktu Kontak 10:00 WIB, log-nya 14:37 WIB — kemungkinan wajar (jam kontak vs jam simpan), perlu konfirmasi.
- Daftar sempat menampilkan "Belum ada leads" / "Belum ada tiket" sebentar saat data masih loading.
- Foto avatar PIC fujianingsih gagal tampil di halaman Tiket.
- Login sempat gagal 1x (403 CSRF mismatch), berhasil di percobaan ke-2.

## Keadaan akhir

Lead tes #ENT-01m8-8153 sekarang **Terverifikasi** (Hot Lead, WhatsApp, 24 Nov 2026 17:43). Tiket Aset Baru tetap hanya berisi tiket Elina. Tidak ada lead/tiket lain yang diubah. Tidak dibuat draf bug report, folder, atau issue Huly — laporan ini untuk di-review Muhammad dulu.

**Screenshot asli (tanpa kotak merah):** `evidence/01-leads-list.png` s.d. `evidence/09-filter-pola-penjualan.png`.
