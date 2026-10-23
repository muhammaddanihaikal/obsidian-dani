# Regression Test - BSN Fase 1

Tracking progres regression test dan bug yang ditemukan selama sesi pengetesan.
**PIC QA**: Dani | **Tanggal Mulai**: 2026-10-23

---

## 📊 Progress Summary

| No | Menu | Sub Menu | Status |
|----|------|----------|--------|
| 1 | Authentication | Logout | 🐛 Bug |

---

## 📌 Status Input Issue ke Huly

| No | Modul / Sub Menu | Total Bug | Status Huly | Rincian Issue |
|----|------------------|-----------|-------------|---------------|
| 1 | **Authentication** | 1 | ⏳ Pending (0/1) | Logout (1) |
| **Total** | | **1** | **0 Reported / 1 Pending** | |

---

## 🐛 Bug Report / Isu Temuan

### 🐞 [BUG] | Authentication - Logout: Gagal Keluar Akun dan Muncul Halaman Error

> * **Menu**: Authentication → Logout
> * **Status**: Open
> * **Deskripsi**: Saat user menekan button Keluar pada dropdown profil di pojok kanan atas, proses logout gagal diproses.
> * **Expected**: Sistem berhasil membersihkan session login user dan mengarahkan kembali ke halaman Login.
> * **Actual**: Sistem mengarahkan user ke halaman error dengan pesan "Permintaan Tidak Dapat Diproses" dan user gagal logout.
> * **Evidence Awal**:
>   * [https://files.catbox.moe/ujkwhl.png](https://files.catbox.moe/ujkwhl.png)
>   * [https://files.catbox.moe/mbunqm.png](https://files.catbox.moe/mbunqm.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
