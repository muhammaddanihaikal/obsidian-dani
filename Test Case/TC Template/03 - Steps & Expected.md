---
tags:
  - QA
  - TestCase
  - Steps
date: 2026-08-31
---
# 📝 03 - Penulisan Steps & Expected

## 1. TERMINOLOGI (TERMINOLOGY)
Gunakan istilah berikut secara konsisten (jangan pernah diganti):
- utton
- ield
- mandatory
- popup
- Berhasil
- keyword valid
- keyword tidak valid
- Mendownload

## 2. LANGKAH-LANGKAH (STEPS)
- Gunakan penomoran (angka) dan kalimat pendek.
- Gunakan istilah baku di atas. Jangan menjelaskan perilaku sistem secara teknis.
- **Aturan Aksi Tunggal (Atomic Step)**: Setiap langkah HARUS merepresentasikan tepat 1 aksi pengguna. DILARANG menggabungkan 2 atau lebih aksi dalam 1 nomor langkah (misal: "Isi field Nama dan pilih Category" ❌). Setiap aksi wajib dipisah menjadi langkah dan expected result tersendiri.
- **Penyederhanaan Form**: Jika form hanya memiliki 1-2 field mandatory, sebutkan secara spesifik. Jika **lebih dari 2 field**, gunakan kalimat simpel: "Mengisi semua field mandatory." atau "Mengosongkan field mandatory.".
- **Batasan Negative Case Form**: Cukup buat **1 Negative Case** secara umum untuk validasi form, yaitu dengan judul "... tanpa mengisi field mandatory". Jangan membuat banyak negative cases untuk masing-masing field.
- **Asumsi Pengguna Sudah Login**: DILARANG menambahkan langkah "Buka aplikasi..." selain modul Authentication. Untuk modul lain, asumsi user sudah login, diawali langsung dengan navigasi menu (1. Klik menu <Nama>).
- **Aturan Navigasi & Konteks Halaman**: Langkah masuk halaman (Klik menu <Nama>, Klik sub menu <Nama>) HARUS ditulis pada **TC 1 (Membuka Halaman)**. Untuk TC ke-2 dan seterusnya di halaman yang sama, **DILARANG mengulang langkah navigasi tersebut**. Langkah pertama wajib langsung berupa aksi utama.

## 3. HASIL YANG DIHARAPKAN (EXPECTED RESULTS)
- Selalu mulai dengan kata **"Berhasil"** kecuali untuk kasus validasi/data tidak ditemukan.
- Jumlah baris Expected Results HARUS sama dengan jumlah baris Steps. Expected Result harus relevan dengan masing-masing step.
- **Penyederhanaan Kalimat**: Tulis secara singkat dan jelas. DILARANG merincikan/mendaftar seluruh rincian komponen data atau grafik di dalam kalimat agar penulisan tetap ringkas.
- **Dilarang Menggunakan Istilah UI Teknis**: DILARANG menggunakan kata "bottom sheet", "modal sheet", dsb. Gunakan istilah umum (misal: "detail", "tampilan", "halaman", atau "menu opsi").

## 4. END TO END (E2E)
Skenario CRUD harus bersifat End-to-End.
- **Add (Tambah)**: Klik Add -> Isi field mandatory -> Save
- **Edit (Ubah)**: Klik Action -> Klik Edit -> Ubah data -> Update
- **Delete (Hapus)**: Pilih data -> Delete -> Yes
