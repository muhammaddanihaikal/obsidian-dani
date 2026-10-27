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
| 5 | Office Management | Office Type | 🐛 Bug |
| 6 | Authentication (External) | Register Nasabah | 🐛 Bug |
| 7 | Authentication (External) | Login | 🐛 Bug |

---

## 📌 Status Input Issue ke Huly

| No | Modul / Sub Menu | Total Bug | Status Huly | Rincian Issue |
|----|------------------|-----------|-------------|---------------|
| 1 | **Authentication** | 4 | ⏳ Pending (0/4) | Logout (2), Login (1), Lupa Kata Sandi (1) |
| 2 | **User Management** | 5 | ⏳ Pending (0/5) | Role (4), User (1) |
| 3 | **Office Management** | 3 | ⏳ Pending (0/3) | Office Type (3) |
| 4 | **Authentication (External)** | 13 | ⏳ Pending (0/13) | Register Nasabah (4), Login (7), Lupa Kata Sandi (2) |
| 5 | **Beranda (External)** | 2 | ⏳ Pending (0/2) | Header (2) |
| 6 | **User Profile (External)** | 1 | ⏳ Pending (0/1) | Profile Tabs (1) |
| **Total** | | **28** | **0 Reported / 28 Pending** | |

---

## 🏷️ Matriks Status Issue QA

| Status | Total | Rincian Issue |
|--------|:-----:|---------------|
| 🟢 **Done** | 0 | - |
| 🔴 **Open** | 26 | 12 Issue Internal, 14 Issue External |
| 🟡 **Catatan / Klarifikasi** | 2 | • `External/Authentication/06`: Validasi Kata Sandi Breached Muncul di Akhir<br>• `External/Authentication/09`: Label Banner Login External Tertulis Sistem Portal Internal |
| 🔄 **Re-Open** | 0 | - |

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

<br>

### 🐞 [BUG] | Office Management - Office Type: Button Hapus Tetap Aktif Pada Parent Root

