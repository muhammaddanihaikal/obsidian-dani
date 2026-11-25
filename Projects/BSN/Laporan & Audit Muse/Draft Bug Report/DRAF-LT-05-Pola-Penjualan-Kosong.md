🐞 [BUG] | Data Pola Penjualan pada Lead Tidak Terisi sehingga Tidak Ditemukan Filter

**Priority:** Normal 🟡

**Label:** `bug` `triage-needed` `Leads`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Sebagian besar lead datanya kosong pada kolom Pola Penjualan, sehingga tidak bisa ditemukan lewat filter Pola Penjualan.
>
> * Dari 4 lead, hanya 1 lead yang terisi Pola Penjualan ("Primary Main"); 3 lead lain termasuk lead tes tampil "-".
> * Akibatnya filter "Primary Discount" menghasilkan 0 lead dan filter "Primary Main" hanya 1 lead.
> * Field ini terbukti bisa terisi (ada lead yang punya nilai), jadi masalahnya data pola penjualan tidak terisi saat lead terbentuk.

* **Impact:** Staff tidak bisa menemukan lead lewat filter Pola Penjualan karena data lead-nya kosong
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Leads Aset Baru**, perhatikan kolom Pola Penjualan pada daftar lead.
3. Lakukan aksi: **Pilih filter Pola Penjualan "Primary Discount", lalu "Primary Main"**.
4. Amati hasil yang tampil.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Setiap lead memiliki Pola Penjualan terisi sesuai pola penjualan pengajuan / asetnya, dan filter menampilkan lead yang sesuai |
| **Actual** | 3 dari 4 lead tampil "-" pada Pola Penjualan; filter Primary Discount = 0 lead dan Primary Main = 1 lead |
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
* Status: DITAHAN atas arahan Muhammad (25 Nov 2026) — tidak dilanjutkan dulu. DRAFT, menunggu ACC Muhammad — belum dibuat folder resmi / issue Huly / entri tracker.
* Evidence lokal: evidence_05_filter-pola-penjualan-kosong_redbox.png (folder eksplorasi-leads-tiket/evidence)
* Sumber: eksplorasi Internal Leads & Tiket Aset Baru, 24 Nov 2026 sore. Belum terverifikasi ulang (auth Internal rusak sejak 24 Nov malam).
