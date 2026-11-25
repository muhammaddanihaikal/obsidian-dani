🐞 [BUG] | Sorting pada Tabel Aset Baru Tidak Berfungsi

**Priority:** High 🟠

**Label:** `bug` `triage-needed` `Stock Management`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> Sorting pada tabel Aset Baru tidak mengurutkan data dengan benar.
>
> * Header Nilai Harga Agunan diklik 2 kali: urutan baris tidak berubah sama sekali (tetap diawali JPMS-10002 Rp1.200.000.000, MKSS-10013 Rp350.000.000, JKHS-10015 Rp0).
> * Header Kode & Unit Aset diklik: urutan baris berubah, tetapi hasilnya acak, bukan urutan A–Z maupun kebalikannya. Klik kedua menghasilkan urutan acak yang berbeda lagi.

* **Impact:** User tidak bisa mengurutkan aset berdasarkan harga atau kode, jadi harus memeriksa baris satu per satu secara manual
* **Frequency:** 100% of the time

## 🛠 Steps to Reproduce

1. Login ke workspace (Internal, role Superadmin).
2. Buka menu **Stock Management → Aset Baru**.
3. Lakukan aksi: **Klik header kolom Nilai Harga Agunan dua kali, lalu klik header kolom Kode & Unit Aset dua kali**.
4. Amati hasil yang tampil: urutan baris tidak berubah saat header Harga diklik, dan berubah secara acak (bukan urutan yang benar) saat header Kode diklik.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | Setiap kolom berikon sort mengurutkan baris dengan benar: klik pertama menaik (A–Z / termurah / terlama), klik kedua menurun (kebalikannya) |
| **Actual** | Header Nilai Harga Agunan mati total (urutan tidak berubah); header Kode & Unit Aset mengubah urutan secara acak, bukan hasil sorting, dan klik kedua bukan kebalikan dari klik pertama |
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
* Hasil pisah dari issue gabungan BSN_I-170 atas permintaan Muhammad (25 Nov 2026). Rencana setelah ACC: buat issue baru khusus Aset Baru, lalu BSN_I-170 dihapus.
* Diverifikasi ulang live 25 Nov 2026 pukul 17:36 WIB (21 aset, halaman 1): header Nilai Harga Agunan 2x klik tanpa perubahan; header Kode & Unit Aset mengacak urutan.
* Evidence: i170_asetbaru-tabel-header_redbox.png (SS desktop 1920×1000, folder ss-desktop-2026-11-25/redbox). Evidence lama dari eksplorasi 23 Nov: evidence_01_sorting_harga_redbox.png (folder resmi issue gabungan).
