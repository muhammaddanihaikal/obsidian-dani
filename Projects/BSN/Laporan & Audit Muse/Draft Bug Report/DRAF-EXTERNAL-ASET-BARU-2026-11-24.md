# Draf Bug Report — External Aset Baru (24 Nov 2026)

> Scope sesuai arahan Muhammad: hanya sampai detail aset. Issue form pengajuan per-temuan TIDAK dibuatkan bug report (form sedang dirombak total dari 1 page jadi 4 page) — sebagai gantinya ada 1 issue penyesuaian form ke desain Figma (nomor 3 di bawah).
> Status: DRAF — menunggu ACC sebelum dibuat folder resmi + issue Huly.

---

## 1. Aset Belum Publish Tampil di Katalog External

**Overview**

> Aset yang statusnya belum publish di Internal (Menunggu Verifikasi dan Butuh Revisi) tetap tampil di katalog Aset Baru portal External, halaman detailnya bisa dibuka, dan tombol ajukan peminatan aktif.

**Steps to Reproduce**

1. Login Internal, buka Stock Management → Aset Baru → tab Published (total 4 aset)
2. Login portal External sebagai nasabah, buka menu Aset Baru
3. Katalog menampilkan 6 aset
4. Buka detail JKHS-10001 (status Menunggu Verifikasi) dan JKHS-10004 (status Butuh Revisi)

**Actual Result**

- Katalog External menampilkan 6 aset, termasuk JKHS-10001 dan JKHS-10004 yang di Internal berstatus "Belum Publish"
- Halaman detail kedua aset bisa dibuka dan pengajuan peminatan bisa dimulai

**Expected Result**

- Katalog External hanya menampilkan aset yang sudah Published di Internal (4 aset)

**Technical Context**

| Item | Value |
|---|---|
| Portal | External (nasabah) |
| Modul | Aset Baru — Katalog & Detail |
| Aset terkait | JKHS-10001 (Menunggu Verifikasi), JKHS-10004 (Butuh Revisi) |
| Environment | Sandbox (terasrumah-sandbox.zegen.app) |
| Tanggal temuan | 24 Nov 2026 |

**Logs & Media**

- evidence_01_total-6-aset_redbox.png (katalog External: "Menampilkan 1–6 dari total 6")

**Checklist for Fix**

- [ ] Katalog External hanya mengambil aset berstatus Published
- [ ] Detail aset belum publish tidak bisa diakses dari External
- [ ] Retest oleh QA

---

## 2. Data pada Detail Aset Belum Sesuai

**Overview**

> Tiga data pada halaman detail aset External belum sesuai: nama developer selalu tertulis PT Sinar Mas Land Tbk, harga coret selalu dihitung harga × 1,25, dan koordinat lokasi tidak tersedia sehingga tombol Buka Google Maps tidak berfungsi.

**Steps to Reproduce**

1. Login portal External sebagai nasabah, buka menu Aset Baru
2. Buka detail aset mana pun (contoh: JKHS-10007)
3. Lihat card Informasi Developer Rekanan, card Harga Developer Rekanan, dan bagian Aksesibilitas & Peta

**Actual Result**

- Card developer tertulis "PT Sinar Mas Land Tbk" di semua aset, padahal developer aslinya berbeda-beda (di card katalog namanya benar)
- Harga coret selalu harga × 1,25 (contoh: Rp 500 Jt → coret Rp 625 Jt, "Hemat Rp 125 Juta")
- Bagian peta menampilkan "Koordinat lokasi tidak tersedia" dan tombol "Buka Google Maps" tidak berfungsi

**Expected Result**

- Nama developer pada detail sama dengan developer asli aset (sama seperti di card katalog)
- Harga coret sesuai harga normal asli aset, bukan hasil perhitungan tetap
- Koordinat lokasi tampil dan tombol Buka Google Maps membuka lokasi aset

**Technical Context**

| Item | Value |
|---|---|
| Portal | External (nasabah) |
| Modul | Aset Baru — Detail Aset |
| Aset terkait | Semua aset (terverifikasi di JKHS-10007, JKHS-10001, MKSS-10010) |
| Environment | Sandbox (terasrumah-sandbox.zegen.app) |
| Tanggal temuan | 24 Nov 2026 |

**Logs & Media**

- evidence_22_detail-desktop-3kotak_redbox.png (detail aset ukuran desktop, 3 kotak merah: harga coret, koordinat, developer)

**Checklist for Fix**

- [ ] Nama developer pada detail mengikuti data aset
- [ ] Harga coret mengikuti harga normal aset
- [ ] Koordinat lokasi tampil dan tombol Google Maps berfungsi
- [ ] Retest oleh QA

---

## 3. Form Pengajuan Peminatan Belum Sesuai Desain Figma

**Overview**

> Form pengajuan peminatan aset baru di portal External saat ini masih tampil dalam 1 halaman panjang (semua bagian ditumpuk dalam satu halaman). Form perlu disesuaikan mengikuti desain Figma terbaru, yaitu alur bertahap per step.

**Steps to Reproduce**

1. Login portal External sebagai nasabah, buka detail aset
2. Klik "Ajukan Peminatan Unit"
3. Lihat tampilan form pengajuan peminatan

**Actual Result**

- Form tampil 1 halaman panjang: Bagian 1 sampai Bagian 5 ditumpuk dalam satu halaman, tombol "Kirim Pengajuan Lead" langsung ada di halaman yang sama

**Expected Result**

- Form mengikuti desain Figma "BSN Lelang" (Pengajuan Peminatan):
  - Step 1: Data Properti & Akad, termasuk modal popup "Pilih & Ganti Aset Unit Properti"
  - Step 2: Data Pemohon
  - Step 3: Data Pekerjaan & Finansial
  - Step 4: Dokumen Pendukung
- Satu step tampil dalam satu halaman, pindah step dengan tombol lanjut/kembali

**Technical Context**

| Item | Value |
|---|---|
| Portal | External (nasabah) |
| Modul | Aset Baru — Form Pengajuan Peminatan |
| Referensi | Desain Figma "BSN Lelang" — Pengajuan Peminatan Step 1, Step 1 Modal Popup, Step 2, Step 3 |
| Environment | Sandbox (terasrumah-sandbox.zegen.app) |
| Tanggal temuan | 24 Nov 2026 |

**Logs & Media**

- evidence_20_figma-form-baru.png (desain Figma: Step 1, Step 1 Modal Popup, Step 2, Step 3)
- evidence_21_form-saat-ini.png (form saat ini: 1 halaman panjang)

**Checklist for Fix**

- [ ] Form diubah menjadi alur bertahap sesuai desain Figma
- [ ] Modal "Pilih & Ganti Aset Unit Properti" tersedia di Step 1
- [ ] Retest oleh QA
