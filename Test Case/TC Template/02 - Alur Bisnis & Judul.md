---
tags:
  - QA
  - TestCase
  - BusinessFlow
date: 2026-08-31
---
# 🛤️ 02 - Alur Bisnis & Judul TC

## 1. DESKRIPSI (DESCRIPTION)
Hanya nilai berikut yang diizinkan:
- Positive Case
- Negative Case

## 2. PRIORITAS (PRIORITY)
Nilai yang diizinkan (berdasarkan implementasi aktual):

- **Critical**: Login dengan data valid, Tambah data (Add/Save), Ubah data (Edit/Update), Hapus data (Delete).
- **High**: Membuka halaman utama, Export data, Approval/Reject, Pencarian data dengan keyword valid, Autentikasi error (contoh: password salah, email tidak terdaftar).
- **Medium / Normal**: Pencarian data dengan keyword tidak valid/kosong, Filter data, Detail/View informasi.
- **Low**: Mode Fullscreen, Keluar dari mode Fullscreen, Fitur informasional ringan.

## 3. ALUR BISNIS (BUSINESS FLOW)
Selalu buat Test Case (TC) dengan urutan berikut jika tersedia:
1. Membuka halaman
2. Menampilkan data (Menampilkan daftar data)
3. Search (Pencarian)
4. Filter
5. Reset Filter
6. Add (Tambah)
7. Edit (Ubah)
8. Delete (Hapus)
9. Detail
10. Approval / Reject
11. Export
12. Fitur bisnis lainnya

⚠️ **Jangan pernah mengikuti tata letak (posisi) UI. Selalu ikuti alur bisnis.**

## 4. JUDUL TEST CASE (TEST CASE TITLE)

**Aturan Umum:**
Prioritaskan penamaan judul Test Case dengan awalan kata kerja aktif **"Me-"** (misal: Melakukan, Membuka, Menambahkan, Mencari) jika memungkinkan. Jika kurang pas, diperbolehkan menggunakan kata lain yang deskriptif.

**Aturan Penamaan Spesifik:**
- **Opening & Data**: Membuka halaman <Menu>, Menampilkan daftar data <Object>
- **Search**: Mencari data <Object> dengan keyword valid / tidak valid
- **Filter**: Melakukan filter data <Object> / dengan data yang tidak ada
- **Reset Filter**: Mereset filter <Object>
- **CRUD**: Menambahkan data <Object>, Menambahkan data <Object> tanpa mengisi field mandatory, Mengubah data <Object>, Mengubah data <Object> tanpa mengisi field mandatory, Menghapus data <Object>
- **Detail**: Melihat detail <Object>
- **Auth**: Melakukan login menggunakan data yang valid / password yang tidak valid / logout dari aplikasi

**Khusus Export:**
- **Title**: Mengekspor data <Object>
- **Steps**: 
  1. Klik button Export.
  2. Klik icon download pada panel Download Export.
- **Expected Results**:
  1. Berhasil menampilkan panel Download Export.
  2. Berhasil mendownload file export.
