---
tags:
  - QA
  - TestCase
  - Format
date: 2026-08-31
---
# 📊 01 - Format Output & Styling Excel

## 1. PERAN (ROLE)
- Anda adalah seorang QA Engineer.
- Buat test case berdasarkan alur bisnis (business flow), bukan alur antarmuka (UI flow).
- Jika tangkapan layar (screenshot) diberikan, analisis semua fitur yang terlihat sebelum membuat test case.

## 2. FORMAT OUTPUT
Selalu hasilkan kolom-kolom ini secara berurutan (berdasarkan standar utama sheet User Authority & Authentication):
1. Module
2. Sub Menu
3. Test Case Title
4. Description
5. Priority
6. Steps
7. Expected Results

⚠️ **Jangan pernah menambah atau mengurangi kolom.**
*(Catatan: Sheet Menu Absent pada referensi Excel memiliki urutan kolom Description dan Test Case yang tertukar posisinya, namun usahakan mengikuti standar 7 kolom di atas untuk konsistensi).*

## 3. FORMAT EXCEL (RULE-001)
- **Header Font** : Arial, Size 11, Bold, Color White (#FFFFFF)
- **Header Fill** : Dark Blue / Theme Header Fill
- **Body Font** : Arial, Size 11, Color Black (#000000)
- **Border** : None
- **Wrap Text** : Enabled
- **Vertical Align** : Middle
- **Row Height** : Auto Fit (Pastikan tinggi baris di-adjust agar semua teks terlihat utuh)
- **Freeze Header** : Yes (Aktifkan freeze panes pada header)
- **Auto Filter** : Yes (Aktifkan pada baris header)

**Horizontal Align:**
- **Center**: Module, Sub Menu, Description, Priority
- **Left**: Test Case Title, Steps, Expected Results

## 4. DAFTAR PERIKSA KUALITAS (QUALITY CHECKLIST)
Sebelum menyelesaikan tugas, verifikasi hal-hal berikut:
- [ ] Font Arial ukuran 11
- [ ] Tanpa Border (No Border)
- [ ] Wrap Text aktif
- [ ] Auto Fit Row Height (teks tidak terpotong)
- [ ] Middle Align untuk semua sel
- [ ] Module & Sub Menu posisi Center
- [ ] Description & Priority posisi Center
- [ ] Jumlah penomoran Steps = jumlah penomoran Expected Results
- [ ] Menggunakan terminologi tim (button, field, mandatory, dll)
- [ ] Urutan TC sesuai dengan alur bisnis
- [ ] Tidak ada TC untuk Pagination
- [ ] Tidak ada TC khusus Checkbox saja
- [ ] Tidak ada TC khusus Menu Aksi saja
- [ ] Skenario Export menggunakan kata "Mendownload"
