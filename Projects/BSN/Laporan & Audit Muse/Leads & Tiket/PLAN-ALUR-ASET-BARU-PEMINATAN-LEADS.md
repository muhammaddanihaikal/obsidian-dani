# Plan — Cek Aset Baru di External + Alur Peminatan ke Leads

> Status: menunggu ACC Muhammad

## Tujuannya

1. Paham dan cek **semua yang terkait Aset Baru di External**: daftar aset, card, search, filter, halaman detail.
2. Membuktikan: peminatan dari External masuk ke menu Leads Aset Baru di Internal.

## Langkahnya

1. Aku login Internal sekali, sekalian tes TOTP baru. Kalau gagal, berhenti di sini.
2. Aku login External pakai akun customer (OTP diambil dari Mailpit lewat API — caranya di bawah).
3. Aku kelilingi Aset Baru di External, cek satu per satu:
   - Daftar aset & tampilan card (nama, developer, harga, harga coret, stok).
   - Search dan filter — hasilnya cocok atau tidak.
   - Halaman detail aset — isinya lengkap atau tidak (foto, spesifikasi, legalitas, lokasi, fasilitas).
   - Aku bandingkan data 1 aset dengan data yang sama di Internal (harga, stok, developer) — sama atau beda.
4. Aku ajukan **1 peminatan** di aset yang sudah publish, pakai nama dummy `[AUTO-QA]`.
5. Aku balik ke Internal, buka menu **Leads Aset Baru**, cek peminatanku muncul atau tidak.

## Cara aku ambil OTP External (dari belakang)

- Login External ngirim kode OTP ke email. Di sandbox, semua email ditangkap **Mailpit** (kotak email bersama tim).
- Aku tidak buka Mailpit lewat browser. Aku tanya langsung ke API-nya:
  1. Sebelum login, aku catat email terbaru yang sudah ada.
  2. Habis klik login, aku cek API Mailpit berulang-ulang sampai muncul email **baru** buat akun customer.
  3. Dari isi email itu aku ambil angka 6 digit-nya — persis cara `helpers/mailpit.py` di automation-mu.
  4. Kode itu aku ketik ke form login di browser.
- Sifatnya cuma **membaca**. Email tidak ada yang aku hapus/ubah.

## Hasilnya buat kamu

- Laporan (.md): peta fitur Aset Baru di External + hasil cek per fitur + hasil alur peminatan ke Leads.
- Locator yang ketemu di External dan Leads.
- Draf bug report kalau ada yang rusak (tetap tunggu ACC kamu).

## Sisa data

- Cuma 1 lead peminatan — itu memang hasil dari alurnya.

## Aturan mainnya

- Data yang sudah ada tidak aku ubah sama sekali (cuma dilihat/dibaca).
- Mailpit cuma dibaca buat ambil OTP.
- Yang sakral (Superadmin, role Admin, Kantor Pusat) tidak disentuh.
