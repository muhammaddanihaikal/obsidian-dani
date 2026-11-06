---
name: qa-bug-reporting
description: >
  Standard operating procedure for QA bug reporting, Huly issue synchronization,
  clean styling (zero yellow blockquotes or backtick badges), evidence management,
  folder structuring (+1 incremental rule), and Obsidian master tracker updates.
  Trigger when reporting bugs, creating report.txt, updating Huly issues, or managing QA regression tests.
license: MIT
---

# 🐞 QA Bug Reporting & Huly Synchronization Guide

Panduan standar operasional untuk Quality Assurance (QA) dalam mendokumentasikan temuan bug, membuat arsip lokal, menyusun deskripsi issue untuk **Huly**, serta menjaga sinkronisasi master tracker di **Obsidian**.

---

## 🗂️ 1. Hierarki & Penamaan Folder Lokal (File Manager)

Setiap pengujian modul/fitur wajib memiliki arsip bukti lokal yang terstruktur:

```
📁 Bug Report/
└── 📁 [Portal: Internal / External]/
    └── 📁 [Nama Modul atau Menu]/
        └── 📁 [Nama Sub Menu]/                      <-- Folder Sub Menu
            ├── 📁 01 - [Judul Singkat Masalah]/
            │   ├── 📄 report.txt
            │   ├── 📄 komentar_huly.txt
            │   └── 🖼️ evidence_01_error.png
            ├── 📁 02 - [Judul Singkat Masalah]/    <-- +1 Incremental per Sub Menu
            │   ├── 📄 report.txt
            │   ├── 📄 komentar_huly.txt
            │   └── 🖼️ evidence_01_blank.png
```

### Aturan Penomoran Incremental (`+1` Rule):
1. **Root**: Folder utama bernama `Bug Report`.
2. **Folder Menu**: Disesuaikan dengan nama menu di aplikasi (misal `Authentication`, `User Management`, `Office Management`, `Beranda`).
3. **Folder Issue**: Diletakkan di dalam folder `[Sub Menu]`, dengan format `[Nomor Issue] - [Judul Singkat Masalah]`. Nomor diawali `01` dan bertambah **+1** untuk temuan baru di sub menu yang sama.

---

## 📄 2. Standar Dua File `.txt` di Setiap Folder Issue

1. `report.txt`: Sumber utama yang berisi judul dan detail bug yang siap di-copas ke **Huly**.
2. `komentar_huly.txt`: Draft teks untuk kolom **Komentar / Update Retest di Huly**.
   * **PENTING**: Saat issue baru dibuat, file ini **WAJIB KOSONG**. Baru diisi saat pengujian ulang (retest) berhasil (`Done`) atau gagal (`Re-Open`).

---

## 🏷️ 3. The Golden Formula: Standar Penamaan Judul Bug

### Pola Baku:
$$\mathbf{🐞\ [BUG]\ |\ [Komponen\ /\ Fitur\ Spesifik]\ +\ [Kondisi\ Cacat\ Sistem]}$$

* **TANPA Nama Modul**: Dilarang mengulang nama menu/modul di dalam judul (misal `Authentication - Login: ...`) karena modul sudah tercatat di field Menu atau label/tag Huly.
* **Filosofi Natural Flow (Bebas Kuota Kaku)**:
  * Tidak ada batasan atau kuota jumlah kata yang kaku.
  * Prioritaskan kalimat yang **Simple, To The Point, dan Enak Dibaca**.
  * **Anti-Mubazir (*Zero Filler Words*)**: Dilarang menyelipkan kata pengganjal seperti *"Normal"*, *"Tanpa Data"*, *"Data"*, atau *"Pesan/Respon"*.
* **Kaidah Tipografi (Title Case Headline)**:
  * Kata Utama diawali **Huruf Kapital**.
  * Kata Hubung & Preposisi WAJIB **huruf kecil (*lowercase*)**: `dan`, `atau`, `ke`, `di`, `pada`, `dari`, `saat`, `dengan`, `untuk`, `yang`, `meskipun`.

