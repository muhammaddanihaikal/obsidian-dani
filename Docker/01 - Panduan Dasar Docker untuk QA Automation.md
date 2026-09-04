# 🐳 01 - Panduan Dasar Docker untuk QA Automation

Catatan ini merangkum pengetahuan dasar, konsep inti, dan perintah sehari-hari Docker untuk menjalankan lingkungan pengujian lokal (*Local Test Environment*).

---

## 1. Mengapa Butuh Docker dalam Automation Testing?
Dalam dunia QA, menguji aplikasi di **server demo publik** (seperti `opensource-demo.orangehrmlive.com`) memiliki banyak masalah:
- ❌ **Flaky / Tidak Stabil:** Rebutan data dengan ribuan tester lain di seluruh dunia.
- ❌ **Lambat:** Ketergantungan pada koneksi internet dan beban server pusat.
- ❌ **Data Berubah Sewaktu-waktu:** Akun atau karyawan bisa diubah/dihapus orang lain di tengah proses pengujian.

### ✅ Solusi Docker:
Docker memungkinkan kita menjalankan replika aplikasi (seperti OrangeHRM + MariaDB) langsung di dalam laptop sendiri secara terisolasi.
- ⚡ **Super Cepat:** Respons localhost hampir 0ms (pengujian 10 test case selesai dalam ~20 detik).
- 🔒 **Data Mandiri:** Data tersimpan permanen dan tidak akan diacak-acak oleh pihak luar.
- 📶 **Offline-Ready:** Bisa menjalankan automation tanpa koneksi internet.

---

## 2. Tiga Konsep Inti Docker (Analogi Dunia Nyata)

| Istilah | Analogi | Penjelasan Teknis |
|---|---|---|
| **IMAGE** | **Cetak Biru / Resep Kue / File `.exe`** | File master/paket mentah yang didownload dari Docker Hub. Sifatnya beku (*read-only*). Contoh: `orangehrm/orangehrm:latest`, `mariadb:10.11`. |
| **CONTAINER** | **Rumah yang Sudah Dibangun / Kue yang Matang** | Wujud nyata saat Image dijalankan. Ini adalah **MESIN** aplikasi yang sedang aktif menggunakan RAM dan CPU. |
| **VOLUME** | **Flashdisk / Brankas Eksternal** | Media penyimpanan fisik di harddisk laptop. Menyimpan data database secara **PERMANEN** agar tidak hilang saat container dimatikan. |

> 💡 **Prinsip Utama:** *"Container itu Mesinnya (bisa dibongkar-pasang), Volume itu Brankasnya (datanya abadi)."*

---

## 3. Siklus Hidup (Lifecycle): Kapan Nyala dan Mati?

### A. Mesin Docker Desktop (Docker Engine):
- **Kapan Nyala?** Otomatis menyala di latar belakang setiap kali laptop dihidupkan (ikon ikan paus 🐳 di taskbar pojok kanan bawah).
- **Kapan Mati?** Mati saat laptop dimatikan, atau jika di-*Quit* manual lewat ikon taskbar.

### B. Container Aplikasi:
- **Default:** Dijalankan secara **manual** menggunakan perintah `docker compose up -d`.
- **Kenapa sebaiknya manual?** **Hemat RAM!** Saat kamu sedang santai, nonton YouTube, atau bermain game, RAM laptopmu tidak akan terbebani oleh server database. Nyalakan container hanya saat kamu ingin ngoding/testing.

### C. Volume (Data):
- **Tidak pernah mati.** Volume adalah data pasif di harddisk. Saat container mati, kabelnya dicabut; saat container nyala lagi, kabelnya dicolokkan kembali dan semua data tetap utuh.

---

## 4. Cheat Sheet Perintah Wajib Sehari-hari

Jalankan perintah ini di terminal root project kamu (tempat file `docker-compose.yml` berada):

### 1. Menyalakan Server (Start)
```bash
docker compose up -d
```
- Membaca file `docker-compose.yml`, membuat network & volume, lalu menyalakan container di latar belakang (*detached mode*).

### 2. Mematikan Server (Stop & Clean)
```bash
docker compose down
```
- Mematikan dan merapikan container agar RAM kembali lega.
- **Data database kamu TETAP AMAN di volume.**

### 3. Mengecek Status Container
```bash
docker ps
```
- Menampilkan daftar container yang sedang aktif berjalan beserta port-nya (misal: `0.0.0.0:8080->80`).

### ⚠️ PERINGATAN (Perintah Berbahaya):
```bash
docker compose down -v
```
- Embel-embel `-v` (*volume*) akan **MENGHAPUS BRANKAS DATABASE**. Hanya gunakan ini jika kamu memang ingin me-reset aplikasi dari nol.

---

## 5. Mengontrol Lewat GUI (Docker Desktop)
Jika sedang malas membuka terminal:
1. Buka aplikasi **Docker Desktop**.
2. Masuk ke tab **Containers** ➜ Klik tombol **Stop (⏹️)** untuk mematikan, atau tombol **Start (▶️)** untuk menyalakan kembali.
3. Masuk ke tab **Volumes** ➜ Melihat daftar brankas data (`mariadb_data` & `orangehrm_data`).
