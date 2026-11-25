🐞 [BUG] | Kolom Nomor Tiket Menampilkan ID Lead dan Card VOA Menampilkan Rp0

**Priority:** Normal 🟡

**Label:** `bug` `triage-needed` `Tiket`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Dua tampilan di halaman Tiket Aset Baru tidak sesuai datanya.
>
> * Kolom Nomor Tiket pada tabel Tiket menampilkan ENT-01m7-2727, yaitu ID lead Elina, bukan nomor tiket.
> * Card VOA Nilai Tiket Aset Baru menampilkan Rp0, padahal ada tiket Elina senilai Rp300.000.000 yang sedang tahap Proses.

* **Impact:** Staff membaca nomor tiket yang salah dan total nilai tiket tampil nol, tidak sesuai kondisi sebenarnya
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Tiket Aset Baru**, lalu buka tampilan Tabel.
3. Lakukan aksi: **Periksa kolom Nomor Tiket pada baris tiket Elina dan nilai pada card VOA Nilai Tiket Aset Baru**.
4. Amati hasil yang tampil.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Kolom Nomor Tiket menampilkan nomor tiket (format #TKT-...) dan card VOA menampilkan total nilai tiket aktif (Rp300.000.000) |
| **Actual** | Kolom Nomor Tiket menampilkan ID lead ENT-01m7-2727 dan card VOA menampilkan Rp0 |
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
* Evidence lokal: evidence_08_nomor-tiket-id-lead-voa-nol_redbox.png (folder eksplorasi-leads-tiket/evidence)
* Sumber: eksplorasi Internal Leads & Tiket Aset Baru, 24 Nov 2026 sore. Belum terverifikasi ulang (auth Internal rusak sejak 24 Nov malam).
