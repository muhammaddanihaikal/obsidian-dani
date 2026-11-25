🐞 [BUG] | Nama Developer, Harga Coret dan Koordinat pada Detail Aset Belum Sesuai

**Priority:** Normal 🟡

**Label:** `bug` `triage-needed` `Aset Baru`

**Linked Issue/PR:** # -

## 📖 Overview

> Tiga data pada halaman detail aset di portal External belum sesuai:

* Nama developer: selalu tertulis PT Sinar Mas Land Tbk di semua aset
* Harga coret: selalu dihitung dari harga dikali 1,25
* Koordinat lokasi: tidak tersedia, tombol Buka Google Maps tidak berfungsi

* **Impact:** Nasabah menerima informasi developer dan harga yang salah, dan tidak bisa membuka lokasi aset di Google Maps.
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Log in ke portal External sebagai nasabah.
2. Navigate to Aset Baru, lalu buka detail aset (contoh: JKHS-10007).
3. Lihat card "INFORMASI DEVELOPER REKANAN": tertulis PT Sinar Mas Land Tbk, padahal developer aset ini adalah PT Harmoni Properti Nusantara, sesuai card di katalog.
4. Lihat card "HARGA DEVELOPER REKANAN": harga Rp 500 Juta tampil dengan harga coret Rp 625 Juta dan label "Hemat Rp 125 Juta". Harga coret selalu dihitung harga dikali 1,25.
5. Scroll ke bagian "Aksesibilitas & Lokasi Strategis": peta menulis "Koordinat lokasi tidak tersedia" dan tombol "Buka Google Maps" tidak berfungsi saat diklik.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Nama developer pada detail sesuai data aset, harga coret sesuai harga normal aset, koordinat lokasi tampil, dan tombol Buka Google Maps membuka lokasi aset. |
| **Actual** | Nama developer selalu PT Sinar Mas Land Tbk di semua aset, harga coret selalu harga dikali 1,25, koordinat lokasi tidak tersedia, dan tombol Buka Google Maps tidak berfungsi. |
| **Environment** | Staging (terasrumah-sandbox.zegen.app) |
| **Device/OS** | Web / Chrome |
| **User Role** | Nasabah (External) |

## 🪵 Logs & Media

* **Screenshots:** (Drag and drop images here) — file draft lokal: evidence_22_detail-desktop-3kotak_redbox.png (detail aset ukuran desktop, 3 kotak merah: harga coret, koordinat, developer)
* **Console Logs:** -

## ✅ Checklist for Fix

• [ ] Reproduce locally.
• [ ] Add regression test.
• [ ] Verify fix in Staging.
• [ ] Update documentation (if behavior changed).
