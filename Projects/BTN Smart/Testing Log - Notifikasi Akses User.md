# Testing Log - Notifikasi Lifecycle & Akses User

Catatan pengetesan untuk fitur notifikasi jika ada perubahan data akun atau penghapusan user oleh Admin (Ref: Tiket US-469).

**Persiapan Testing:**
Siapkan 2 akun untuk testing:
1. **Akun Monitoring** (sebagai pihak yang mengubah/menghapus akses)
2. **Akun Sales** (sebagai pihak yang datanya diedit/dihapus)

---

## 📋 Skenario Pengetesan (Test Cases)

### 1. Skenario POSITIF (Harus Ada Notifikasi)

- [x] **TC01 - Perubahan Hak Akses oleh Monitoring** [PASS] ✅
  * **Langkah:** Login pakai Akun Monitoring (`monitoring dani`) → Buka data Akun Sales (`salesdani6`) → Ubah `Role` dan `Kantor/Cabang` → Klik Update.
  * **Ekspektasi:** 
    1. Akun Sales mendapat notifikasi In-App (Lonceng).
    2. Isi notif mencantumkan Nama Monitoring (`monitoring dani`).
    3. Isi notif mencantumkan detail perubahan Role & Unit Kerja.
  * **Hasil:** Sesuai ekspektasi (Muncul badge Peringatan, judul "Akses BTNSmart Anda Berubah", detail role & unit sebelum → sesudah tercatat jelas).
  * **Bukti / Evidence:**
    - Form Awal User: https://files.catbox.moe/lr0s1m.png
    - Form Edit (Ubah Role & Kantor): https://files.catbox.moe/jgjdi1.png
    - Notifikasi Masuk di Sales: https://files.catbox.moe/emprkc.png

- [x] **TC02 - Penghapusan Akun oleh Monitoring** [PASS] ✅
  * **Langkah:** Login pakai Akun Monitoring → Buka data Akun Sales (`salesdani11`) → Lakukan hapus akun (Delete/Deactivate).
  * **Ekspektasi:** 
    1. Akun Sales mendapat notifikasi via **Email Saja**.
    2. Subjek email: "Akses BTNSmart Anda Dinonaktifkan".
    3. Isi email memberitahu bahwa akun telah dinonaktifkan/dihapus beserta info waktu & kontak support.
  * **Hasil:** Sesuai ekspektasi (Email terkirim ke `salesdani11@gmail.com` via Mailpit, template dan pesan sesuai spesifikasi).
  * **Bukti / Evidence:**
    - Email Akun Dinonaktifkan (Mailpit): https://files.catbox.moe/mmo660.png

---

### 2. Skenario NEGATIF (TIDAK BOLEH Ada Notifikasi)

- [x] **TC03 - Perubahan Non-Mandatory oleh Monitoring** [PASS] ✅
  * **Langkah:** Login pakai Akun Monitoring → Buka data Akun Sales → Hanya ubah data non-mandatory (misal: `No Telepon`, `Alamat`, `NIP`) tanpa mengubah Role & Unit → Klik Update.
  * **Ekspektasi:** Akun Sales **TIDAK** mendapat notifikasi apapun (Email/In-App/Push).
  * **Hasil:** Sesuai ekspektasi (Aman, tidak ada notifikasi yang masuk).

- [x] **TC04 - Sales Mengubah Datanya Sendiri (Self-Change)** [PASS] ✅
  * **Langkah:** Login pakai Akun Sales → Masuk ke menu Profil sendiri → Ubah data mandatory profil sendiri → Klik Update.
  * **Ekspektasi:** Akun Sales **TIDAK** mendapat notifikasi apapun (karena aksi dilakukan oleh user sendiri).
  * **Hasil:** Sesuai ekspektasi (Aman, tidak ada notifikasi yang masuk).

- [x] **TC05 - Monitoring Save Tanpa Perubahan (No-Op)** [PASS] ✅
  * **Langkah:** Login pakai Akun Monitoring → Buka form edit Akun Sales → **Jangan ubah data apapun** → Langsung klik Update.
  * **Ekspektasi:** Akun Sales **TIDAK** mendapat notifikasi apapun (mencegah spam notif kosong).
  * **Hasil:** Sesuai ekspektasi (Aman, tidak ada notifikasi yang terkirim).

---

## 🎯 Kesimpulan & Status Platform
* **Web:** **VERIFIED / DONE** ✅ (Semua skenario TC01 s/d TC05 sudah teruji dan valid di Web & Email)
* **Mobile:** **ADA BUG (ISSUES FOUND)** ⚠️
  * **Push Notification (Banner HP):** PASS ✅ (Muncul normal saat ada perubahan Role & Unit. Bukti: https://files.catbox.moe/6uatck.jpg)
  * **In-App (Lonceng Notifikasi Mobile):** FAILED ❌ (Crash parsing data/type cast)

---

## ⚠️ Bug Report / Isu Temuan

> **[BUG] [Mobile] Notifikasi In-App: Halaman Notifikasi Crash / Error Type Cast saat Dibuka**
> 
> * **Platform**: Mobile (Android/iOS - Build Firebase)
> * **Menu / Flow**: Menu Profil → Notifikasi (Ikon Lonceng)
> * **Deskripsi**:
>   1. Push notification di banner atas HP berhasil masuk saat Role & Unit diubah.
>   2. Namun ketika user membuka menu/halaman **Notifikasi (In-App)** di dalam aplikasi mobile, daftar notifikasi tidak tampil dan malah muncul teks error:
>      `type 'String' is not a subtype of type 'int' in type cast`
> * **Expected**: Halaman Notifikasi menampilkan list notifikasi in-app secara normal seperti di versi Web.
> * **Actual**: Terjadi crash/error parsing Flutter (`type 'String' is not a subtype of type 'int' in type cast`) sehingga notifikasi tidak muncul.
> * **Evidence**:
>   * Crash di Menu Notifikasi Mobile: https://files.catbox.moe/3gt7tv.jpg
>   * Push Notif Berhasil Masuk di HP: https://files.catbox.moe/6uatck.jpg



