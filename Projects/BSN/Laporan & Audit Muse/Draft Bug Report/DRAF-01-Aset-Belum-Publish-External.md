🐞 [BUG] | Aset yang Belum Publish Tampil di Katalog External
**Priority:** High 🟠
**Label:** `bug` `triage-needed` `Aset Baru`
**Linked Issue/PR:** # -
## 📖 Overview
> Katalog Aset Baru di portal External menampilkan 6 aset. Padahal aset yang sudah publish di Internal hanya 4. Dua aset yang belum publish (JKHS-10001 dan JKHS-10004) ikut tampil, detailnya bisa dibuka, dan bisa diajukan peminatan.
* **Impact:** Nasabah bisa melihat dan mengajukan peminatan untuk aset yang belum disetujui untuk dijual.
* **Frequency:** 100% of the time
## 🛠 Steps to Reproduce
1. Log in to the workspace (Internal, role Superadmin).
2. Navigate to Stock Management → Aset Baru, lalu buka tab Published: totalnya 4 aset.
3. Log in ke portal External sebagai nasabah, lalu buka menu Aset Baru.
4. Perhatikan katalog: tampil 6 aset, termasuk JKHS-10001 (Menunggu Verifikasi) dan JKHS-10004 (Butuh Revisi) yang berstatus "Belum Publish".
5. Klik salah satu aset tersebut: halaman detail terbuka dan tombol ajukan peminatan aktif.
## 🔍 Technical Context
| Field | Detail |
|---|---|
| **Expected** | Katalog External hanya menampilkan 4 aset yang sudah Published di Internal. Aset yang belum publish tidak tampil dan tidak bisa diakses dari External. |
| **Actual** | Katalog External menampilkan 6 aset. JKHS-10001 dan JKHS-10004 yang belum publish ikut tampil, detailnya bisa dibuka, dan peminatan bisa diajukan. |
| **Environment** | Staging (terasrumah-sandbox.zegen.app) |
| **Device/OS** | Web / Chrome |
| **User Role** | Nasabah (External) |
## 🪵 Logs & Media
* **Screenshots:** (Drag and drop images here) — file draft lokal: evidence_01_total-6-aset_redbox.png (katalog External, kotak merah pada keterangan "Menampilkan 1–6 dari total 6")
* **Console Logs:** -
## ✅ Checklist for Fix
• [ ] Reproduce locally.
• [ ] Add regression test.
• [ ] Verify fix in Staging.
• [ ] Update documentation (if behavior changed).
