# Laporan Singkat — Issue Hard Aset Baru External

> Senin, 24 Nov 2026 · Portal External (customer) vs Internal · Bukti: folder `evidence/` (file `_redbox.png`)
> Struktur sesuai arahan Muhammad: 1 nomor = 1 issue, SS tepat di bawahnya.

## Alur utama: JALAN ✅

Peminatan dari External **masuk ke Leads Aset Baru di Internal**.
Lead tes: **#ENT-01m8-8153** — [AUTO-QA] Test Peminatan, aset JKHS-10007, 24 Nov 14:59 WIB, status "Tindak Lanjut". Total leads naik 3 → 4.

## Issue

1. Aset belum publish tampil di External dan bisa diajukan peminatan (Internal Published 4, External tampil 6 — JKHS-10001 Menunggu Verifikasi & JKHS-10004 Butuh Revisi, dua-duanya "Belum Publish")

   ![SS 1](evidence/evidence_01_total-6-aset_redbox.png)

2. Data pada detail aset belum sesuai — developer tertulis PT Sinar Mas Land Tbk di semua aset (aslinya beda-beda); harga coret selalu harga × 1,25 (Rp 500 Jt → Rp 625 Jt); koordinat lokasi tidak tersedia dan tombol Buka Google Maps tidak berfungsi

   ![SS 2](evidence/evidence_22_detail-desktop-3kotak_redbox.png)

   (1 gambar ukuran desktop, 3 kotak merah: harga coret, koordinat, developer. SS per bagian: evidence_03, evidence_05, evidence_17.)

3. Submit peminatan ditolak karena data bawaan (prefilled) tidak terbaca — toast "Lengkapi data pemohon: status pernikahan" padahal sudah terisi "Menikah"; pola yang sama di form kosong: toast menyuruh melengkapi nama & WhatsApp padahal dua-duanya sudah terisi otomatis. Ter-reproduksi 2× (JKHS-10007 & JKHS-10003). Setelah ditolak, data & berkas tetap utuh (tidak ke-reset)

   ![SS 3](evidence/evidence_08_toast-status-pernikahan_redbox.png)

4. Angka DP tidak konsisten di 3 tempat untuk lead yang sama — form checkout Rp 50.000.000 (10%), card daftar peminatan nasabah "DP Minimal Rp 25.000.000", detail lead Internal "DP 10%" tertulis Rp 85.000.000 (= 17%)

   ![SS 4a](evidence/evidence_09_dp-checkout-50jt_redbox.png)

   ![SS 4b](evidence/evidence_10_dp-nasabah-25jt_redbox.png)

   ![SS 4c](evidence/evidence_16_dp-internal-85jt_redbox.png)

## Temuan baru dari putaran bukti (24 Nov sore) — kandidat, menunggu penilaian Muhammad

5. Dokumen SP3K pada detail peminatan tidak bisa dibuka — tombol "Unduh" SP3K-Garden-8153.pdf dan "Cetak SP3K Resmi" tidak merespons (dicoba 3×), isi dokumen tidak bisa diverifikasi.

   ![SS 5](evidence/evidence_11_sp3k_redbox.png)

6. Data pemohon pada detail peminatan menampilkan data profil akun, bukan data yang diinput di form — nama tampil "Terasrumah Customer" (form: "[AUTO-QA] Test Peminatan") dan NIK ter-masking 3174********0002, sedangkan NIK yang di-submit 3171...0001.

   ![SS 6](evidence/evidence_12_data-pemohon-profil_redbox.png)

7. Validasi NIK tidak ada — NIK diisi "123" tidak memunculkan error apa pun.

   ![SS 7](evidence/evidence_13_validasi-nik_redbox.png)

8. Penghitung berkas peminatan tidak akurat — tetap "11/11 Terunggah / 100%" padahal slot wajib "Rekening Koran 6 Bulan" kosong (ter-reproduksi di 2 aset).

   ![SS 8a](evidence/evidence_14_penghitung-berkas-100persen_redbox.png)

   ![SS 8b](evidence/evidence_15_slot-rekening-koran-kosong_redbox.png)

## Catatan (bukan issue hard)

- Issue simulasi (harga tidak terbawa & salah hitung) DIHAPUS dari daftar atas arahan Muhammad, 24 Nov 16:16.

- Pagination katalog gabungan (/after-search/): saat dites Muse tombol halaman 2 timeout 3×, TAPI Muhammad mencoba sendiri dan BISA (15:57) — tidak ter-reproduksi, kemungkinan efek server lambat saat pengetesan. DICORET dari issue.
- Daftar aset sempat gagal dimuat ±8 menit (14:24–14:32, "Data aset belum dapat dimuat") lalu pulih sendiri — intermiten saat backend gangguan, tidak bisa di-SS ulang setelah pulih. Filter lokasi DKI Jakarta yang saat itu 0 hasil adalah efek yang sama; setelah pulih filter bekerja benar (2 hasil).
- Card pemohon pada detail lead nasabah tampil tidak konsisten antar-load (satu load menampilkan data akun, load lain menampilkan "AB / Akun BSN" + UUID + nomor HP berbeda).
- Badge tipe pada card checkout JKHS-10003 tertulis "Tipe36/72" padahal judul aset "Tipe 50/100".
- Section pembiayaan di detail lead Internal masih berlabel "Data dummy, API belum tersedia"; status pembayaran lead baru tertulis "Non Performing".

## Sisa data

- 1 lead tes **#ENT-01m8-8153** ([AUTO-QA] Test Peminatan) di Leads Aset Baru — tidak bisa dihapus dari sisi Muse, tercatat di sini.
- Favorit sempat diubah lalu dikembalikan seperti semula. Data existing lain tidak disentuh.
