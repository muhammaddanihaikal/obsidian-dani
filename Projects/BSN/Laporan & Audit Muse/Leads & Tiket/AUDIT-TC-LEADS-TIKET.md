# Audit TC — Leads Aset Baru + Ticket Aset Baru (Portal Internal BSN)

> Tanggal: Selasa, 24 Nov 2026 (malam)
> Sumber TC: `tc-sheet.xlsx`, sheet "Script Internal", bagian Customer Management —
> Leads Aset Baru baris 69–79 (11 TC) dan Ticket Aset Baru baris 114–125.
> ⚠️ **Catatan jumlah:** baris Ticket yang ditemukan berisi **12 TC** (114–125),
> bukan 11 seperti perkiraan awal — total yang diaudit **23 TC**, bukan 22.
> Basis bukti: eksplorasi live 24 Nov 2026 sore (17:35–17:51 WIB,
> `LAPORAN-LEADS-TIKET-2026-11-24.md`, 8 issue hard) + screenshot buktinya.
> ⚠️ **Verifikasi live ulang malam ini TIDAK bisa dilakukan**: browser automation
> dari VM Muse gagal menyelesaikan login SSO sandbox (Chromium gagal tunnel
> proxy egress; Firefox berhenti di rantai redirect OAuth) dan percobaan
> lanjutan dihentikan. Poin yang belum terverifikasi ditandai eksplisit di
> bagian E — tidak ada yang dianggap terkonfirmasi tanpa bukti.

## A. Sudah benar (10 TC)

TC sesuai dengan perilaku/struktur aplikasi berdasarkan bukti eksplorasi 24 Nov sore:

- **Leads:** 69 (membuka halaman — summary card + daftar tampil), 70 (memilih tab
  status — tab jalan, hitungan Tindak Lanjut 2 / Terverifikasi 2 benar), 74
  (filter tidak sesuai menampilkan kosong — perilaku kosong memang tampil;
  catatan semantik di bagian B), 75 (mereset filter — Reset jalan dan daftar
  kembali), 79 (melihat detail leads — drawer berisi biodata peminat, rangkuman
  tindak lanjut, aset diminati, simulasi pembiayaan, berkas, dan log aktivitas,
  persis seperti Expected).
- **Ticket:** 114 (membuka halaman Board + summary aktivitas), 115 (mengubah
  tampilan menjadi Tabel), 116 (filter dengan data sesuai — mekanisme
  Filter + kata kunci + Terapkan jalan), 117 (filter tidak sesuai — kondisi
  kosong "Belum ada tiket" tampil, terbukti di screenshot bukti 05), 120
  (melihat detail tiket — stepper tahapan, informasi properti, berkas tampil).

### TC benar — aplikasi yang gagal (bug dari eksplorasi, belum ada issue Huly)

- **77 (Leads)** "Melakukan tindak lanjut dan konfirmasi pembuatan leads" —
  Expected menuntut tiket leads berhasil dibuat setelah tindak lanjut disimpan.
  Aktual: lead tes #ENT-01m8-8153 sudah Terverifikasi, tetapi tiketnya tidak
  terbentuk sama sekali (Board, Tabel, pencarian — semua 0; dicek 3x sampai
  6 menit setelah simpan) → **issue hard #1**. Expected TC sudah benar;
  aplikasinya yang gagal. (Catatan redaksi terpisah di bagian B.)
- **73 (Leads)** "Melakukan filter data leads dengan data yang sesuai" —
  Expected: daftar tampil sesuai filter Pola Penjualan. Aktual: filter hanya
  menjangkau 1 dari 4 lead (Primary Main = 1, Primary Discount = 0); 3 lead
  lain berpola "-" sehingga tidak bisa ditemukan lewat filter pola mana pun →
  **issue hard #5**. Mekanisme filternya jalan, cakupan datanya yang gagal.

## B. Perlu diperbaiki redaksinya (3 TC)

1. **TC 71 (Leads)** — Skenario menulis pencarian "ID pesanan **atau nama
   peminat**", padahal placeholder kolomnya hanya "Cari ID Pesanan..." dan
   eksplorasi hanya membuktikan pencarian by ID. Ubah redaksi menjadi ID
   pesanan saja, atau buktikan dulu pencarian nama memang didukung.
2. **TC 77 (Leads)** — Expected menulis "status berubah menjadi **Selesai**";
   status aktual setelah tindak lanjut adalah **Terverifikasi** (tab Selesai
   tetap 0). Samakan istilah status dengan UI. Nama tombol di skenario
   ("Selesai Konfirmasi & Buat Leads") juga belum pernah dicocokkan persis
   dengan label tombol aktual pada form tindak lanjut.
3. **TC 123 (Ticket)** — Skenario menyebut tombol "Setujui Permohonan
   (Approve SP3K)"; tombol aktual di detail tiket adalah **"Lanjut ke
   Approved"**. Samakan nama tombol dengan UI (eksekusinya sendiri belum
   terverifikasi — lihat bagian E).

## C. Berlebih / outdated

Tidak ada TC yang murni berlebih. Yang berpotensi outdated:

- **TC 121 & 122 (Ticket)** — Memvalidasi / menolak dokumen "pada tahap
  Melengkapi Berkas" dengan tombol Validasi / Tolak pada dokumen. Pada
  satu-satunya tiket yang ada (Elina, tahap Proses), Checklist Berkas Awal
  hanya menampilkan status "Pending" — tidak terlihat tombol Validasi/Tolak
  per dokumen di bukti eksplorasi. TC ini belum bisa dinyatakan salah (tahap
  Melengkapi Berkas-nya tidak teramati karena tiket sudah lewat tahap itu),
  tetapi redaksinya berisiko tidak cocok dengan UI aktual dan wajib
  diverifikasi saat ada tiket yang benar-benar berada di tahap Melengkapi
  Berkas.

