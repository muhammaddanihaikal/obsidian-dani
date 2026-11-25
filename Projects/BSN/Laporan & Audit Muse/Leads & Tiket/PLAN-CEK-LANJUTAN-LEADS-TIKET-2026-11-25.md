# Rencana Cek Lanjutan — Leads & Tiket Aset Baru (Internal)

Status: **PLAN — menunggu ACC Muhammad, belum dijalankan.**
Tanggal: 25 Nov 2026.

## Jawaban singkat: belum semua dicek

Yang SUDAH dicek (eksplorasi 24 Nov + recheck 25 Nov):
- Leads: tabel, filter, search, sorting (terbatas 2 kolom), drawer + simulasi DP, tindak lanjut sampai Terverifikasi, card statistik.
- Tiket: Board & Tabel, search, detail tiket (checklist, simulasi), pembentukan tiket dari lead (terlambat ±11:53), sorting tabel Tiket berfungsi, bug page size saat sorting.

Yang BELUM dicek (bolongnya di sini):
1. **Pindah-pindah tahap (staging) di Tiket** — tombol tahap belum pernah diklik sama sekali.
2. **Penyesuaian data Leads ↔ Tiket secara sistematis** — baru ketemu insidental (DP di drawer Leads salah, di detail Tiket benar). Belum dibandingkan field per field.
3. **Transisi status Leads selain Tindak Lanjut → Terverifikasi** (mis. jalur ditolak / tidak berminat).
4. **Konsistensi Board vs Tabel Tiket** setelah ada perubahan tahap.

## Ruang lingkup rencana

Data uji: lead/tiket tes kita sendiri **[AUTO-QA] Test Peminatan (#ENT-01m8-8153 / tiketnya)** — semua aksi ubah tahap hanya di data ini.
Data existing (termasuk tiket Elina): **read-only**, hanya dibuka untuk perbandingan tampilan.

### A. Transisi tahap Tiket (di tiket tes saja)
- Klik perpindahan tahap satu per satu sesuai urutan Board: New → Melengkapi Berkas → Proses → Disetujui → Akad → Booked.
- Di tiap tahap catat: apakah tiket benar-benar pindah kolom di Board, berubah di Tabel, dan persen tahapnya berubah.
- Cek tombol "Lanjut ke Approved" dan "Tolak Pengajuan": tiket tes dicoba jalur Tolak di akhir (setelah semua tahap positif tercatat), catat status akhirnya (Ditolak / Cancel).
- Cek apakah checklist berkas memengaruhi bisa/tidaknya pindah tahap (semua berkas masih Pending — apakah tahap tetap bisa maju?).

### B. Penyesuaian data Leads ↔ Tiket (field per field)
Bandingkan drawer Leads vs detail Tiket untuk lead tes (dan Elina sebagai pembanding read-only):
- Nama peminat, kode aset, harga aset
- DP / uang muka, plafon, tenor, estimasi angsuran, combined income, DBR
- Pola penjualan, sales/PIC, status & tahap
- Nomor tiket yang tampil di drawer Leads vs di Tiket
Hasilnya dibuat tabel: field | nilai di Leads | nilai di Tiket | sesuai / tidak.

### C. Transisi status Leads
- Cek status-status yang tersedia di tindak lanjut selain Hot Lead → Terverifikasi (mis. tidak berminat / ditolak, bila ada) pada lead tes — catat perubahan tab & card-nya.
- Cek apakah perubahan tahap di Tiket (bagian A) ikut mengubah status/tampilan lead di Leads.

### D. Konsistensi Board vs Tabel
- Setelah tiap perpindahan tahap di bagian A: samakan jumlah tiket per tahap di Board dengan isi Tabel (termasuk card VOA & Aktivitas Tiket Berjalan).

## Aturan main
- Existing data read-only; tidak klik simpan/pindah tahap di data selain tiket tes.
- Semua aksi di tiket tes dicatat (tahap sebelum → sesudah) di laporan.
- Tidak ada pembuatan data baru; lead/tiket tes yang sudah ada saja yang dipakai.
- Bug report: temuan hard dibuatkan draf dulu, menunggu ACC Muhammad (tidak langsung folder/Huly).

## Hasil akhir yang dikirim
- Laporan .md: hasil A–D + tabel penyesuaian data (bagian B).
- Daftar temuan hard baru (format favorit: nomor, judul, penjelasan singkat).
- Bukti SS mengikuti standar (full desktop + kotak merah) sebisa alat yang ada; keterbatasan ekspor SS dari browser cloud disampaikan apa adanya bila masih terjadi.