---

## 🎨 4. Format Teks Huly Bebas Kuning-Kuning (Clean Styling)

Aplikasi Huly memiliki parser markdown khusus yang merender elemen tertentu dengan warna mencolok. Untuk menjaga tampilan profesional dan bersih (seperti tampilan `HULY-35`):

1. **DILARANG Menggunakan Blockquote (`> `)**:
   * Tanda `> ` di awal baris otomatis memunculkan **garis vertikal oranye/kuning** di samping teks.
   * **Wajib gunakan bullet point biasa (`* `)**.
2. **DILARANG Menggunakan Backticks (`` `...` ``)**:
   * Tanda petik miring (backticks) otomatis memicu **badge / pill kotak kuning-oranye**.
   * Dilarang menggunakan backticks baik pada `report.txt` maupun `komentar_huly.txt`.
   * Gunakan tanda kutip ganda biasa (`"..."`) atau plain text untuk nama tombol, nama tab, nama status, dan pesan toast/error.
3. **Dilarang Baris `Status:` di `report.txt`**:
   * Dropdown status sudah ada di panel kanan Huly. Teks deskripsi dilarang memuat baris status.
4. **Label Evidence Wajib (1–2 Kata)**:
   * Setiap link Catbox wajib diawali label ringkas penjelas (contoh: `* Halaman Error: [link]`).

### Template Baku `report.txt`:
```markdown
🐞 [BUG] | {Judul Simple & Enak Dibaca}

* **Menu**: {Modul} → {Sub Menu} (Tab {Nama Tab jika ada})
* **Deskripsi**: {Jelaskan alur masalah secara runut, padat, dan to the point (1–2 kalimat)}
* **Expected**: {Kondisi ideal seharusnya sesuai PRD atau aturan bisnis}
* **Actual**: {Kondisi error, cacat sistem, atau penyimpangan saat ini}
* **Evidence**:
  * {Label 1-2 Kata}: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
```

### Template Baku `komentar_huly.txt` (Bebas Kuning / Plain Text):
```markdown
Retest: Done

{Penjelasan ringkas 1-2 kalimat kondisi setelah perbaikan tanpa backtick}

Bukti Retest:
* {Label 1-2 Kata}: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
```

---

## 🛑 5. Alur Wajib Pembuatan Issue Baru (Review & Approval Gate)

**ATURAN MUTLAK**: AI dilarang langsung membuat folder lokal, dilarang menghapus/memindahkan screenshot dari tampungan, dilarang meng-update tracker Obsidian, dan **DILARANG mengunggah ke Catbox sebelum draf disetujui USER** agar hemat waktu.

1. **Langkah 1 (Fast Draft - Tanpa Upload Catbox Dulu)**:
   * AI menganalisis screenshot langsung dari file lokal di folder tampungan.
   * Sajikan draft proposal issue lengkap ke chat user (Judul, Menu, Deskripsi, Expected, Actual, dan label Evidence lokal). Tunda upload Catbox sampai draf disetujui.
2. **Langkah 2 (Tunggu Approval User)**:
   * AI meminta review user: *"Gimana judul dan detailnya bro, mau langsung dieksekusi?"*.
3. **Langkah 3 (Eksekusi Setelah Di-approve / Di-ACC)**:
   * Baru setelah user memberikan lampu hijau (misal: *"gas"*, *"oke"*, *"eksekusi"*), AI:
     * Mengunggah screenshot ke Catbox untuk mendapatkan URL publik `[URL](URL)`.
     * Membuat folder issue `01`, `02`, `+1`.
     * Menyimpan `report.txt` (dengan link Catbox) dan `komentar_huly.txt` (kosong).
     * Memindahkan & membersihkan file screenshot dari folder `tampungan screenshot`.
     * Memperbarui Master Tracker di Obsidian dan melakukan `git commit` & `git push` ke `origin/main`.

