# Hasil Eksplorasi Ulang — Aset Baru + Approval Aset Baru

> Status: **BLOKIR SERVER** — eksplorasi ulang TIDAK dapat dijalankan.
> SSO `https://terasrumah-sandbox.zegen.app/sso/oauth2/auth` mengembalikan
> **502 Bad Gateway (host down)** pada setiap percobaan sejak Senin 23 Nov 2026
> 21:05 WIB sampai pengecekan terakhir Selasa 24 Nov 2026 pagi (~04:37 WIB).
> Halaman `/internal` sendiri merespons 200, tetapi login mustahil tanpa SSO.
> Tidak ada kredensial yang dimasukkan, tidak ada TOTP yang dipakai,
> tidak ada data yang disentuh, Mailpit tidak disentuh.

## Konsekuensi

- Semua titik verifikasi di `AUDIT-DESK-PENDAHULUAN.md` berstatus
  **BELUM TERVERIFIKASI ULANG** — daftarnya ada di
  `~/workspace/bsn/AUDIT-TC-ASET-BARU-APPROVAL.md` bagian E.
- Audit final pagi ini didasarkan pada bukti eksplorasi live 23 Nov 2026
  (yang memang ekstensif: CRUD MKSS-10013, audit sorting 12 kolom,
  filter/search Approval) + analisis desk 42 TC.
- Locator Aset Baru diambil dari Page Object repo yang sudah terverifikasi
  (test PASSED); locator Approval ditandai belum terverifikasi di `LOCATOR.md`.
- Cron retry `bsn-eksplorasi-malam` dinonaktifkan 24 Nov pagi atas arahan
  Muhammad (pekerjaan diambil alih langsung). Bila server pulih, eksplorasi
  penutup bagian E bisa dijalankan ulang kapan saja.
