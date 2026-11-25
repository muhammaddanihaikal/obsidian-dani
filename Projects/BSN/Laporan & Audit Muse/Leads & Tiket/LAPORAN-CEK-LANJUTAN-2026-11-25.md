# Laporan Cek Lanjutan — Leads & Tiket Aset Baru (Internal)

Tanggal: Rabu, 25 Nov 2026, 14:41–14:49 WIB (sesi Internal, Superadmin).
Sesuai plan yang di-ACC Muhammad. Yang diubah hanya data tes sendiri: lead/tiket **#ENT-01m8-8153 [AUTO-QA] Test Peminatan**. Data Elina & data lain read-only, tidak berubah.

**Status akhir:** tiket tes = **Booked**, lead tes = **Selesai**. Elina tidak berubah (tiket Proses, lead Terverifikasi).

---

## Bagian B — Penyesuaian Data Leads vs Tiket (kondisi awal)

### Lead tes #ENT-01m8-8153 (JKHS-10007, Rp500.000.000)

| Field | Di Leads (drawer) | Di Tiket (detail) | Sesuai? |
|---|---|---|---|
| Nama peminat | [AUTO-QA] Test Peminatan | [AUTO-QA] Test Peminatan | Ya |
| Kode aset | JKHS-10007 | JKHS-10007 | Ya |
| Harga aset | Rp500.000.000 | Rp500.000.000 | Ya |
| DP / uang muka | Rp85.000.000 (ada label "Data dummy, API belum tersedia") | Rp50.000.000 | **Tidak** |
| Plafon | Tidak tampil | Rp450.000.000 | **Tidak (hilang di Leads)** |
| Tenor | 15 Tahun (180 Bulan) | 1 Thn (15 Bln) | **Tidak** |
| Estimasi angsuran | Rp6.380.000/bln | Rp4.022.500/bln | **Tidak** |
| Combined income | Tidak tampil | Rp10.000.000 | **Tidak (hilang di Leads)** |
| DBR | Tidak tampil | 40,23% | **Tidak (hilang di Leads)** |
| Pola penjualan | "-" | Tidak tampil di detail tiket | **Tidak** |
| Sales / PIC | Terasrumah Admin | Terasrumah Admin | Ya |
| Status | "Processing" | Tahap "New" | **Tidak (istilah beda)** |
| Nomor tiket | #TKT-2024-0891 | ENT-01m8-8153 | **Tidak** |

### Elina #ENT-01m7-2727 (JKHS-10003, Rp300.000.000)

| Field | Di Leads (drawer) | Di Tiket (detail) | Sesuai? |
|---|---|---|---|
| Nama peminat | Elina | Elina | Ya |
| Kode aset | JKHS-10003 | JKHS-10003 | Ya |
| Harga aset | Rp300.000.000 | Rp300.000.000 | Ya |
| DP / uang muka | Rp85.000.000 (sama persis dengan lead tes) | Rp30.000.000 | **Tidak** |
| Plafon | Tidak tampil | Rp270.000.000 | **Tidak (hilang di Leads)** |
| Tenor | 15 Tahun (180 Bulan) | 1 Thn (15 Bln) | **Tidak** |
| Estimasi angsuran | Rp6.380.000/bln (sama persis) | Rp2.413.500/bln | **Tidak** |
| Combined income | Tidak tampil | Rp50.000.000 | **Tidak (hilang di Leads)** |
| DBR | Tidak tampil | 4,83% | **Tidak (hilang di Leads)** |
| Pola penjualan | "-" | Tidak tampil di detail tiket | **Tidak** |
| Sales / PIC | fujianingsih | fujianingsih | Ya |
| Status | "Terverifikasi" | Tahap "Proses" | **Tidak (istilah beda)** |
| Nomor tiket | #TKT-2024-0891 (sama persis) | ENT-01m7-2727 | **Tidak** |

---

## Bagian A + D — Transisi Tahap Tiket Tes & Konsistensi Board vs Tabel

Checklist berkas tetap "0 dari 12 Siap" (semua Pending) di semua tahap — **tidak pernah menghalangi pindah tahap**.

| Langkah | Hasil di detail | Board | Tabel | Board vs Tabel |
|---|---|---|---|---|
| Awal | New | New 1, Proses 1 (Elina) | tes New, Elina Proses | Sama |
| 1. New → Melengkapi Berkas | Pindah OK. Banner: "Nasabah telah mengunggah 12 dari 12 berkas" (padahal checklist 0/12) | Melengkapi Berkas 1 | tes Melengkapi Berkas | Sama |
| 2. → Proses | Pindah OK. Banner: "berkas lengkap 100% / Berkas Syarat Lengkap" | Proses 2 | dua-duanya Proses | Sama |
| 3. → Disetujui | Pindah OK. Banner: SP3K terbit, "syarat pre-akad terpenuhi 100%" | Disetujui 1 | tes Disetujui | Sama |
| 4. → Akad | Pindah OK | Akad 1 | tes Akad | Sama |
| 5. → Booked | Pindah OK. Tombol lanjut & "Tolak Pengajuan" hilang dari header | Booked 1 (label LUNAS) | tes Booked | Sama |

