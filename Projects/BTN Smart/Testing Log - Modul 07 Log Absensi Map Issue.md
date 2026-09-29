# 📝 Testing Log - Modul 07 Log Absensi (Issue Map Detail Log Absent)

Catatan pengujian mobile untuk **Modul 07. Log Absensi** pada aplikasi **BTN Smart Mobile**.

---

## 📌 Informasi Pengujian
* **Aplikasi**: BTN Smart Mobile (Android)
* **Modul**: Modul 07. Log Absensi
* **Tanggal Penemuan**: 28 September 2026
* **Tester**: Dani & Team QA

---

## ⚠️ Status Penundaan Test Case ke Dokumen Hasil Uji
Test Case berikut **DITUNDA / BELUM DIMASUKKAN** ke `Dokumen_Hasil_Uji_Mobile.docx`:
1. **TC 7.3 - Melihat detail log absensi (Clock In)**
2. **TC 7.4 - Melihat detail log absensi (Clock Out)**

---

## 🔍 Detail Masalah (Bug / Issue)
* **Deskripsi Masalah**: Komponen peta (Map) pada halaman detail log absensi tidak muncul (blank / gagal render) saat tester membuka detail riwayat absensi.
* **Dampak**: Bukti screenshot pengujian untuk TC 7.3 dan TC 7.4 belum valid / belum memenuhi ekspektasi pengujian (peta lokasi absen harus tampil dengan marker posisi koordinat).
* **Tindakan**:
  - TC 7.1 (*Membuka halaman Log Absensi*) dan TC 7.2 (*Melakukan filter data log absensi*) **sudah aman, lengkap, dan dimasukkan ke dokumen hasil uji**.
  - TC 7.3 dan TC 7.4 di-hold sampai tim developer memperbaiki issue pemuatan map pada detail log absensi.
