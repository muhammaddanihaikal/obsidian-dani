# Regression Test - BSN Fase 1

Tracking progres regression test dan bug yang ditemukan selama sesi pengetesan.
**PIC QA**: Dani | **Tanggal Mulai**: 2026-10-23

---

## 📊 Progress Summary

| No | Menu | Sub Menu | Status |
|----|------|----------|--------|
| 1 | Authentication | Logout | 🐛 Bug |
| 2 | Authentication | Login | 🐛 Bug |
| 3 | User Management | Role | 🐛 Bug |
| 4 | User Management | User | 🐛 Bug |

---

## 📌 Status Input Issue ke Huly

| No | Modul / Sub Menu | Total Bug | Status Huly | Rincian Issue |
|----|------------------|-----------|-------------|---------------|
| 1 | **Authentication** | 2 | ⏳ Pending (0/2) | Logout (1), Login (1) |
| 2 | **User Management** | 5 | ⏳ Pending (0/5) | Role (4), User (1) |
| **Total** | | **7** | **0 Reported / 7 Pending** | |

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

<br>

### 🐞 [BUG] | User Management - Role: Gagal Menambah Role Baru Muncul Error 415

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi form modal Tambah Role dan menekan button Tambah, proses simpan gagal diproses oleh sistem.
> * **Expected**: Data role baru berhasil ditambahkan dan langsung terdaftar pada list Daftar Role.
> * **Actual**: Muncul toast error "Gagal menambah role" dengan keterangan `code=415, message=Unsupported Media Type` dan data role baru tidak tersimpan.
> * **Evidence Awal**:
>   * Toast Error Tambah Role: [https://files.catbox.moe/y85oza.png](https://files.catbox.moe/y85oza.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | User Management - Role: Gagal Menghapus Role Muncul Toast Error

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user menekan icon hapus pada salah satu data role dan mengonfirmasi dengan button Ya, Hapus, proses penghapusan gagal diproses sistem.
> * **Expected**: Data role berhasil dihapus dan otomatis terhapus dari list Daftar Role.
> * **Actual**: Muncul toast error "Gagal menghapus role" dengan pesan "Oops something went wrong, Contact Developer for the issue" dan data role tetap ada di list.
> * **Evidence Awal**:
>   * Modal Konfirmasi Hapus: [https://files.catbox.moe/a2dlfq.png](https://files.catbox.moe/a2dlfq.png)
>   * Toast Error Hapus: [https://files.catbox.moe/ypdpob.png](https://files.catbox.moe/ypdpob.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | User Management - Role: Gagal Menyimpan Aksi Role Muncul Error 415

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user memilih checkbox pada bagian Aksi Umum Role dan menekan button Simpan Aksi, proses penyimpanan gagal diproses sistem.
> * **Expected**: Pengaturan aksi umum role berhasil disimpan dan sistem memunculkan toast konfirmasi sukses.
> * **Actual**: Muncul toast error "Gagal menyimpan aksi role" dengan pesan `code=415, message=Unsupported Media Type` dan data aksi tidak tersimpan.
> * **Evidence Awal**:
>   * Toast Error Simpan Aksi Role: [https://files.catbox.moe/x29f8c.png](https://files.catbox.moe/x29f8c.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | User Management - Role: Gagal Mengubah Role Muncul Error 415

> * **Menu**: User Management → Role
> * **Status**: Open
> * **Deskripsi**: Saat user mengedit data role pada modal Ubah Role dan menekan button Simpan, proses pembaruan data gagal diproses sistem.
> * **Expected**: Perubahan data role berhasil diperbarui dan tersimpan pada list Daftar Role.
> * **Actual**: Muncul toast error "Gagal mengubah role" dengan pesan `code=415, message=Unsupported Media Type` dan data role tidak ter-update.
> * **Evidence Awal**:
>   * Toast Error Ubah Role: [https://files.catbox.moe/c6n1h7.png](https://files.catbox.moe/c6n1h7.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | User Management - User: Dropdown Pilihan Kantor Kosong (No Data)

> * **Menu**: User Management → User
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi form tambah user dan membuka dropdown Kantor, opsi daftar kantor tidak muncul dan hanya menampilkan status "No data".
> * **Expected**: Dropdown Kantor menampilkan seluruh daftar kantor cabang yang aktif dan dapat dipilih oleh user.
> * **Actual**: Dropdown Kantor kosong dan hanya menampilkan "No data", sehingga proses submit data user tidak dapat diselesaikan.
> * **Evidence Awal**:
>   * Dropdown Kantor No Data: [https://files.catbox.moe/u2z6fh.png](https://files.catbox.moe/u2z6fh.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
