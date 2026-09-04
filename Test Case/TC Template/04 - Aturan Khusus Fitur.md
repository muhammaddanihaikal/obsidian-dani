---
tags:
  - QA
  - TestCase
  - Rules
date: 2026-08-31
---
# 🚫 04 - Aturan Khusus Fitur & AI Tree

## 1. ATURAN KOMPONEN SPESIFIK
- **PENCARIAN (SEARCH)**: Buat tepat **1 Positive Case** dan **1 Negative Case**. Jangan buat lebih kecuali diminta eksplisit.
- **FILTER**: Buat **Positive Case**, **Negative Case (data tidak ditemukan)**. Jika ada fitur Reset, buat **1 TC untuk Reset Filter**. Jangan pernah membuat TC untuk masing-masing field filter (gabungkan menjadi satu alur filter).
- **TOGGLE**: Buat HANYA SATU TC untuk toggle (misal: Mengubah status Requires Approval).
- **TAB**: Buat SATU TC untuk navigasi tab (misal: Menampilkan data berdasarkan status absent).
- **PETA (MAP)**: Buat TC hanya jika ada nilai bisnisnya (Menampilkan peta, Melihat info lokasi/spot, Fullscreen). **DILARANG** membuat TC untuk Zoom, Scroll, Drag.

## 2. JANGAN BUAT TEST CASE UNTUK
- Pagination (Paginasi)
- Checkbox tunggal (tanpa aksi lanjutan) -> **Harus digabung ke alur Delete/Approval.**
- Menu Aksi saja (klik titik tiga tanpa aksi lanjutan) -> **Harus digabung ke alur Edit/Delete/Detail.**
- Clear Search
- Sorting (kecuali diminta)
- Hover
- Tooltip
- Loading state
- Skeleton view
- UI spacing (Jarak antar elemen UI)
- Responsive layout (Tampilan responsif)

## 3. POHON KEPUTUSAN AI (AI DECISION TREE)
Saat AI menerima tangkapan layar (screenshot), lakukan urutan ini:
1. Deteksi semua menu yang terlihat.
2. Deteksi semua fitur bisnis.
3. Abaikan fitur yang hanya bersifat visual/UI.
4. Susun urutan berdasarkan alur bisnis (Business Flow).
5. Buat Positive Case.
6. Buat Negative Case jika relevan dan bermakna.
7. Ikuti semua aturan dalam spesifikasi ini dengan ketat.

*Akhir dari Spesifikasi.*
