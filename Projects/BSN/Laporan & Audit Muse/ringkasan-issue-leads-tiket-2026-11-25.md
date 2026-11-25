# Ringkasan Temuan Issue — Leads & Tiket Aset Baru (Internal)

Eksplorasi 24 Nov 2026, 17:35–17:51 WIB. Lead tes: #ENT-01m8-8153 ([AUTO-QA] Test Peminatan, JKHS-10007, Rp500.000.000).
Status: **belum terverifikasi ulang** — login Internal sandbox rusak semalaman (banner "Unable to locate the column"), jadi status di bawah = temuan terakhir 24 Nov sore.

## 8 issue hard

1. **Tindak lanjut tidak membuat tiket (KRITIS)** — Lead tes sudah Terverifikasi, tapi tidak ada tiketnya di Tiket Aset Baru (Board, Tabel, pencarian semua 0). Buat manual juga tidak bisa: tombol Create Leads hanya menampilkan toast "Fitur ini belum tersedia, menunggu API tiket aset baru".
2. **Nomor tiket duplikat #TKT-2024-0891** — Lead tes dan lead Elina menampilkan nomor tiket yang sama persis; tahunnya 2024, padahal sekarang 2026.
3. **Simulasi DP & angsuran di drawer Leads = dummy** — DP (10%) tertulis Rp85.000.000 dan angsuran Rp6.380.000/bln, sama persis untuk aset Rp500jt (lead tes) dan Rp300jt (Elina). Yang benar untuk lead tes: Rp50.000.000. Detail tiket Elina sendiri angkanya benar (DP Rp30.000.000).
4. **Kartu "Perlu Tindak Lanjut" tidak berubah** — Tetap 4 (dengan "2 SLA Kritis") setelah tindak lanjut disimpan, padahal tab sudah benar (Tindak Lanjut 2 / Terverifikasi 2). Juga tidak berubah saat filter menghasilkan 0 lead.
5. **Filter Pola Penjualan tidak menemukan lead** — "Primary Discount" = 0 lead, "Primary Main" = 1 lead. Tiga lead lain (termasuk lead tes) datanya "-" di Pola Penjualan, jadi tidak pernah bisa ditemukan lewat filter ini.
6. **Sorting hanya jalan di 2 kolom** — Hanya ID Pesanan dan Kode Asset yang bisa di-sort. Kolom Peminat, Waktu Peminatan, dan Status Lead tidak ada kontrol sorting-nya.
7. **Detail tiket Elina saling bertentangan** — Banner bilang "Berkas Syarat Lengkap / 100%", tapi Checklist Berkas Awal "0 dari 4 Siap", semuanya Pending. Tenor tertulis "1 Thn (15 Bln)" — 1 tahun = 12 bulan.
8. **Kolom "Nomor Tiket" isinya ID lead + VOA Rp0** — Di tabel Tiket, kolom Nomor Tiket menampilkan ENT-01m7-2727 (ID lead Elina, bukan nomor tiket). Kartu "VOA Nilai Tiket Aset Baru" menampilkan Rp.0 padahal ada tiket Rp300.000.000 di tahap Proses.

## Usulan prioritas lapor

- **Lapor duluan:** 1, 2, 3, 7, 8 — datanya jelas dan bisa dibuktikan angka/contohnya. Catatan untuk no. 1: aplikasi sendiri bilang API tiket belum tersedia, jadi ini fitur belum jadi sekaligus bug.
- **Menyusul:** 4 (angka ringkasan basi, dampak kecil) dan 5 (filternya jalan, masalahnya data lead yang "-").
- **Tahan dulu:** 6 — paling lemah, polanya mirip issue sorting yang sudah dilaporkan (BSN_I-170), bisa jadi memang desain.

Detail lengkap + screenshot bukti: `LAPORAN-LEADS-TIKET-2026-11-24.md` di folder eksplorasi Leads & Tiket.
