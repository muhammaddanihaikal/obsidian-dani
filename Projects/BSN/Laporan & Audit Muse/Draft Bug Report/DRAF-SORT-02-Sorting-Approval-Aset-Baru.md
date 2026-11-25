🐞 [BUG] | Sorting pada Tabel Approval Aset Baru Tidak Berfungsi

**Priority:** High 🟠

**Label:** `bug` `triage-needed` `Stock Management`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Sorting pada tabel Approval Aset Baru tidak berfungsi: header kolom diklik, tetapi urutan baris tidak berubah sama sekali.
>
> * Header Harga Pengajuan (satu-satunya kolom yang menampilkan ikon sort ⇅) diklik 2 kali: urutan tetap JPMS-10001 Rp450.000.000, MKSS-10011 Rp345.000.000, JKHS-10014 Rp500.000.000.
> * Header Tanggal Diajukan diklik: urutan juga tidak berubah.
> * Header kolom pada tabel ini berfungsi sebagai handle untuk menggeser urutan kolom (drag), bukan untuk sorting.

* **Impact:** User tidak bisa mengurutkan pengajuan berdasarkan harga atau tanggal masuk, jadi harus memeriksa baris satu per satu secara manual
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Stock Management → Approval Aset Baru**.
3. Lakukan aksi: **Klik header kolom Harga Pengajuan dua kali, lalu klik header kolom Tanggal Diajukan satu kali**.
4. Amati hasil yang tampil: urutan baris tidak berubah sama sekali pada kedua kolom.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Setiap kolom berikon sort mengurutkan baris dengan benar: klik pertama menaik (A–Z / termurah / terlama), klik kedua menurun (kebalikannya) |
| **Actual** | Semua kolom yang dicoba mati total, termasuk Harga Pengajuan yang berikon sort dan Tanggal Diajukan; URL juga tidak pernah mendapat parameter sort setelah header diklik |
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
* Status: DRAFT, menunggu ACC Muhammad — belum dibuat folder resmi / issue Huly baru.
* Hasil pisah dari issue gabungan BSN_I-170 atas permintaan Muhammad (25 Nov 2026). Rencana setelah ACC: buat issue baru khusus Approval Aset Baru, lalu BSN_I-170 dihapus.
* Diverifikasi ulang live 25 Nov 2026 pukul 17:20 WIB (16 pengajuan, tab Approval Input Aset): header Harga Pengajuan 2x klik dan Tanggal Diajukan 1x klik, urutan tidak berubah.
* Evidence: i170_approval-tabel-header_redbox.png (SS desktop 1919×998, folder ss-desktop-2026-11-25/redbox).