> * **Menu**: Office Management → Office Type
> * **Status**: Open
> * **Deskripsi**: Pada tabel daftar tipe kantor, baris data dengan parent Root (Kantor Pusat) masih memiliki button hapus yang aktif pada kolom Action.
> * **Expected**: Data tipe kantor yang menjadi parent "Root" tidak dapat dihapus (button hapus dinonaktifkan/disabled atau disembunyikan).
> * **Actual**: Button hapus pada baris data parent "Root" tetap tampil aktif dan dapat ditekan oleh user.
> * **Evidence Awal**:
>   * Button Hapus Parent Root: [https://files.catbox.moe/210map.png](https://files.catbox.moe/210map.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Authentication - Logout: Button Halaman Utama Gagal Redirect ke Login Internal

> * **Menu**: Authentication → Logout
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman auto-logout dan menekan button Halaman Utama, sistem gagal mengarahkan kembali ke form login portal internal.
> * **Expected**: Button Halaman Utama mengarahkan user kembali ke halaman Login Portal Internal BSN.
> * **Actual**: Sistem mengarahkan user ke path URL yang salah dan berujung pada halaman 404 situs publik.
> * **Evidence Awal**:
>   * Button Halaman Utama: [https://files.catbox.moe/p3u8zt.png](https://files.catbox.moe/p3u8zt.png)
>   * Hasil Redirect Error: [https://files.catbox.moe/bgx4u8.png](https://files.catbox.moe/bgx4u8.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Dropdown Pilihan Parent Kosong No Data

> * **Menu**: Office Management → Office Type
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi form tambah tipe kantor dan membuka dropdown Parent, daftar pilihan parent tidak muncul dan hanya menampilkan status "No data".
> * **Expected**: Dropdown Parent menampilkan daftar opsi tipe kantor (misal: Root, Kantor Pusat, dll.) yang dapat dipilih sebagai induk hierarki.
> * **Actual**: Dropdown Parent kosong dan hanya menampilkan "No data", sehingga proses penambahan tipe kantor baru terhambat.
> * **Evidence Awal**:
>   * Dropdown Parent No Data: [https://files.catbox.moe/iw6luy.png](https://files.catbox.moe/iw6luy.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Filter Pencarian Tipe Kantor Belum Berfungsi

> * **Menu**: Office Management → Office Type
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi parameter pencarian pada bar filter dan menekan button Cari, sistem tidak melakukan penyaringan data pada tabel.
> * **Expected**: Tabel menampilkan daftar tipe kantor yang sesuai dengan kriteria filter yang dimasukkan oleh user.
> * **Actual**: Fitur filter belum berfungsi dan tabel tidak merespons perubahan data pencarian setelah button Cari ditekan.
> * **Evidence Awal**:
>   * Filter Tipe Kantor: [https://files.catbox.moe/cuno1j.png](https://files.catbox.moe/cuno1j.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Validasi Konfirmasi Kata Sandi Tidak Hilang Meskipun Password Sesuai

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Open
> * **Deskripsi**: Saat user mengisi field Konfirmasi Kata Sandi dengan nilai yang identik dan telah memenuhi seluruh kriteria keamanan, teks peringatan validasi di bawah field tidak hilang.
> * **Expected**: Peringatan validasi otomatis hilang saat input Konfirmasi Kata Sandi sudah cocok dengan Kata Sandi.
> * **Actual**: Pesan "Kata sandi harus terdiri dari huruf besar, huruf kecil, angka, dan karakter khusus." tetap muncul dan tidak berubah meskipun password sudah sesuai.
> * **Evidence Awal**:
>   * Peringatan Validasi Konfirmasi: [https://files.catbox.moe/5dlimo.png](https://files.catbox.moe/5dlimo.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Submit Pendaftaran Tidak Menampilkan Notifikasi dan Gagal Redirect ke Login

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Open
> * **Deskripsi**: Saat user menyetujui Syarat & Ketentuan di langkah terakhir dan menekan button Daftar Sekarang, tidak ada notifikasi sukses dan user diarahkan kembali ke halaman pendaftaran.
> * **Expected**: Sistem memunculkan notifikasi/informasi pendaftaran berhasil dan langsung mengarahkan user ke halaman Login.
> * **Actual**: Tidak ada notifikasi sukses yang muncul dan sistem malah me-redirect user kembali ke form pendaftaran awal.
> * **Evidence Awal**:
>   * Button Daftar Sekarang: [https://files.catbox.moe/b00i5x.png](https://files.catbox.moe/b00i5x.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Masuk dengan Akun Lain Tidak Berfungsi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman Konfirmasi Identitas dan menekan button Masuk dengan akun lain, tidak ada respons apa pun dari sistem.
> * **Expected**: Sistem mengarahkan user kembali ke halaman/form login awal untuk memasukkan email atau akun lain.
> * **Actual**: Button Masuk dengan akun lain tidak berfungsi saat ditekan dan user tetap tertahan di halaman Konfirmasi Identitas.
> * **Evidence Awal**:
>   * Button Masuk Akun Lain: [https://files.catbox.moe/6nlq0m.png](https://files.catbox.moe/6nlq0m.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Klik "Daftar gratis sekarang" Malah Memunculkan Toast Konfirmasi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di form login dan menekan link button Daftar gratis sekarang, sistem tidak mengarahkan ke form registrasi akun baru.
> * **Expected**: Sistem mengarahkan user ke halaman pendaftaran akun baru (Register).
> * **Actual**: Muncul toast info "Harap konfirmasi tindakan ini dengan memverifikasi bahwa ini benar-benar Kamu" dan user tetap tertahan di halaman login.
> * **Evidence Awal**:
>   * Toast Daftar Gratis Sekarang: [https://files.catbox.moe/av606w.png](https://files.catbox.moe/av606w.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Klik Lupa Kata Sandi Malah Diarahkan ke Halaman Sesi

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di form login dan menekan link button Lupa kata sandi?, sistem tidak mengarahkan ke form pemulihan/reset kata sandi akun.
> * **Expected**: Sistem mengarahkan user ke halaman reset kata sandi dengan field input email untuk verifikasi pemulihan akun.
> * **Actual**: Sistem malah mengarahkan user ke halaman sesi auth dengan keterangan "Anda belum masuk ke akun manapun" dan button "Masuk Sekarang".
> * **Evidence Awal**:
>   * Form Login: [https://files.catbox.moe/214j9d.png](https://files.catbox.moe/214j9d.png)
>   * Halaman Sesi: [https://files.catbox.moe/c2vb8i.png](https://files.catbox.moe/c2vb8i.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Nama Nasabah Pada Header Navbar Belum Muncul

> * **Menu**: Beranda → Header
> * **Status**: Open
> * **Deskripsi**: Saat user nasabah telah berhasil login dan mengakses halaman Beranda, komponen profil akun pada pojok kanan atas header navbar belum memuat identitas nasabah.
> * **Expected**: Header navbar menampilkan inisial avatar serta nama lengkap nasabah yang sedang login.
> * **Actual**: Header navbar belum memuat nama nasabah dan hanya menampilkan karakter strip (-) pada badge lingkaran hijau serta teks label (- v).
> * **Evidence Awal**:
>   * Badge Profil Navbar: [https://files.catbox.moe/8bm9tu.png](https://files.catbox.moe/8bm9tu.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Tab Profil, Akun, Favorit, dan Notifikasi Gagal Memuat Data

> * **Menu**: User Profile (Tab Profil, Akun, Favorit, Notifikasi)
> * **Status**: Open
> * **Deskripsi**: Saat user nasabah mengakses halaman profil akun, hanya tab Daftar Pesanan yang dapat dibuka, sedangkan tab menu lainnya gagal memuat konten.
> * **Expected**: Seluruh tab menu (Profil, Akun, Favorit, Notifikasi) dapat diakses dan menampilkan konten data nasabah dengan normal.
> * **Actual**: Tab Profil, Akun, Favorit, dan Notifikasi menampilkan halaman error "Oops! Terjadi kesalahan saat memuat data".
> * **Evidence Awal**:
>   * Halaman Error Profil: [https://files.catbox.moe/yxag2f.png](https://files.catbox.moe/yxag2f.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Setelah Logout Navbar Profil Tidak Berubah Menjadi Button Masuk

> * **Menu**: Beranda → Header
> * **Status**: Open
> * **Deskripsi**: Saat user nasabah telah melakukan logout dan kembali ke Beranda, komponen header navbar di pojok kanan atas tidak kembali ke status belum login.
> * **Expected**: Header navbar menampilkan button Masuk setelah proses logout selesai.
> * **Actual**: Header navbar tetap menampilkan badge profil ([-] - v) dan tidak berubah menjadi button Masuk.
> * **Evidence Awal**:
>   * Navbar Setelah Logout: [https://files.catbox.moe/09p09q.png](https://files.catbox.moe/09p09q.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Validasi Kata Sandi Breached Muncul di Langkah Terakhir dan Melempar User ke Awal

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Catatan / Clarification
> * **Deskripsi**: Saat mendaftar akun nasabah, indikator kata sandi di Langkah 1 valid dan berwarna hijau ("Kuat"). Namun saat menekan button Daftar Sekarang di Langkah 3, sistem menolak pendaftaran dengan pesan pelanggaran data dan melempar user kembali ke Langkah 1.
> * **Expected**: Validasi kata sandi (termasuk deteksi data breach) dievaluasi langsung di Langkah 1 sebelum user melanjutkan ke langkah berikutnya, atau indikator kekuatan kata sandi menampilkan peringatan sejak awal.
> * **Actual**: User berhasil menyelesaikan form hingga Langkah 3, namun gagal submit dengan toast error "Kata sandi ditemukan dalam pelanggaran data dan tidak boleh digunakan lagi" dan otomatis diarahkan kembali ke Langkah 1.
> * **Catatan Tim**: Menunggu klarifikasi tim terkait security policy HaveIBeenPwned (HIBP) / breached password di auth backend dan kesesuaian alur UX di Langkah 1 vs Langkah 3.
> * **Evidence Awal**:
>   * Submit Langkah 3: [https://files.catbox.moe/0eqyh8.png](https://files.catbox.moe/0eqyh8.png)
>   * Error Langkah 1: [https://files.catbox.moe/37o3lw.png](https://files.catbox.moe/37o3lw.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Daftar dengan Google Stuck Memproses dan Tidak Berfungsi

> * **Menu**: Authentication → Register Nasabah
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman pendaftaran akun nasabah langkah 1 dan menekan button Daftar dengan Google, sistem tidak merespons pengalihan ke akun Google.
> * **Expected**: Sistem mengarahkan user ke halaman login/pemilihan akun Google (Google OAuth Sign-In).
> * **Actual**: Button hanya berubah menampilkan status spinner "Memproses" secara terus-menerus (stuck loading) dan tidak terjadi redirect.
> * **Evidence Awal**:
>   * Button Google: [https://files.catbox.moe/96bd6e.png](https://files.catbox.moe/96bd6e.png)
>   * Status Memproses: [https://files.catbox.moe/uzp8ik.png](https://files.catbox.moe/uzp8ik.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Tidak Ada Button Navigasi Kembali ke Login Pada Halaman Verifikasi OTP

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman verifikasi OTP ("Masukkan Kode Verifikasi"), tidak tersedia button atau navigasi untuk membatalkan proses dan kembali ke form login awal.
> * **Expected**: Halaman verifikasi OTP menyediakan button atau link navigasi Kembali ke Login (atau tombol kembali) agar user dapat mengganti akun jika terjadi salah input email.
> * **Actual**: Halaman hanya menyediakan button Lanjutkan dan Kirim ulang kode tanpa ada opsi navigasi kembali ke login.
> * **Evidence Awal**:
>   * Halaman Verifikasi OTP: [https://files.catbox.moe/ibxwqj.png](https://files.catbox.moe/ibxwqj.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Label Banner Login External Masih Tertulis Sistem Portal Internal

> * **Menu**: Authentication → Login
> * **Status**: Catatan / Clarification
> * **Deskripsi**: Saat user mengakses halaman login external (nasabah), teks sub-judul pada banner sebelah kiri masih menampilkan label "Sistem Portal Internal".
> * **Expected**: Banner sebelah kiri menampilkan label yang sesuai dengan portal publik/external nasabah (misalnya "Sistem Portal Nasabah" atau "Portal Lelang BSN").
> * **Actual**: Banner sebelah kiri masih tertulis "Sistem Portal Internal", yang tidak sesuai dengan konteks portal external nasabah.
> * **Catatan Tim**: Menunggu klarifikasi tim apakah teks banner kiri pada portal nasabah/external memang seharusnya 'Sistem Portal Nasabah / External' atau teks 'Sistem Portal Internal' adalah copywriting sementara/salah template.
> * **Evidence Awal**:
>   * Form Login: [https://files.catbox.moe/gmq0kc.png](https://files.catbox.moe/gmq0kc.png)
>   * Konfirmasi Identitas: [https://files.catbox.moe/5hfldp.png](https://files.catbox.moe/5hfldp.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Field Email dan Kata Sandi Tidak Memiliki Indikator Bintang Mandatory

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user berada di form login, label pada field Email dan Kata Sandi tidak dilengkapi dengan simbol asterisk/tanda bintang (*) penanda field wajib diisi.
> * **Expected**: Label field menampilkan simbol asterisk merah (Email * & Kata Sandi *) sebagai penanda bahwa kedua field tersebut mandatory/wajib diisi.
> * **Actual**: Label hanya menampilkan teks Email dan Kata Sandi polos tanpa indikator bintang mandatory.
> * **Evidence Awal**:
>   * Form Login: [https://files.catbox.moe/pkauex.png](https://files.catbox.moe/pkauex.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Field Kata Sandi Baru dan Konfirmasi Tidak Memiliki Indikator Bintang Mandatory

> * **Menu**: Authentication → Lupa Kata Sandi
> * **Status**: Open
> * **Deskripsi**: Saat user berada di halaman pemulihan akun ("Masukkan Kata Sandi Baru"), label pada field Kata Sandi dan Konfirmasi Kata Sandi tidak dilengkapi simbol asterisk/tanda bintang (*) penanda field wajib diisi.
> * **Expected**: Label field menampilkan simbol asterisk merah (Kata Sandi * & Konfirmasi Kata Sandi *) sebagai penanda bahwa kedua field tersebut mandatory/wajib diisi.
> * **Actual**: Label hanya menampilkan teks Kata Sandi dan Konfirmasi Kata Sandi polos tanpa indikator bintang mandatory.
> * **Evidence Awal**:
>   * Form Reset Password: [https://files.catbox.moe/rwoifa.png](https://files.catbox.moe/rwoifa.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Button Masuk Sekarang Terpental ke Halaman Sesi dan Gagal Membuka Login

> * **Menu**: Authentication → Lupa Kata Sandi
> * **Status**: Open
> * **Deskripsi**: Setelah user selesai mereset kata sandi dan diarahkan ke halaman sesi auth, penekanan button Masuk Sekarang mengalami mental (redirect loop) kembali ke /auth sehingga user tidak bisa mengakses form login.
> * **Expected**: Sistem mengarahkan user ke form login dan user dapat memasukkan kata sandi baru untuk masuk ke akun.
> * **Actual**: Saat menekan button Masuk Sekarang, sistem sempat membuka form login namun langsung terpental kembali ke halaman sesi /auth ("Anda belum masuk ke akun manapun").
> * **Evidence Awal**:
>   * Halaman Sesi Auth: [https://files.catbox.moe/acnx02.png](https://files.catbox.moe/acnx02.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Identitas Akun User Tidak Muncul Pada Halaman Konfirmasi Identitas

> * **Menu**: Authentication → Login
> * **Status**: Open
> * **Deskripsi**: Saat user melanjutkan alur login ke tahap Konfirmasi Identitas, teks penjelas akun tidak menampilkan alamat email atau nama akun user.
> * **Expected**: Halaman Konfirmasi Identitas menampilkan identitas user yang sedang login (misalnya: "Anda masuk sebagai user@email.com").
> * **Actual**: Keterangan "Anda masuk sebagai" kosong tanpa menampilkan email atau data user yang sedang diverifikasi.
> * **Evidence Awal**:
>   * Halaman Konfirmasi Identitas: [https://files.catbox.moe/34yhsf.png](https://files.catbox.moe/34yhsf.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -

<br>

### 🐞 [BUG] | Email Tautan Pemulihan Kata Sandi Tidak Terkirim ke Mailpit

> * **Menu**: Authentication → Lupa Kata Sandi
> * **Status**: Open
> * **Deskripsi**: Saat user mengajukan pemulihan kata sandi akun internal dan sistem memunculkan toast bahwa email telah dikirim, pesan berisi tautan pemulihan tidak pernah masuk/diterima di Mailpit.
> * **Expected**: Sistem berhasil mengirimkan email berisi tautan/kode pemulihan kata sandi ke server Mailpit.
> * **Actual**: Toast info menyatakan email telah dikirim, namun inbox Mailpit tidak menerima email pemulihan apa pun.
> * **Evidence Awal**:
>   * Toast Pemulihan Akun: [https://files.catbox.moe/6rd9fo.png](https://files.catbox.moe/6rd9fo.png)
> * **Bukti Retest (Done)**:
>   * -
> * **Catatan Retest**:
>   * -