---

## ⚡ 6. Preferensi Presentasi saat Membantu User Update Huly

Saat menyajikan daftar issue kepada user untuk di-copas ke board Huly:
1. **Tanpa Tabel jika diminta langsung copy**: Langsung sajikan per nomor/kode issue.
2. **Urutan Top-to-Bottom Layar User**: Urutkan dari atas ke bawah mencocokkan baris yang terlihat di layar Huly user (`BSN_I-xx` atau `HULY-xx`).
3. **Blok 1-Klik Copy**: Berikan teks baru dalam markdown code block terpisah (`text` / `markdown`) agar user tinggal klik ikon copy tanpa seleksi kursor.
4. **Pilah Yang Berubah vs Tidak Berubah**: Berikan daftar issue yang berubah saja terlebih dahulu agar user hemat waktu.

---

## 📓 6. Sinkronisasi Obsidian Vault & Git Otomatis

* Seluruh catatan master, test script (SIT), dan regression tracker tersimpan di:
  `D:\Obsidian\dani`
* Setiap kali ada penambahan issue, perapian judul, atau update status regresi:
  1. Perbarui file master tracker: `Projects/BSN/Regression Test - BSN Fase 1.md`.
  2. Perbarui panduan standar jika ada aturan baru: `Test Case/TC Template/05 - Standar Bug Report & Manajemen Folder Issue.md`.
  3. **Wajib langsung jalankan git commit dan push**:
     ```powershell
     git -C "D:\Obsidian\dani" commit -am "docs(QA): <ringkasan update>"
     git -C "D:\Obsidian\dani" push origin main
     ```
---

## 🐛 7. Template Resmi Tim Huly (Berlaku untuk Issue Baru)

> Template lama (format `report.txt` dengan Catbox) tetap berlaku untuk issue-issue yang sudah dibuat sebelumnya. Semua issue BARU wajib menggunakan template tim berikut.

### Template Baku `report.txt` (New Team Format):

```
🐛 [BUG] | {Short Summary}

Priority: Select One (Urgent 🔴 | High 🟠 | Normal 🟡 | Low 🔵)

Label: bug triage-needed [Module Name]

Linked Issue/PR: # (If applicable)

📖 Overview

> {Give a 1-2 sentence high-level summary of the failure.}

* **Impact:** {What does this stop the user from doing?}
* **Frequency:** {e.g., 100% of the time, intermittent, only on first load}

🛠 Steps to Reproduce

1. Log in to the workspace.
2. Navigate to {Specific Page/Sidebar}.
3. Perform action: {e.g., Click 'Save'}.
4. Observe the result.

🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | {What should have happened?} |
| **Actual** | {What did happen? Include error codes if any} |
| **Environment** | {Production / Staging / Local} |
| **Device/OS** | {e.g., macOS Sonoma / Chrome 122} |
| **User Role** | {e.g., Admin / Guest / Member} |

🪵 Logs & Media

* **Screenshots:** (Drag and drop images here)
* **Console Logs:**

✅ Checklist for Fix

* [ ] Reproduce locally.
* [ ] Add regression test.
* [ ] Verify fix in Staging.
* [ ] Update documentation (if behavior changed).
```

### Aturan Penting Template Tim:

1. **Emoji Bug**: 🐛 (bukan 🐞) — sesuai template resmi tim.
2. **Overview blockquote**: `> ` BOLEH dipakai di sini karena ini bagian dari struktur template tim.
3. **Steps to Reproduce**: Selalu sertakan. Jika STR perlu langkah custom yang panjang, tampilkan draf ke user dan tunggu approval sebelum finalisasi.
4. **Screenshots di Huly**: Drag-and-drop langsung ke bagian Logs & Media — BUKAN link Catbox di bagian ini.
5. **Issue lama**: Dibiarkan as-is dengan format lama, tidak perlu dikonversi.
