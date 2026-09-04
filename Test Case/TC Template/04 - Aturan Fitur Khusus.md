---
tags:
  - QA
  - TestCase
  - Rules
date: 2026-08-31
---
# 🚫 04 - Aturan Khusus Fitur

Panduan untuk menangani elemen atau fitur spesifik di dalam aplikasi.

## 1. Aturan Jumlah TC
- **Search**: Wajib buat tepat 1 Positive & 1 Negative Case.
- **Filter**: Wajib buat 1 Positive, 1 Negative (not found), dan 1 Reset Filter.
- **Toggle / Tab**: Cukup 1 TC saja (misal: "Mengubah status Toggle").
- **Map / Peta**: Hanya buat TC bisnis (misal: "Menampilkan peta"). Dilarang membuat TC untuk interaksi mouse seperti Zoom/Scroll/Drag.

## 2. DILARANG Membuat TC Untuk:
Jangan pernah membuat Test Case terpisah untuk hal-hal berikut kecuali diminta spesifik:
- Pagination
- Checkbox tunggal (Harus digabung ke alur *Delete / Bulk Action*)
- Menu Aksi / Titik Tiga (Harus digabung ke alur *Edit / Delete / Detail*)
- Clear Search
- Sorting
- Hover & Tooltip
- Loading state / Skeleton view
- UI spacing & Responsive layout
