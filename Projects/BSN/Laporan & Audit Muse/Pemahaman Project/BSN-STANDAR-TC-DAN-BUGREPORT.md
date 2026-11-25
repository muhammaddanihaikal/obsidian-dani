# Standar TC SIT BSN & Bug Report BSN

> Hasil mempelajari dokumen standar proyek BSN di vault Obsidian Muhammad, disusun 2026-11-23.
> Sumber: `SIT BSN - Format & Standar Penulisan Test Case.md` (baku, 2026-11-17), `SIT Script Internal - BSN Lelang.md`, `SIT Script External - BSN Lelang.md`, `skill/qa-bug-reporting/SKILL.md`, `Regression Test - BSN Fase 1.md`, dibandingkan dengan `QA_RULES.md` (aturan umum QA Muhammad).
> Catatan penting: file SIT Script Internal/External di vault adalah hasil konversi `.docx` versi 1.0 (2026-10-27) — isinya adalah praktik lama dan SEBAGIAN tidak lagi sesuai standar baku 2026-11-17 (lihat catatan di A.6). Untuk menulis TC baru/update, yang berlaku adalah dokumen standar 2026-11-17.

## A. Test Case versi BSN

### A.1 Format persisnya

- File master: Excel `Script Test BSN .xlsx` (lokasi tim: `D:\Project\BSN\Fase 1\SIT\`).
- Workbook terdiri dari **3 sheet** mengikuti portal:
  1. `Script Internal` — Admin BSN (Terasrumah Admin)
  2. `Script External` — User / Pembeli publik
  3. `Script Portal Developer` — Mitra Developer
- **9 kolom berurutan (A–I)**:

| Kolom | Header | Aturan isi |
| :---: | :--- | :--- |
| A | `No` | Nomor urut modul (1, 2, 3, ...), di-merge vertikal per Menu |
| B | `Menu` | Nama menu utama, di-merge vertikal per Menu |
| C | `Sub Menu` | Di-merge vertikal per Sub Menu; kosong + di-merge jika Menu tidak punya Sub Menu |
| D | `Test Case` | Judul TC, wajib kata kerja aktif `Me-` |
| E | `Scenario` | Langkah pengguna singkat, mengikuti 2 Rumus Tim (lihat A.3) |
| F | `Expected Result` | Tepat 1 kalimat (lihat A.4) |
| G | `Actual Result` | **Dikosongkan** saat penulisan; diisi saat eksekusi SIT |
| H | `Test Status ( P = Passed, F = Failed )` | **Dikosongkan**; diisi saat eksekusi SIT |
| I | `Remark` | **Dikosongkan** |

- **Penamaan/ID**: dokumen standar SIT BSN **tidak mengatur kode/ID test case** (tidak ada format seperti `TC-xxx`). Yang ada hanya nomor urut modul di kolom A dan urutan baris TC di dalam modulnya. Pola ID seperti `TC-INT-AUTH-01` hanya dipakai di automation, bukan di dokumen SIT.

### A.2 Aturan judul (kolom Test Case)

- Wajib diawali **kata kerja aktif `Me-`**: Membuka, Memilih, Mencari, Memfilter, Mereset, Menambahkan, Mengubah, Melihat, Menghapus, Menyetujui, Menolak, Mengunduh, Mengunggah, Mengajukan, Menyimpan, dst.
- Simple, natural, **bebas kata mubazir**; hindari mengulang nama halaman di setiap judul jika kolom Sub Menu sudah jelas.
- Contoh bagus dari dokumen standar: `Membuka halaman List Developer`, `Mencari developer dengan keyword sesuai`, `Menambahkan mitra developer baru`, `Menyetujui pengajuan mitra developer`.

### A.3 Aturan Scenario (disebut "Scenario", bukan "Steps")

Mengikuti **2 Rumus Tim** berdasarkan jenis aksi:

**Rumus A — Aksi langsung → 1 baris horizontal dipisah ` - `**
Berlaku untuk: buka halaman, klik tab, search, filter, reset filter, download, detail, edit/approve singkat.
- Buka halaman (TC #1): `Klik menu <Menu> - Klik sub menu <Sub Menu>` — TC #2 dan seterusnya **jangan mengulang** langkah navigasi ini.
- Tab status: `Klik tab status selain Semua` (atau sebut nama tabnya).
- Search valid: `Input <objek pencarian>` (+ `- Klik button Cari` / `- Klik button Terapkan` jika ada tombolnya).
- Search tidak valid: `Input kata kunci tidak ada pada list` (+ `- Klik button Cari` jika ada).
- Filter sesuai: `Pilih <filter 1> - Pilih <filter 2>` (+ tombol terapkan/cari jika ada).
- Filter tidak sesuai: `Pilih filter yang tidak sesuai` (+ tombol jika ada).
- Reset filter: `Klik button Reset` / `Klik button Atur Ulang`.
- Detail/Download/Approve tabel: `Klik button Detail`, `Klik button Unduh Laporan`, `Klik button Setujui - Klik button Setujui pada pop up`.

**Rumus B — Form panjang / multi-step → poin vertikal `- ...`**
Berlaku untuk: wizard Step 1–6, Create Developer, Tindak Lanjut Leads, Pengurangan Stok, Ubah Profil/Sandi.
- Dijabarkan ke bawah per poin `- ...`, tapi **tiap baris cukup 2–4 kata sehari-hari**.
- Tanpa label UI panjang/kaku, tanpa `/`, tanpa `(opsional)`, dan tanpa menumpuk banyak field dalam 1 kalimat.
- Contoh dari dokumen standar:
  ```text
  - Klik button + Input Aset Baru
  - Pilih developer
  - Pilih tipe aset
  - Pilih proyek
  - Pilih klaster
  - Input stok unit
  - Klik button Selanjutnya
  ```

### A.4 Aturan Expected Result

- Wajib **tepat 1 kalimat** per Test Case.
- Awali dengan **`Berhasil ...`** untuk skenario sukses, atau **`Menampilkan ...`** untuk kondisi kosong (empty state) pada Search & Filter.
- Ringkas, tanpa mendaftar puluhan detail kecil UI.
- Contoh dari dokumen standar:
  - `Berhasil menampilkan halaman Daftar Mitra Developer Terdaftar beserta summary card dan tabel data`
  - `Menampilkan tabel kosong dengan keterangan data tidak ditemukan`
  - `Berhasil menyetujui pengajuan developer dan mengubah status menjadi Disetujui`

### A.5 Aturan data uji

- Dokumen standar SIT BSN **tidak mengatur data uji secara khusus** (tidak ada aturan nilai data, akun, atau format data test) — **tidak diatur di dokumen**. Yang diatur hanya frasa baku di Scenario (mis. `Input kata kunci tidak ada pada list` untuk search tidak valid, `Pilih filter yang tidak sesuai` untuk filter tidak sesuai).

### A.6 Aturan kasus negatif — kapan boleh / kapan tidak

**Zero Negative Case (kecuali Search & Filter)**:
- Negative case **HANYA boleh** dibuat untuk:
  - **Search**: keyword tidak valid / tidak ada pada list.
  - **Filter**: kombinasi filter tidak sesuai.
- **DILARANG** membuat negative case untuk: validasi field wajib/kosong, format file, ukuran file, karakter password — kecuali diminta khusus.

### A.7 Hal yang DILARANG dalam TC BSN

1. Membuat TC **Pagination** (baris per halaman / next-prev).
2. Membuat TC interaksi mikro tidak krusial: copy-to-clipboard (mis. CIF), clear search kecil, tooltip, search sekunder di dalam tab detail.
3. Membuat TC mengklik **tab default** saat halaman pertama dibuka — cukup 1 TC untuk pindah ke tab selain default.
4. Membuat TC untuk fitur yang **belum ada / masih kosong di UI** dan belum ada alur unggahnya (rawan tidak bisa dites saat SIT).
5. Mengulang langkah navigasi buka halaman di TC #2 ke bawah.
6. **Mengubah isi baris milik tim** saat menambah/merapikan script sendiri.
7. Mengedit typo/format saat menyalin sheet/menu dari file teman — wajib salin **100% utuh apa adanya (as-is)**.
8. Workflow Excel: dilarang edit tanpa backup `.xlsx` dulu; edit wajib via **Excel COM automation** (agar merged cells/border/styling tidak rusak); setelah selesai wajib **verifikasi XML diff** terhadap backup untuk memastikan 0 perubahan tidak disengaja.

> ⚠️ Catatan praktik lama: file script hasil konversi .docx v1.0 masih memuat hal-hal yang kini dilarang standar baru — contohnya TC pagination (`Cek pagination data Role`, `Pagination data User`), negative case validasi field kosong/format email/password (Modul Akun & Modul User), dan judul generik seperti `Melakukan login`. Itu warisan script lama; TC baru/update mengikuti standar 2026-11-17.

### A.8 Dua contoh TC asli dari SIT Script (dikutip ringkas, isi tidak diubah)

**Contoh 1 — Internal** (SIT Script Internal, Modul User Authority – Role, baris 1 & 6):
- Test Case: `Membuka halaman Role` — Scenario: `Klik menu User Management - Klik Sub menu Role` — Expected Result: `Menampilkan halaman Role`
- Test Case: `Filter Data Role yang tidak sesuai` — Scenario: `Input kata kunci tidak ada pada list data - Klik button Search` — Expected Result: `Menampilkan tabel kosong dengan keterangan no data`

**Contoh 2 — Eksternal** (SIT Script External, Modul Akun – Login, baris 1; sudah tereksekusi):
- Test Case: `Melakukan Login menggunakan data yang benar` — Scenario: `Input email dan kata sandi dengan data yang benar > klik masuk` — Expected Result: `Masuk ke halaman beranda/Home page` — Actual Result: sama dengan expected — Test Status: `P` — Remarks: catatan adanya Issue 13 & Issue 10 terkait halaman konfirmasi identitas.

### A.9 Perbedaan vs template kantor umum (QA_RULES.md §1)

| Aspek | Template umum (QA_RULES) | TC versi BSN |
| :--- | :--- | :--- |
| Jumlah kolom | Tepat **7 kolom**: Module, Sub Menu, Test Case Title, Description, Priority, Steps, Expected Results | **9 kolom**: No, Menu, Sub Menu, Test Case, Scenario, Expected Result, Actual Result, Test Status, Remark |
| Sheet | Tidak diatur per portal | **3 sheet per portal**: Internal, External, Portal Developer |
| Kolom Description (Positive/Negative Case) | Wajib ada, hanya 2 nilai itu | **Tidak ada** |
| Kolom Priority | Wajib ada (Critical/High/Medium/Low dengan kriteria baku) | **Tidak ada** |
| Nama kolom langkah | `Steps` — bernomor, 1 nomor = 1 aksi atomic | `Scenario` — 1 baris horizontal ` - ` untuk aksi langsung, atau poin vertikal 2–4 kata/baris untuk form panjang |
| Expected | Jumlah baris = jumlah Steps (1:1), awali "Berhasil" | **Tepat 1 kalimat**, awali `Berhasil ...` / `Menampilkan ...` (empty state) |
| Negative case | Negative form cukup 1 per form ("tanpa mengisi field mandatory"); search tepat 1 positif + 1 negatif; filter 1 positif + 1 negatif + 1 reset | **Zero negative** kecuali Search & Filter; negative validasi field/format/password dilarang |
| Sorting | Dilarang TC terpisah untuk sorting | Tidak diatur di dokumen standar BSN (script lama eksternal justru punya TC sorting) |
| Kolom hasil eksekusi | Tidak ada di template penulisan | Ada: Actual Result, Test Status (P/F), Remark — dikosongkan saat penulisan |
| Merge sel | Tidak diatur | Kolom No/Menu/Sub Menu **di-merge vertikal** |
| Aturan kolaborasi file | Tidak diatur | Ketat: backup dulu, Excel COM, XML diff, dilarang ubah baris tim, salin file teman 100% as-is |
| Format Excel (font Arial 11, header dark blue, freeze, autofilter) | Diatur rinci | Tidak diatur di dokumen standar BSN |

Persamaan: judul sama-sama wajib kata kerja `Me-`; navigasi hanya ditulis di TC pertama; pagination sama-sama dilarang dibuatkan TC terpisah (pada standar BSN yang baru).

## B. Bug Report versi BSN

### B.1 Format judul persisnya (Golden Formula)

```text
🐞 [BUG] | [Komponen / Fitur Spesifik] + [Kondisi Cacat Sistem]
```

Aturan judul:
- **TANPA nama modul/menu** di judul (modul sudah tercatat di field Menu / label Huly).
- **Title Case** untuk kata utama; kata hubung & preposisi wajib huruf kecil: `dan, atau, ke, di, pada, dari, saat, dengan, untuk, yang, meskipun`.
- Panjang fleksibel — tidak ada kuota kata kaku; prioritaskan simple, to the point, enak dibaca.
- **Anti-mubazir (zero filler words)**: dilarang kata pengganjal seperti "Normal", "Tanpa Data", "Data", "Pesan/Respon".
- Contoh asli dari tracker: `🐞 [BUG] | Gagal Logout Akun dan Muncul Halaman Error`, `🐞 [BUG] | Dropdown Kantor pada Form Tambah User Kosong`.

### B.2 Struktur isi `report.txt`

Ada **dua format** yang berlaku di BSN, tergantung umur issue:

**(1) Format lama** — untuk issue yang sudah dibuat sebelumnya (tetap berlaku, tidak dikonversi). Isi `report.txt` untuk copas ke Huly, urutan field:

```markdown
🐞 [BUG] | {Judul Simple & Enak Dibaca}

* **Menu**: {Modul} → {Sub Menu} (Tab {Nama Tab jika ada})
* **Deskripsi**: {alur masalah runut, padat, 1–2 kalimat}
* **Expected**: {kondisi ideal sesuai PRD / aturan bisnis}
* **Actual**: {kondisi error / penyimpangan saat ini}
* **Evidence**:
  * {Label 1-2 Kata}: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
```

Aturan clean styling Huly (format lama):
- **Dilarang blockquote `> `** — memunculkan garis vertikal oranye/kuning di Huly; wajib bullet biasa `* `.
- **Dilarang backtick** di `report.txt` maupun `komentar_huly.txt` — memicu badge/pill kuning-oranye; pakai kutip dua biasa `"..."` atau plain text untuk nama button/tab/status/toast.
- **Dilarang baris `Status:`** di report.txt (status ada di dropdown panel kanan Huly).
- Setiap link evidence Catbox wajib diawali **label ringkas 1–2 kata**.

**(2) Template resmi tim Huly (format BARU)** — **wajib untuk semua issue BARU**. Struktur `report.txt`:

```markdown
🐞 [BUG] | {Short Summary}

**Priority:** Select One (Urgent 🔴 | High 🟠 | Normal 🟡 | Low 🔵 )

**Label:** `bug` `triage-needed` `[Module Name]`

**Linked Issue/PR:** # (If applicable)

## 📖 Overview

> {ringkasan kegagalan 1-2 kalimat}

* **Impact:** {apa yang membuat user tidak bisa melakukan sesuatu}
* **Frequency:** {mis. 100% of the time, intermittent, only on first load}

## 🛠 Steps to Reproduce

1. Log in to the workspace.
2. Navigate to **[Specific Page/Sidebar]**.
3. Perform action: **[e.g., Click 'Save']**.
4. Observe the result.

## 🔍 Technical Context

| Field | Detail |
|---|---|
| **Expected** | {yang seharusnya terjadi} |
| **Actual** | {yang benar-benar terjadi, sertakan error code bila ada} |
| **Environment** | {Production / Staging / Local} |
| **Device/OS** | {mis. macOS Sonoma / Chrome 122} |
| **User Role** | {Admin / Guest / Member} |

## 🪵 Logs & Media

* **Screenshots:** (Drag and drop images here)
* **Console Logs:** (blok kode untuk stack trace / console error)

## ✅ Checklist for Fix

• [ ] Reproduce locally.
• [ ] Add regression test.
• [ ] Verify fix in Staging.
• [ ] Update documentation (if behavior changed).
```

Aturan khusus template baru:
- Emoji bug **🐞** (sesuai template resmi tim).
- Blockquote `> ` pada Overview **BOLEH** — itu bagian struktur template tim (pengecualian dari larangan clean styling format lama).
- **Steps to Reproduce selalu disertakan.** Jika STR butuh langkah custom yang panjang, tampilkan draf ke user dan tunggu approval sebelum finalisasi.
- Screenshot: **drag-and-drop langsung** di bagian Logs & Media Huly — bukan link Catbox.
- Koreksi Muhammad 2026-11-25 (berlaku untuk issue berikutnya; issue Huly yang sudah terbuat TIDAK perlu diubah): baris Screenshots WAJIB persis template "(Drag and drop images here)" — JANGAN ditambah catatan apa pun (mis. "file draft lokal: evidence_...png (...)"). Console Logs WAJIB mempertahankan blok kode bash template ("# Paste any relevant stack traces or console errors here" + baris contoh template), BUKAN diisi "-" polos.
- Koreksi Muhammad 2026-11-25 (lanjutan, dari screenshot template mentah Huly): baris Priority di teks report DIPILIH satu nilai (keputusan final Muhammad 25 Nov 11:40, membatalkan arahan persis-template sebelumnya). STR ditulis dalam Bahasa Indonesia (struktur 4 langkah sama). Overview faktual & ringkas: tanpa detail proses verifikasi (mis. "dicek 3x") dan tanpa dugaan penyebab (mis. "dugaan static frontend"). Poin-poin Overview multi-kasus masuk DI DALAM blockquote Overview (area garis oranye), bukan bullet lepas di bawahnya; Impact/Frequency tetap di luar blockquote. Linked Issue/PR persis "# (If applicable)". STR = 4 langkah sesuai template.
- Issue lama dibiarkan as-is dengan format lama, tidak perlu dikonversi.

### B.3 `komentar_huly.txt` — apa & formatnya

- Fungsi: draft teks untuk kolom **Komentar / Update Retest di Huly**.
- **Saat issue baru dibuat, file ini WAJIB KOSONG.** Baru diisi saat retest selesai: berhasil (`Done`) atau gagal (`Re-Open`).
- Format isinya (plain text, bebas kuning, tanpa backtick):

```markdown
Retest: Done

{Penjelasan ringkas 1-2 kalimat kondisi setelah perbaikan}

Bukti Retest:
* {Label 1-2 Kata}: [https://files.catbox.moe/xxx.png](https://files.catbox.moe/xxx.png)
```

### B.4 Struktur folder & penamaan

```text
Bug Report/
└── [Portal: Internal / External]/
    └── [Nama Modul atau Menu]/
        └── [Nama Sub Menu]/
            ├── 01 - [Judul Singkat Masalah]/
            │   ├── report.txt
            │   ├── komentar_huly.txt
            │   └── evidence_01_error.png
            └── 02 - [Judul Singkat Masalah]/   ← +1 incremental per Sub Menu
```

- Folder issue: format `[Nomor 2 digit] - [Judul Singkat Masalah]`, mulai `01`, bertambah **+1** untuk temuan baru di sub menu yang sama.
- Isi wajib tiap folder issue: `report.txt` + `komentar_huly.txt` + file screenshot evidence.
- Nama file screenshot mengikuti pola `evidence_[nn]_[deskripsi].png` (contoh di skill: `evidence_01_error.png`, `evidence_01_blank.png`).
- Red box pada area error: **tidak disebutkan di skill qa-bug-reporting**; aturan memberi kotak merah pada screenshot ada di standar umum Muhammad (MEMORY/QA workflow), bukan di dokumen skill BSN.

### B.5 Aturan evidence / screenshot

- Format lama: screenshot di-upload ke **Catbox**, link publiknya `[url](url)` ditempel di Evidence report.txt / Bukti Retest komentar, selalu dengan label 1–2 kata.
- Template tim baru: screenshot **drag-and-drop langsung ke Huly** (bagian Logs & Media) — **BUKAN link Catbox** di bagian itu.
- Upload Catbox **tidak boleh dilakukan sebelum draft di-ACC user** (bagian dari approval gate).
- Setelah ACC: screenshot dipindahkan dari folder tampungan ke folder issue dan folder tampungan dibersihkan.

### B.6 Approval gate — langkah persis sebelum file dibuat

**Aturan mutlak**: sebelum user menyetujui draft, AI **DILARANG**: membuat folder lokal, menghapus/memindahkan screenshot dari folder tampungan, meng-update tracker Obsidian, dan mengunggah ke Catbox.

1. **Langkah 1 — Fast Draft (tanpa upload Catbox dulu)**: AI menganalisis screenshot langsung dari file lokal di folder tampungan, lalu menyajikan draft proposal issue lengkap di chat (Judul, Menu, Deskripsi, Expected, Actual, label Evidence lokal).
2. **Langkah 2 — Tunggu approval user**: AI meminta review, mis. *"Gimana judul dan detailnya bro, mau langsung dieksekusi?"* — berhenti dan tunggu.
3. **Langkah 3 — Eksekusi setelah di-ACC** (user memberi lampu hijau, mis. "gas" / "oke" / "eksekusi"), baru AI:
   - Mengunggah screenshot ke Catbox untuk mendapat URL publik.
   - Membuat folder issue dengan nomor +1 berikutnya.
   - Menyimpan `report.txt` (dengan link Catbox) dan `komentar_huly.txt` (**kosong**).
   - Memindahkan & membersihkan screenshot dari folder tampungan.
   - Memperbarui Master Tracker di Obsidian (`Projects/BSN/Regression Test - BSN Fase 1.md`) lalu `git commit` & `git push` ke `origin/main`.

Preferensi penyajian saat membantu update Huly: sajikan per nomor/kode issue tanpa tabel bila user minta langsung copy; urutkan top-to-bottom sesuai layar Huly user (`BSN_I-xx` / `HULY-xx`); teks dalam code block terpisah agar 1-klik copy; dahulukan daftar issue yang berubah saja.

### B.7 Contoh bug report asli dari Regression Test – BSN Fase 1 (struktur di tracker Obsidian)

Contoh: issue `Internal/User Management/User/01` — satu-satunya yang berstatus Done:

```text
### 🐞 [BUG] | Dropdown Kantor pada Form Tambah User Kosong

> * **Menu**: User Management → User
> * **Status**: Done
> * **Deskripsi**: Saat user mengisi form tambah user dan membuka dropdown Kantor, opsi daftar kantor tidak muncul dan hanya menampilkan status "No data".
> * **Expected**: Dropdown Kantor menampilkan seluruh daftar kantor cabang yang aktif dan dapat dipilih oleh user.
> * **Actual**: Dropdown Kantor kosong dan hanya menampilkan "No data", sehingga proses submit data user tidak dapat diselesaikan.
> * **Evidence Awal**:
>   * Dropdown Kantor No Data: [link Catbox]
> * **Bukti Retest (Done)**:
>   * Dropdown Kantor: [link Catbox]
> * **Catatan Retest**:
>   * Dropdown Kantor sudah berhasil menampilkan daftar kantor cabang aktif.
```

Struktur baku entri tracker yang terlihat konsisten di seluruh file: judul `### 🐞 [BUG] | ...`, lalu blockquote berisi **Menu → Status → Deskripsi → Expected → Actual → Evidence Awal → Bukti Retest (Done/Re-Open) → Catatan Retest** (dua field retest diisi `-` selama belum diretest). Varian: 8 entri Stock Management – Aset Baru di bagian atas file memakai label **`Overview`** sebagai pengganti `Deskripsi`. Status di tracker memakai nilai: Open / Done / Re-Open / Catatan-Klarifikasi. File tracker juga memuat 3 tabel rekap: Progress Summary per menu, Status Input Issue ke Huly (total 51 bug, 0 reported / 51 pending), dan Matriks Status Issue QA (46 Open, 1 Done, 2 Catatan/Klarifikasi, 2 Re-Open).

### B.8 Perbedaan vs standar bug report umum (QA_RULES.md §3)

| Aspek | Umum (QA_RULES §3 / TC Template 05) | Versi BSN (skill qa-bug-reporting) |
| :--- | :--- | :--- |
| Judul | Sama: `🐞 [BUG] \| Komponen + Kondisi Cacat`, tanpa nama modul, Title Case, anti-filler | **Sama persis** (skill BSN adalah sumber standar yang sama) |
| report.txt format lama | Bullet `* ` Menu/Deskripsi/Expected/Actual/Evidence Catbox; dilarang blockquote, backtick, baris Status | **Sama persis** |
| Template tim Huly baru | **Tidak ada** — QA_RULES menegaskan report.txt TANPA field severity/priority dan STR hanya bila alur panjang/kompleks | **Ada & wajib untuk issue baru**: ada Priority, Label, Linked Issue/PR, Overview, Impact/Frequency, **STR selalu disertakan**, Technical Context, Logs & Media, Checklist for Fix |
| Screenshot di Huly | Link Catbox `[url](url)` di Evidence | Template baru: **drag-and-drop langsung** di Huly, bukan Catbox (Catbox tetap untuk format lama & bukti retest) |
| Struktur folder | `Bug Report/` → per menu/modul → folder issue `NN - Judul` | Ada **level Portal** di atasnya: `Bug Report/[Portal]/[Modul]/[Sub Menu]/NN - Judul/` |
| komentar_huly.txt | Kosong saat baru; saat retest ringkas `Retest: Done/Re-Open`; QA_RULES menyebut istilah penting dibungkus **backtick** (highlight kuning di komentar memang dipakai) | Kosong saat baru; format `Retest: Done` + penjelasan + Bukti Retest; skill BSN menegaskan **tanpa backtick** (plain text bebas kuning) — *catatan: dua dokumen berbeda di poin backtick komentar ini; skill BSN adalah SOP khusus proyek BSN* |
| Judul di tracker Obsidian | Pakai **prefix menu** | Praktik tracker BSN: judul **tanpa prefix menu**; Menu ditulis sebagai field di dalam blockquote, plus baris `Status` wajib ada di tracker |
| Approval gate | Sama: draft preview → konfirmasi eksplisit → baru buat folder/file | Sama, ditambah larangan eksplisit upload Catbox & memindahkan screenshot tampungan sebelum ACC, dan kewajiban commit + push vault setelah update tracker |
| Nama file screenshot | `evidence_[nn]_[desc].png`, retest `retest_done_[nn]_...` / `retest_reopen_[nn]_...`, wajib red box | Pola `evidence_[nn]_[desc].png` sama; penamaan varian retest & red box tidak diatur di skill BSN |

## C. Checklist verifikasi diri — sebelum kirim TC / bug report ke Muhammad, cek ini

**Test Case BSN:**
1. ☐ Sheet benar sesuai portal (Internal / External / Portal Developer) dan kolom lengkap 9 (A–I) dengan No/Menu/Sub Menu di-merge vertikal.
2. ☐ Judul diawali kata kerja `Me-`, simple, tanpa kata mubazir dan tanpa mengulang nama halaman yang sudah jelas di Sub Menu.
3. ☐ Scenario mengikuti rumus yang benar: aksi langsung = 1 baris ` - `; form panjang = poin vertikal 2–4 kata per baris, tanpa `/` dan tanpa `(opsional)`.
4. ☐ Langkah navigasi buka halaman hanya ada di TC #1; TC berikutnya langsung ke aksi utama.
5. ☐ Expected Result tepat **1 kalimat**, diawali `Berhasil ...` (atau `Menampilkan ...` untuk empty state Search & Filter).
6. ☐ Tidak ada negative case di luar Search & Filter (tidak ada TC validasi field kosong/format file/password).
7. ☐ Tidak ada TC pagination, tab default, tooltip/clear-search mikro, atau fitur yang belum ada alur ujinya di UI.
8. ☐ Kolom Actual Result, Test Status, Remark masih kosong; tidak menyentuh/mengubah satu pun baris milik tim; file hasil edit sudah dibackup dan lolos verifikasi XML diff (0 perubahan tak disengaja).

**Bug Report BSN:**
9. ☐ Judul mengikuti Golden Formula `🐞 [BUG] | ...`, tanpa nama modul, Title Case benar (kata hubung/preposisi huruf kecil), nol kata filler.
10. ☐ Format tepat guna: issue BARU memakai template tim Huly (Priority, Label, STR selalu ada, Technical Context, Checklist for Fix); issue lama tetap format lama bullet `* `.
11. ☐ report.txt format lama: tanpa blockquote, tanpa backtick, tanpa baris `Status:`, evidence Catbox berlabel 1–2 kata; template baru: screenshot disiapkan untuk drag-and-drop ke Huly, bukan link Catbox.
12. ☐ `komentar_huly.txt` masih **kosong** untuk issue baru (hanya diisi setelah retest, format `Retest: Done/Re-Open`).
13. ☐ Nomor folder issue = nomor terakhir di sub menu yang sama **+1**; struktur `Bug Report/[Portal]/[Modul]/[Sub Menu]/NN - Judul/` lengkap berisi report.txt, komentar_huly.txt, evidence.
14. ☐ **Approval gate dipatuhi**: draft sudah ditampilkan ke Muhammad dan di-ACC SEBELUM folder dibuat / screenshot dipindah dari tampungan / Catbox di-upload / tracker Obsidian di-update.
15. ☐ Setelah eksekusi: tracker `Regression Test - BSN Fase 1.md` diperbarui (entri blockquote + Status + tabel rekap) dan vault sudah di-commit & push.
