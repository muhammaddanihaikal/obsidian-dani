🐞 [BUG] | Simulasi DP dan Angsuran pada Drawer Leads Tidak Sesuai Harga Aset

**Priority:** Normal 🟡

**Label:** `bug` `triage-needed` `Leads`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Nilai simulasi DP dan angsuran pada drawer Leads sama untuk harga aset yang berbeda, tidak dihitung dari harga aset lead.
>
> * Lead tes (aset Rp500.000.000): DP (10%) tampil Rp85.000.000, angsuran Rp6.380.000/bln.
> * Lead Elina (aset Rp300.000.000): DP dan angsuran tampil sama persis, Rp85.000.000 dan Rp6.380.000/bln.
> * Nilai yang benar untuk lead tes: DP 10% x Rp500.000.000 = Rp50.000.000. Sebagai pembanding, detail tiket Elina menampilkan angka yang benar (DP Rp30.000.000).

* **Impact:** Staff melihat simulasi pembayaran yang salah dan bisa menyampaikan angka yang keliru ke nasabah
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Leads Aset Baru**.
3. Lakukan aksi: **Buka drawer lead tes (aset Rp500jt) dan lead Elina (aset Rp300jt), lalu bandingkan nilai DP dan angsurannya**.
4. Amati hasil yang tampil.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | DP tampil 10% dari harga aset masing-masing lead (lead tes Rp50.000.000, Elina Rp30.000.000) dan angsuran dihitung dari plafon serta tenor lead tersebut |
| **Actual** | Kedua lead menampilkan DP Rp85.000.000 dan angsuran Rp6.380.000/bln yang sama persis |
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
* Evidence lokal: evidence_03_simulasi-dp-dummy_redbox.png (folder eksplorasi-leads-tiket/evidence)
* Sumber: eksplorasi Internal Leads & Tiket Aset Baru, 24 Nov 2026 sore. Belum terverifikasi ulang (auth Internal rusak sejak 24 Nov malam).
