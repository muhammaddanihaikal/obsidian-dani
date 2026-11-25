🐞 [BUG] | Form Pengajuan Peminatan Belum Sesuai Desain Figma
**Priority:** Normal 🟡
**Label:** `bug` `triage-needed` `Aset Baru`
**Linked Issue/PR:** # -
## 📖 Overview
> Form pengajuan peminatan aset baru di portal External saat ini tampil dalam satu halaman panjang, semua bagian form ditumpuk di satu halaman. Tampilan ini belum sesuai desain Figma terbaru yang membagi form menjadi beberapa step.
* **Impact:** Alur pengisian form menjadi panjang dalam satu halaman dan belum mengikuti desain yang sudah dibuat.
* **Frequency:** 100% of the time
## 🛠 Steps to Reproduce
1. Log in ke portal External sebagai nasabah.
2. Navigate to Aset Baru, buka detail aset, lalu klik "Ajukan Peminatan Unit".
3. Perhatikan form yang tampil: Bagian 1 sampai Bagian 5 berada dalam satu halaman panjang, dengan tombol "Kirim Pengajuan Lead" di halaman yang sama.
4. Bandingkan dengan desain Figma "BSN Lelang" (Pengajuan Peminatan): form dibagi menjadi Step 1 Data Properti & Akad (dengan modal popup "Pilih & Ganti Aset Unit Properti"), Step 2 Data Pemohon, Step 3 Data Pekerjaan & Finansial, dan Step 4 Dokumen Pendukung.
## 🔍 Technical Context
| Field | Detail |
|---|---|
| **Expected** | Form pengajuan peminatan tampil bertahap sesuai desain Figma: satu step dalam satu halaman, mulai dari Step 1 Data Properti & Akad sampai Step 4 Dokumen Pendukung. |
| **Actual** | Form tampil dalam satu halaman panjang dan belum dibagi per step seperti desain Figma. |
| **Environment** | Staging (terasrumah-sandbox.zegen.app) |
| **Device/OS** | Web / Chrome |
| **User Role** | Nasabah (External) |
## 🪵 Logs & Media
* **Screenshots:** (Drag and drop images here) — file draft lokal: evidence_21_form-saat-ini.png (form saat ini, satu halaman panjang) dan evidence_20_figma-form-baru.png (desain Figma: Step 1, Step 1 Modal Popup, Step 2, Step 3)
* **Console Logs:** -
## ✅ Checklist for Fix
• [ ] Reproduce locally.
• [ ] Add regression test.
• [ ] Verify fix in Staging.
• [ ] Update documentation (if behavior changed).
