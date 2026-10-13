# 📝 Testing Log - Sync Hasil Uji Modul 26 & 67 Web (13 Oktober 2026)

Catatan sinkronisasi screenshot baru dari tim untuk **Modul 26 (Lead Qualification - Aktifitas)** dan **Modul 67 (Re-Assign dan Approval - Re-Assign Prospek)**, standarisasi penamaan file tanpa leading zero, penyelarasan konsistensi (Excel, SIT, Hasil Uji), serta embedding gambar ke dalam dokumen Word Hasil Uji Web.

---

## 📌 Informasi Sinkronisasi
* **Tanggal**: 13 Oktober 2026 (~17:30 WIB)
* **Tester / PIC**: Dani & Team QA
* **Status**: **SINKRONISASI, EMBEDDING, & TRI-DRIVE PARITY 100% LENGKAP** ✅

---

## 1. 🔍 Temuan Screenshot Baru dari Tim (Drive H)
Di-upload oleh rekan tim pada tanggal 13 Oktober 2026 (15:04 s/d 16:11 WIB):
1. **Modul 26 (`26. Lead Qualification - Aktifitas`) — Total 43 Gambar Baru:**
   * `26.8` Melakukan call dengan menambahkan pengingat (4 gambar)
   * `26.16` Membuat tugas (4 gambar)
   * `26.17` Membuat tugas tanpa mengisi field mandatory (1 gambar)
   * `26.18` Melihat detail tugas (3 gambar)
   * `26.19` Melihat aktivitas dan percakapan tugas (4 gambar)
   * `26.20` Menambahkan komentar pada tugas (4 gambar)
   * `26.21` Menghapus komentar pada tugas (4 gambar)
   * `26.22` Mengedit tugas (5 gambar)
   * `26.23` Mengedit tugas tanpa mengisi field mandatory (4 gambar)
   * `26.24` Menghapus tugas (5 gambar)
   * `26.25` Membagikan tugas (5 gambar)

2. **Modul 67 (`67. Re-Assign dan Approval - Re-Assign Prospek`) — 1 Baru + 5 Updated:**
   * **Baru:** `67.5/4.png` (melakukan re-assign beberapa data prospek)
   * **Updated:** `67.1/1.png`, `67.4/1.png`, `67.5/1.png`, `67.5/2.png`, `67.5/3.png` (resolusi dan tampilan diperbarui oleh tim).

3. **Pembersihan File Orphan/Redundan Modul 67:**
   * Ditemukan 10 file lama berekstensi `0x.png` (`01.png`, `02.png`, dst.) yang merupakan duplikat di Local D dan Drive G. Seluruhnya telah dibersihkan agar seragam dengan Drive H yang hanya menggunakan format angka tunggal (`1.png`, `2.png`, dst.).

---

## 2. 🏷️ Standarisasi Penamaan File Screenshot
* Sesuai preferensi dan pedoman proyek, seluruh penamaan file screenshot distandarisasi **tanpa leading zero**:
  * `01.jpeg` $\rightarrow$ `1.jpeg`
  * `02.jpeg` $\rightarrow$ `2.jpeg`
  * `03 (1).jpeg` $\rightarrow$ `3.jpeg` *(anomali duplikat download diperbaiki)*
  * `04.jpeg` $\rightarrow$ `4.jpeg`
  * `05.jpeg` $\rightarrow$ `5.jpeg`
* Standarisasi diterapkan serentak di ketiga drive: **Local D**, **Drive H**, dan **Drive G**.

---

## 3. ⚖️ Verifikasi Penyelarasan Dokumen (Excel vs SIT vs Hasil Uji)
Dilakukan audit 4 sisi terhadap seluruh 31 Test Case (25 TC Modul 26 + 6 TC Modul 67):
* **Excel Test Case (`SIT\Test Case.xlsx`)**: 31 TC terdaftar lengkap.
* **SIT Word (`SIT\SIT BTN SMART Web.docx`)**: 31 TC nomor dan judul 100% identik dengan Excel.
* **Hasil Uji Word (`Hasil Uji\Dokumen_Hasil_Uji_Web.docx`)**: 31 TC nomor dan judul 100% identik dengan Excel dan SIT.
* **Folder Screenshot (`Hasil Uji\Screenshot\Web\`)**: Penamaan folder TC 100% presisi (`[No] [Judul]`).

---

## 4. 📄 Embedding Gambar ke Dokumen Word Hasil Uji Web
* **Dokumen Target**: `Hasil Uji\Dokumen_Hasil_Uji_Web.docx`
* **Table 29 (Modul 26)**: Berhasil menyematkan **43 gambar** ke dalam 11 TC yang sebelumnya kosong (`26.8` dan `26.16` s/d `26.25`).
* **Table 70 (Modul 67)**: Berhasil memperbarui dan menyematkan **14 gambar** untuk seluruh 6 TC (`67.1` s/d `67.6`), termasuk penambahan `4.png` pada TC `67.5`.
* **Layout & Styling**:
  * Gambar diset dengan lebar standar `5.9 inch` (~15.0 cm), Alignment Center.
  * Paragraph spacing diset `Space Before = 6 pt`, `Space After = 6 pt`.
  * Properti `trHeight` fixed (misal `4316`) pada baris screenshot dibersihkan agar tinggi baris menyesuaikan ukuran gambar secara alami.
* **Ukuran File Dokumen Akhir**: Meningkat dari `153.9 MB` menjadi `157.4 MB`.

---

## 5. 🌐 Tri-Drive Parity & Git Version Control
1. **Drive Synchronization**:
   * File `Dokumen_Hasil_Uji_Web.docx` (157.4 MB) berhasil disinkronkan ke **Drive H** dan **Drive G**.
   * Parity folder screenshot Web antara Drive H, Local D, dan Drive G: **0 differences (100% in sync)**.
2. **Git Commit & Push**:
   * Commit 1: `39340a1` — *feat(web): sync and standardize new screenshots for Module 26 and Module 67*
   * Commit 2: `ff1f1f8` — *feat(web): embed Modul 26 and 67 screenshots into Dokumen_Hasil_Uji_Web.docx and cleanup redundant 0x.png*
   * Branch: `main` (pushed via Git LFS).


---

## 6. 🔲 Pemisahan Kotak Test Case (Layout Standar Mobile)
* **Permintaan User**: Kotak tabel tiap Test Case di Dokumen_Hasil_Uji_Web.docx yang sebelumnya menyatu dalam satu tabel besar per modul, dipisahkan per kotak individual dengan spasi paragraf antar-tabel agar identik dengan tampilan Dokumen_Hasil_Uji_Mobile.docx.
* **Eksekusi**:
  * Seluruh 71 modul tabel berhasil dipisahkan menjadi tabel-tabel per TC.
  * Total tabel di dokumen Web meningkat dari 75 menjadi **931 tabel**.
  * Tiap TC memiliki batas border tertutup sendiri dan dipisahkan oleh paragraf kosong (<w:p/>), menghasilkan visual layout yang rapi dan terisolasi.
  * Tri-drive sync ke Drive H dan Drive G selesai 100%.
  * Git commit e956086 pushed ke main.
