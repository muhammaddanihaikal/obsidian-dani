# Regression Test - BSN Fase 1

Tracking progres regression test dan bug yang ditemukan selama sesi pengetesan.
**PIC QA**: Dani | **Tanggal Mulai**: 2026-10-23

---

## 📊 Progress Summary

| No | Menu | Sub Menu | Status |
|----|------|----------|--------|
| 1 | Authentication | Logout | 🐛 Bug |
| 2 | Authentication | Login | 🐛 Bug |

---

## 📌 Status Input Issue ke Huly

| No | Modul / Sub Menu | Total Bug | Status Huly | Rincian Issue |
|----|------------------|-----------|-------------|---------------|
| 1 | **Authentication** | 2 | ⏳ Pending (0/2) | Logout (1), Login (1) |
| **Total** | | **2** | **0 Reported / 2 Pending** | |

---

## 🐛 Bug Report / Isu Temuan

### 🐞 [BUG] | Authentication - Logout: Gagal Keluar Akun dan Muncul Halaman Error

> * **Menu**: Authentication → Logout
> * **Status**: Open
> * **Deskripsi**: Saat user menekan button Keluar pada dropdown profil di pojok kanan atas, proses logout gagal diproses.
> * **Expected**: Sistem berhasil membersihkan session login user dan mengarahkan kembali ke halaman Login.
> * **Actual**: Sistem mengarahkan user ke halaman error dengan pesan "Permintaan Tidak Dapat Diproses" dan user gagal logout.
> * **Evidence Awal**:
>   * Button Keluar: [https://files.catbox.moe/ujkwhl.png](https://files.catbox.moe/ujkwhl.png)
>   * Halaman Error: [https://files.catbox.moe/mbunqm.png](https://files.catbox.moe/mbunqm.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Authentication - Login: Button "Masuk dengan akun lain" Tidak Berfungsi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman Konfirmasi Identitas dan menekan button Masuk dengan akun lain, tidak ada respons apa pun dari sistem.
> * **Expected**: Sistem mengarahkan user kembali ke form login awal untuk memasukkan email atau akun yang berbeda.
> * **Actual**: Button Masuk dengan akun lain tidak berfungsi saat ditekan dan user tetap tertahan di halaman Konfirmasi Identitas.
> * **Evidence Awal**:
>   * Button Masuk Akun Lain: [https://files.catbox.moe/n4w7iw.png](https://files.catbox.moe/n4w7iw.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
