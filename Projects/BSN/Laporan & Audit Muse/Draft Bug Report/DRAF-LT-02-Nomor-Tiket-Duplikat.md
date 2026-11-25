🐞 [BUG] | Nomor Tiket Duplikat pada Dua Lead Berbeda

**Priority:** High 🟠

**Label:** `bug` `triage-needed` `Tiket`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Dua lead berbeda menampilkan nomor tiket yang sama persis.
>
> * Lead tes #ENT-01m8-8153 dan lead Elina sama-sama menampilkan nomor tiket #TKT-2024-0891.
> * Tahun pada nomor tiket adalah 2024, padahal lead dibuat tahun 2026.

* **Impact:** Nomor tiket tidak bisa dipakai sebagai identitas unik, rawan tertukar saat tracking dan komunikasi ke nasabah
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Leads Aset Baru**.
3. Lakukan aksi: **Buka detail lead tes #ENT-01m8-8153 dan lead Elina, lalu bandingkan nomor tiketnya**.
4. Amati hasil yang tampil.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Setiap lead / tiket memiliki nomor tiket unik yang berbeda, dengan tahun sesuai tahun pembuatan |
| **Actual** | Kedua lead menampilkan nomor tiket yang sama: #TKT-2024-0891 |
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
* Evidence lokal: evidence_02_nomor-tiket-duplikat_redbox.png (folder eksplorasi-leads-tiket/evidence)
* Sumber: eksplorasi Internal Leads & Tiket Aset Baru, 24 Nov 2026 sore. Belum terverifikasi ulang (auth Internal rusak sejak 24 Nov malam).