## D. Kurang — fitur/perilaku belum ada TC-nya (8 usulan)

Berdasarkan 8 issue hard eksplorasi, cakupan yang belum dimiliki 23 TC di atas:

1. **Keunikan nomor tiket antar-lead** — tidak ada TC yang memeriksa nomor
   tiket; aktualnya lead tes & lead Elina sama-sama #TKT-2024-0891, tahunnya
   pun 2024 (issue hard #2).
2. **Kebenaran hitungan simulasi pembiayaan di drawer Leads** — TC 79 hanya
   memeriksa simulasi *tampil*; tidak ada TC yang memeriksa angkanya. Aktual:
   DP 10% dari Rp500.000.000 tertulis Rp85.000.000 dan angsuran Rp6.380.000 —
   sama persis dengan lead Rp300.000.000 (data dummy) (issue hard #3).
3. **Kartu ringkasan mengikuti data aktual** — tidak ada TC untuk kebenaran
   angka kartu "Perlu Tindak Lanjut" (tetap 4 / "2 SLA Kritis" setelah tindak
   lanjut, dan tidak berubah saat filter menghasilkan 0) (issue hard #4).
4. **Sorting tabel Leads & Ticket** — nol TC sorting di kedua menu. Aktual
   Leads: hanya ID Pesanan & Kode Asset yang punya kontrol sorting; Peminat,
   Waktu Peminatan, Status Lead tidak (issue hard #6). Tabel Ticket punya
   ikon sorting di semua kolom, juga belum tercakup TC.
5. **Konsistensi isi detail tiket** — TC 120 hanya memeriksa detail *tampil*;
   tidak ada TC konsistensi banner "Berkas Syarat Lengkap / telah lengkap
   100%" vs Checklist Berkas Awal "0 dari 4 Siap" semua Pending (issue hard #7).
6. **Kebenaran konversi tenor** — tidak ada TC; aktual "1 Thn (15 Bln)"
   (1 tahun = 12 bulan) (issue hard #7).
7. **Isi kolom Nomor Tiket pada tabel Ticket** — tidak ada TC; aktualnya
   berisi ID lead (ENT-01m7-2727), bukan nomor tiket (issue hard #8).
8. **Kebenaran nilai kartu VOA** — tidak ada TC; aktual Rp.0 padahal ada
   tiket Rp300.000.000 tahap Proses (issue hard #8).

Catatan: pembentukan tiket setelah tindak lanjut (issue hard #1) **sudah**
tercakup TC 77 — bukan usulan baru, melainkan TC benar yang aplikasinya gagal.

## E. Belum terverifikasi (menunggu verifikasi live)

Verifikasi ulang malam ini tidak bisa dijalankan (login SSO sandbox tidak
bisa diselesaikan dari VM — lihat catatan di atas). Poin berikut hanya
berdasar bukti eksplorasi sore atau belum teramati sama sekali:

- **TC 72 (Leads)** — Teks persis keterangan tabel kosong saat keyword tidak
  valid belum tercatat (yang teramati hanya teks "Belum ada leads" saat
  loading dan hasil filter 0 pada issue #4/#5).
- **TC 76 (Leads)** — Mengunduh data leads: tidak dites pada eksplorasi
  (di luar alur yang diminta) — tombol Download Data ada, hasil unduhannya
  belum pernah dibuktikan.
- **TC 78 (Leads)** — Membatalkan peminatan: tidak dites (aksi merusak;
  data existing read-only, dan lead tes pun tidak dibatalkan). Status akhir
  "Batal" belum teramati.
- **TC 116 (Ticket)** — Opsi "unit bisnis" pada panel Filter belum teramati
  rinci; yang terbukti jalan adalah kata kunci + Terapkan.
- **TC 118 (Ticket)** — Reset filter tiket: tombol Reset ada di panel Filter,
  tetapi efeknya belum pernah dibuktikan pada eksplorasi.
- **TC 119 (Ticket)** — Drag & drop tiket di Board: tidak dites — hanya ada
  tiket Elina (data existing, read-only) dan tidak ada tiket tes.
- **TC 121 & 122 (Ticket)** — Validasi/tolak dokumen: tidak dieksekusi
  (tiket Elina read-only) dan tombolnya belum terkonfirmasi ada (lihat C).
- **TC 123 & 124 (Ticket)** — Approve/Reject: tidak dieksekusi — tombol
  "Lanjut ke Approved" dan "Tolak Pengajuan" teramati ada di detail tiket,
  tetapi mengkliknya pada tiket Elina dilarang (mengubah data existing).
- **TC 125 (Ticket)** — Mengunduh dokumen di detail tiket: preview/download
  tidak dites pada eksplorasi.

## F. Keterbatasan

- Data existing read-only total — TC aksi status/dokumen (78, 119, 121–124)
  tidak akan pernah bisa diverifikasi penuh tanpa tiket/lead tes milik
  sendiri yang boleh diproses; saat ini tiket tes tidak ada karena
  pembentukan tiket dari lead tes gagal (issue hard #1).
- Audit ini berbasis bukti eksplorasi 24 Nov sore; tidak ada temuan live
  baru malam ini karena login automation dari VM terblokir (bukan karena
  server down — sandbox-nya sendiri pulih dan bisa dibuka dari browser
  interaktif sore ini).
- Automation pembukti untuk issue hard #1–#8 sudah ditulis malam ini
  (TC-INT-LEAD-06 s.d. 10 dan TC-INT-TIKET-05 s.d. 09 di repo bsn-automation)
  dengan assertion sesuai Expected yang benar — siap dijalankan setelah
  locator terverifikasi live.
