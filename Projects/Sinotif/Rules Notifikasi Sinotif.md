# Panduan Trigger Notifikasi (Aplikasi Ortu & Siswa)

Sistem notifikasi dirancang **hanya untuk penambahan data baru**, BUKAN saat melakukan update/edit data lama. 

Berikut ringkasannya untuk pengetesan (QA):

## 1. Laporan Hasil Belajar (LHB), Nilai Ulangan, & Hasil SmolTok
- **Notif MUNCUL:** Saat pertama kali di-input (Create New).
- **Notif TIDAK MUNCUL:** Saat melakukan Edit / Update data yang sudah ada.

## 2. Jadwal Ulangan (Baru)
- **Notif MUNCUL:** Saat jadwal ulangan baru dibuat (single maupun *bulk*).
- **Catatan:** Akan langsung muncul **2 notif sekaligus** di tab yang sama.

## 3. Reminder "Jadwal Hari Ini"
- **Notif MUNCUL:** Otomatis terkirim oleh scheduler jam **02:00 pagi WIB** untuk siswa yang punya slot aktif dengan tanggal efektif hari itu.
- **Catatan:** Jika ada jadwal yang dipindah hari atau dinonaktifkan *setelah* jam 02:00 pagi, notif yang sudah terlanjur terkirim subuh tadi tidak akan ditarik/berubah.

---
**Tips QA:** 
Untuk memastikan fitur notifikasi berjalan dengan benar, selalu gunakan skenario **Create / Tambah Baru**. Jangan pakai fitur Edit/Update (kecuali sedang menguji *negative case* untuk memastikan tidak ada notifikasi bocor yang terkirim).


## Status Pengetesan (QA)
- [x] Input Hasil SmolTok (Notif masuk)
- [x] Input Laporan Hasil Belajar (LHB)
- [x] Input Nilai Ulangan
- [x] Create Jadwal Ulangan
- [ ] Reminder Jadwal Hari Ini


## ⚠️ Bug Report / Isu Temuan
- **Status Read/Unread Notifikasi Bocor (Terkoneksi) antara Ortu & Siswa**
  - *Detail:* Saat ini status dibaca/belum dibaca (read/unread) saling nyambung. Misalnya, jika Ortu membuka/membaca notifikasi, maka di akun Siswa notifikasi tersebut otomatis berubah menjadi 'sudah dibaca', padahal seharusnya berstatus independen (harus dibaca oleh masing-masing user).