- **VOA tetap Rp.0 di semua tahap**, padahal total dua tiket Rp800.000.000 dan satu sudah Booked/LUNAS.
- **Leads tidak ikut berubah pada langkah 1–3** (tetap Processing). Lead tes baru berubah jadi **Selesai** di akhir rantai (teramati setelah Booked; langkah persisnya Akad/Booked tidak terpisah karena Leads tidak dicek setelah langkah 4): Perlu Tindak Lanjut 4 → 3, Konversi 0% → 25%.
- **Jalur Tolak TIDAK bisa dieksekusi**: di tahap Booked tombol "Tolak Pengajuan" sudah tidak ada, jadi tiket Booked tidak bisa ditolak dari halaman detailnya.
- Catatan log aktivitas tiket tes: sebelum sesi ini sudah ada riwayat pindah tahap 14:32–14:35 (NEW → … → AKAD → NEW) dari aktivitas hari ini juga, dan entri AKAD 14:45 tampil ganda.

## Bagian C — Opsi Status / Tindak Lanjut Lead

- Lead tes **tidak punya pintu tindak lanjut**: barisnya hanya ada "Detail", drawer hanya "Tutup" & "Lihat di Tiket Leads". Jadi form tindak lanjut tidak bisa dibuka untuk lead ini.
- Isi form tindak lanjut (dibuka read-only dari lead lain, tidak disimpan): Klasifikasi Minat = Hot Lead / Warm Lead / Cold Lead / **Batal / Tidak Memenuhi**; Kanal = Telepon / WhatsApp / Email / Kunjungan; Waktu kontak; Durasi; Catatan (maks 500); Checklist Verifikasi Petugas (2 checkbox); Lampiran dokumen pendukung; tombol **Batal Peminatan** & Simpan Tindak Lanjut.
- Jalur negatif ADA di form, tapi **tidak bisa diterapkan ke lead tes** karena pintunya tidak ada (dan lead tes sudah Selesai).

## Temuan Hard Baru (dari cek lanjutan ini)

1. Banner tahap bertentangan dengan checklist: banner mengklaim berkas lengkap 100% / SP3K terbit, checklist tetap 0 dari 12 Siap (semua Pending).
2. Checklist serba Pending (0/12) tidak menghalangi pindah tahap sama sekali — tiket bisa sampai Booked tanpa satu pun berkas siap.
3. "Tolak Pengajuan" hilang di tahap Booked — tiket Booked tidak bisa ditolak dari detailnya.
4. Lead tes tidak punya tombol/form tindak lanjut (hanya Detail) — jalur Batal/Tidak Memenuhi tidak bisa dipakai untuk lead ini.
5. Perpindahan tahap tiket tidak memantul ke Leads sampai akhir rantai (lead tetap Processing di langkah 1–3, baru Selesai di akhir; drawer tidak pernah berubah, riwayat tidak bertambah).
6. Card "Perlu Tindak Lanjut" menghitung beda dengan tab Tindak Lanjut (card 4→3, tab tetap 2).
7. Checklist sempat tampil "0 dari 0 Siap / Belum ada data" sesaat saat halaman dibuka sebelum datanya termuat.
8. Log aktivitas tiket tes: ada entri tahap ganda (AKAD 14:45 muncul dua kali).

Temuan lama yang terkonfirmasi lagi di sesi ini: page size membengkak (URL masih pageSize=2040, Per halaman 16080 di awal sesi), VOA selalu Rp0, nomor tiket drawer Leads #TKT-2024-0891 di kedua lead, simulasi dummy Leads (DP 85jt / tenor 15 thn / angsuran 6,38jt) di kedua lead, plafon/income/DBR tidak tampil di Leads, pola penjualan "-" dan tidak tampil di tiket, istilah status Leads vs Tiket berbeda.

## Revisi SS Desktop (25 Nov 2026, 16:00)
SS diganti screenshot desktop asli 1919x998 (drawer 1919x1080) + kotak merah, di ~/workspace/bsn/ss-desktop-2026-11-25/redbox/:
- Temuan 1 & 2: cl2_01_banner-vs-checklist_redbox.png, cl2_02_checklist-0-dari-12_redbox.png
- Temuan 3: cl2_03_header-booked-tanpa-tombol_redbox.png
- Temuan 4 (flash 0 dari 0): TIDAK berhasil ditangkap ulang (5x percobaan; checklist langsung tampil 0 dari 12) — tanpa SS.
- Temuan 5: cl2_05_log-aktivitas_redbox.png
- Temuan 6: cl2_06_aksi-lead-tes_redbox.png, cl2_06b_drawer-tanpa-tindak-lanjut_redbox.png
- Temuan 7: cl2_07_leads-selesai-di-akhir_redbox.png
