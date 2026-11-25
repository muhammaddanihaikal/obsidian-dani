# Plan Eksplorasi Malam Ini — Leads & Tiket Aset Baru (Internal)

**Mulai:** hari ini 18:00 WIB
**Target:** 2 menu Internal — Leads Aset Baru + Tiket Aset Baru
**Hasil akhir:** laporan singkat + list issue hard + screenshot kotak merah (ukuran desktop/PC)

## Modal yang sudah ada

- Lead tes kita sendiri dari External: **#ENT-01m8-8153** ([AUTO-QA] Test Peminatan, aset JKHS-10007, status Tindak Lanjut) — ini bahan utama buat ngetes alur Leads → Tiket tanpa nyentuh data asli.
- Login Internal udah aman (TOTP baru jalan), aku login sendiri kayak biasa.

## Langkah — Leads Aset Baru

1. Buka menu Leads, cek tampilan awal: total leads, kolom tabel, status-status yang ada.
2. Cek Search, Filter, Reset, sorting, pagination — jalan semua atau nggak.
3. Buka detail lead tes kita (#ENT-01m8-8153), cocokin datanya sama yang disubmit dari External (nama, NIK, aset, DP, dokumen).
4. Bandingin sekilas sama lead lain yang tampil (cuma baca, nggak diubah) — datanya masuk akal atau ada yang aneh.
5. Coba tombol/aksi yang ada di Leads (misal Tindak Lanjut) **khusus di lead tes kita** — lihat hasil aksinya apa.

## Langkah — Tiket Aset Baru

1. Buka menu Tiket, cek apakah udah ada tiket yang kebentuk dari lead tes kita habis di-Tindak Lanjut.
2. Kalau belum ada: cari cara tiket terbentuk (dari aksi di Leads), bikin **hanya dari lead tes kita**.
3. Cek tampilan Tiket: kolom, status, Search, Filter, Reset, sorting, pagination.
4. Buka detail tiket: isinya nyambung nggak sama data lead-nya (nama, aset, riwayat).
5. Coba aksi yang ada di tiket (ubah status / respon / tutup) khusus tiket tes kita, catat alurnya.

## Aturan main (standar BSN)

- Data existing = **read-only**, nggak diubah/di-proses sama sekali.
- Proses (Tindak Lanjut, bikin tiket, ubah status) **hanya di data tes kita sendiri**.
- Nggak ada self-healing, nggak ngarang hasil — yang nggak bisa dites aku tulis apa adanya.
- Screenshot bukti ukuran desktop, issue dikasih kotak merah.

## Hasil yang kamu terima

1. Laporan singkat: alur Leads → Tiket jalan atau nggak, ketemu apa aja.
2. List issue hard (kalau ada), satu per satu + screenshot kotak merah-nya.
3. Draf bug report **nggak** aku buat dulu — nunggu kamu review list-nya.
