🐞 [BUG] | Tiket Tidak Terbentuk setelah Lead Ditindaklanjuti

**Priority:** Urgent 🔴

**Label:** `bug` `triage-needed` `Tiket`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Lead tes #ENT-01m8-8153 yang sudah ditindaklanjuti dan berstatus Terverifikasi tidak membentuk tiket di Tiket Aset Baru, baik di Board, Tabel, maupun pencarian.

* **Impact:** Lead yang sudah terverifikasi tidak bisa diproses ke tahap berikutnya karena tiketnya tidak pernah terbentuk
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Leads Aset Baru**, lalu buka lead tes #ENT-01m8-8153.
3. Lakukan aksi: **Isi Input Hasil Tindak Lanjut (Hot Lead, WhatsApp, checklist) - Klik Simpan sampai status menjadi Terverifikasi - Buka menu Tiket Aset Baru (Board dan Tabel) dan cari lead tersebut**.
4. Amati hasil yang tampil.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Setelah lead Terverifikasi, tiket terbentuk otomatis di Tiket Aset Baru dan lead dapat diproses ke tahap berikutnya |
| **Actual** | Tidak ada tiket untuk lead tes di Board, Tabel, maupun pencarian Tiket Aset Baru |
| **Environment** | Staging (Sandbox) |
| **Device/OS** | Web / Chrome |
| **User Role** | Admin Internal (Superadmin) |

## 🪵 Logs & Media

* **Screenshots:** (Drag and drop images here)
* **Console Logs:**

```bash
# Paste any relevant stack traces or console errors here
Uncaught TypeError: Cannot read properties of undefined (reading 'id')
```

## ✅ Checklist for Fix

• [ ] Reproduce locally.
• [ ] Add regression test.
• [ ] Verify fix in Staging.
• [ ] Update documentation (if behavior changed).

---
Catatan draft (tidak masuk Huly):
* Status: DRAFT, menunggu ACC Muhammad — belum dibuat folder resmi / issue Huly / entri tracker.
* Evidence lokal: evidence_01_tiket-tidak-terbentuk_redbox.png (folder eksplorasi-leads-tiket/evidence)
* Sumber: eksplorasi Internal Leads & Tiket Aset Baru, 24 Nov 2026 sore. Belum terverifikasi ulang (auth Internal rusak sejak 24 Nov malam).
