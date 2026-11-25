🐞 [BUG] | Card Perlu Tindak Lanjut Tidak Berubah setelah Tindak Lanjut Disimpan

**Priority:** Normal 🟡

**Label:** `bug` `triage-needed` `Leads`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Card ringkasan Perlu Tindak Lanjut tidak berubah setelah tindak lanjut lead disimpan, padahal tab status sudah berubah dengan benar.
>
> * Setelah tindak lanjut lead tes disimpan: tab berubah benar menjadi Tindak Lanjut 2 / Terverifikasi 2, tapi card tetap menampilkan 4 dengan keterangan "2 SLA Kritis" (harusnya 2).
> * Card juga tidak berubah saat filter dipakai: tetap 4 walaupun hasil filter 0 lead.

* **Impact:** Staff membaca jumlah lead yang perlu ditindaklanjuti dari card yang basi, tidak sesuai kondisi sebenarnya
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Leads Aset Baru**, catat angka pada card Perlu Tindak Lanjut.
3. Lakukan aksi: **Tindaklanjuti lead tes sampai Terverifikasi, lalu bandingkan angka card dengan tab status**.
4. Amati hasil yang tampil.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Card Perlu Tindak Lanjut ikut berubah mengikuti data terbaru (menjadi 2, sama seperti tab Tindak Lanjut) |
| **Actual** | Card tetap menampilkan 4 ("2 SLA Kritis") setelah tindak lanjut disimpan, dan tetap 4 saat hasil filter 0 lead |
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
* Evidence lokal: evidence_04_kartu-tindak-lanjut-tidak-update_redbox.png (folder eksplorasi-leads-tiket/evidence)
* Sumber: eksplorasi Internal Leads & Tiket Aset Baru, 24 Nov 2026 sore. Belum terverifikasi ulang (auth Internal rusak sejak 24 Nov malam).
