# Laporan Retest — BSN_I-168 | Data Statistik, Kolom Tabel, dan Filter pada List Developer Belum Sesuai

Retest: Rabu, 25 Nov 2026 sore (Internal, Superadmin, read-only). Status Huly tidak diubah — keputusan status di Muhammad.
Hasil: **1 dari 5 poin FIXED, 4 masih FAILING.**

1. **Card TOTAL ASET PROYEK — FIXED**
   Sekarang tampil "20 Aset Proyek" (dulu "0"), cocok dengan total kolom Unit di tabel (20). Catatan: angka ini menghitung unit; total Properti 11, Klaster 10.
   SS: retest168_01_card-total-aset-proyek_redbox.png

2. **Filter Segmen — MASIH FAILING**
   Opsi tetap cuma "Subsidi" & "Non Subsidi"; opsi gabungan "Subsidi & Non Subsidi" belum ada. Filter "Subsidi" menghasilkan 0 baris (segmen semua baris kosong).
   SS: retest168_02_filter-segmen-dan-kanwil_redbox.png (kontrol filter; isi dropdown terverifikasi live)

3. **Filter Kantor Wilayah — MASIH FAILING**
   Opsi sekarang cuma "Menara BTN" (dulu "KCS Makassar" — berubah, tapi tetap 1 opsi). Data tabel sebenarnya punya 5 kantor: Menara BTN, KCS Makassar, KCS Jakarta Ps. Minggu, KCS Bogor, KCS Jakarta Harmoni.
   SS: retest168_02_filter-segmen-dan-kanwil_redbox.png (kontrol filter; isi dropdown terverifikasi live)

4. **Kolom Segmen — MASIH FAILING**
   Ke-13 baris developer tetap "Segmen belum diisi" semua.
   SS: tidak terlampir — kolom Segmen/Unit kepotong di sisi kanan render print halaman (keterbatasan ekspor SS browser cloud); nilai dikutip dari pengecekan live per baris.

5. **Kolom Unit — MASIH FAILING (membaik sebagian)**
   5 baris sekarang berisi (1, 2, 1, 1, 15 unit; total 20), tapi 8 dari 13 baris masih "0 Unit": PT. Pelangi Abadi, PT. Rex Requm Qeon, PT Cendana Properti Nusantara, Firman, PT. SEJAHTERA, PT. Insan Mandiri, PT PTAN, PT Sinar Matahari Bulan.
   SS: sama seperti poin 4.

## Revisi SS Desktop (25 Nov 2026, 16:00)
SS diganti screenshot desktop asli 1919x998 + kotak merah, di ~/workspace/bsn/ss-desktop-2026-11-25/redbox/:
- Poin 1: rt2_01_card-total-aset_redbox.png
- Poin 2 & 3: rt2_02_filter-segmen-kanwil_redbox.png (kontrol filter; isi dropdown terverifikasi live)
- Poin 4 & 5: rt2_03_kolom-segmen-unit_redbox.png (kolom Segmen & Agunan Listing sekarang terlihat penuh)
Catatan: di SS baru, baris PT Terasrumah Developer terbaca "1 Unit, 2 Properti, 1 Klaster" (saat retest terbaca 1 Properti).
