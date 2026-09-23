---
tags:
  - QA
  - AI
  - ContextEngineering
  - PromptEngineering
  - BestPractice
date: 2026-09-23
---
# 🧠 01 - Prompt vs Context Engineering & Best Practice Workflow QA AI

Catatan ini merangkum pergeseran paradigma dari **Prompt Engineering** ke **Context Engineering**, serta panduan implementasi alur kerja QA (*Quality Assurance*) berbasis AI agar menghasilkan output berstandar industri (10/10).

---

## 1. Fondasi: Prompt Engineering vs Context Engineering

### A. Analogi Meja Kerja
Bayangkan kamu menyewa seorang **konsultan jenius** (LLM):
* **Prompt Engineering:** Memikirkan kalimat instruksi yang sangat sopan, detail, dan memakai trik kata-kata (*"Bertindaklah sebagai Senior QA kelas dunia, pikirkan langkah demi langkah..."*).
* **Context Engineering:** Menyiapkan **berkas data yang relevan di atas mejanya** (PRD terbaru, skema database, log error spesifik, API docs, dan template baku) sebelum si konsultan mulai bekerja.

> [!NOTE]
> Tanpa data dan konteks yang akurat, sebaik apa pun kalimat instruksimu, model AI tetap akan menebak-nebak atau berhalusinasi (*Garbage In, Garbage Out*).

### B. Tabel Perbandingan

| Pembeda | Prompt Engineering | Context Engineering |
| :--- | :--- | :--- |
| **Fokus Utama** | Formulasi teks & kata-kata (*Wording & Instruction*). | Kurasi data, state, memory, dan lingkungan (*Information Architecture*). |
| **Teknik Kunci** | Roleplay, Few-Shot text, Chain-of-Thought (CoT), Delimiter. | RAG (Vector Search), Context Window Management, Tool Use/MCP, Pruning/Filtering. |
| **Penerapan** | Kotak chat user / baris instruksi awal. | Arsitektur data, file referensi, project rules, context cache. |
| **Tujuan** | Memandu cara model menalar. | Memastikan model memiliki fakta akurat tanpa *noise* berlebih. |

### C. Mengapa Industri Beralih ke Context Engineering?
1. **Model Modern Sudah Sangat Cerdas**: Model penalaran modern sudah paham bahasa alami tanpa memerlukan "mantra prompt" aneh-aneh.
2. **Era AI Agent & Coding Tools**: Keberhasilan tools seperti Cursor, Devin, atau coding assistant 90% ditentukan oleh file mana yang dibaca dan tools apa yang diekspos ke model.
3. **Masalah *Noise* & *"Lost in the Middle"***: Memasukkan konteks terlalu banyak justru menurunkan akurasi (*attention drift*). Context engineering menyaring hanya data esensial (*high signal-to-noise ratio*).
4. **Efisiensi Token & Biaya**: Penggunaan *prompt caching* dan kompresi konteks mempercepat respons dan menghemat biaya API.

---

## 2. 5 Strategi Universal untuk Hasil AI Maksimal

1. **Spec-First, Code Later (Planning Mode)**:
   * Jangan minta output final sekaligus untuk tugas kompleks.
   * Minta AI membuat outline rencana & analisis edge case terlebih dahulu $\rightarrow$ Review/Koreksi $\rightarrow$ Eksekusi bertahap.
2. **Few-Shot Grounding (Golden Example)**:
   * 1 contoh file/kode nyata jauh lebih efektif mengunci format dibanding 10 paragraf penjelasan teks.
3. **Tingkatkan *Signal-to-Noise Ratio***:
   * Jangan dump 500 baris log terminal jika hanya 5 baris stack trace yang relevan. Buang log dependency/instalasi yang tidak terkait.
4. **Output Contract & Negative Constraints**:
   * Tentukan format baku (misal schema JSON / tabel kolom pasti).
   * Berikan larangan tegas (*"Jangan buat test case pagination"*, *"Jangan ubah method X"*).
5. **Agentic Feedback Loop**:
   * Masukkan AI ke dalam siklus: $\text{Generate} \rightarrow \text{Test/Run} \rightarrow \text{Feed Error Log} \rightarrow \text{Fix}$.

---

## 3. Best Practice Workflow QA (Level 10/10)

Alur kerja optimal mengombinasikan AI dengan dokumentasi yang sudah ada di Obsidian:

### A. Pembuatan Test Case (Tanpa Redundansi Upload Template)
Jangan meminta AI menebak atau mengekstrak template dari file Excel di setiap sesi chat baru. Manfaatkan aturan yang sudah terkunci di Obsidian:
* Format 7 kolom baku: [[01 - Format & Styling]]
* Alur Bisnis (CRUD) & Standar Judul Awalan "Me-": [[02 - Alur Bisnis & Judul]]
* Konsistensi nomor Steps = Expected: [[03 - Steps & Expected]]
* Larangan pagination & UI-only test: [[04 - Aturan Khusus Fitur]]

> **Template Prompt Cepat untuk Test Case:**
> ```text
> Buatkan Test Case untuk fitur: [Nama Fitur / Lampirkan Screenshot UI].
> Ikuti standar baku:
> 1. Gunakan 7 kolom: Module, Sub Menu, Test Case Title, Description, Priority, Steps, Expected Results.
> 2. Urutan skenario wajib alur bisnis (Buka -> Tampil -> Search -> Filter -> Add -> Edit -> Delete -> Export).
> 3. Judul gunakan kata kerja aktif 'Me-'.
> 4. Pastikan jumlah nomor Steps = jumlah nomor Expected Results (1:1).
> 5. DILARANG membuat TC untuk pagination, hover, dan styling UI.
> ```

---

### B. Pelaporan Bug / Issue Report: *UI + DevTools Context*
Screenshot UI hanya menampilkan **gejala** (misal tombol loading terus). Developer membutuhkan **akar masalah**.

* **Kombinasi Konteks Ideal:**
  1. Screenshot UI area yang bermasalah.
  2. Screenshot / Copy text dari **DevTools (F12) $\rightarrow$ Tab Console** (jika ada error JavaScript).
  3. Screenshot / Copy response dari **DevTools (F12) $\rightarrow$ Tab Network** (payload request, status code HTTP 4xx/5xx, respons JSON error).

* **Format Output Laporan Bug yang Dihasilkan AI:**
  ```markdown
  ### [BUG] <Judul Singkat & Jelas>
  - **Module / Fitur**: <Nama Modul>
  - **Environment**: <Staging / Browser Chrome / OS>
  - **Severity / Priority**: <Critical / High / Medium>
  
  #### Steps to Reproduce (STR):
  1. Masuk ke halaman X.
  2. Isi form dengan kondisi Y.
  3. Klik button Simpan.
  
  #### Actual Result:
  Sistem menampilkan loading terus menerus dan data tidak tersimpan.
  
  #### Expected Result:
  Muncul notifikasi sukses dan data baru tampil pada tabel list.
  
  #### Technical Evidence & Context:
  - **API Endpoint**: `POST /api/v1/resource/create`
  - **Status Code**: `500 Internal Server Error`
  - **Error Payload**: `{"message": "Column 'user_id' cannot be null"}`
  - **Screenshot**: `[Lampiran UI & Network]`
  ```

---

### C. Alur Retest & Verification Tracker
Saat melakukan retest, jangan hanya mengirimkan screenshot tanpa konteks perubahan. Gunakan format matriks perbandingan:

| Issue ID | Judul Bug | Status Awal | Bukti Awal | Status Retest | Bukti Retest | Catatan QA |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| BUG-001 | Gagal export data filter | Failed / Open | `[error_network.png]` | **Passed / Closed** | `[retest_success.png]` | File berhasil terdownload sesuai parameter filter |

---

## 4. Matriks Transformasi Workflow

| Aspek | Alur Konvensional (8/10) | Alur Best Practice Context-Driven (10/10) |
| :--- | :--- | :--- |
| **Template TC** | Upload ulang file Excel contoh tiap chat baru. | Template dikunci permanen via aturan prompt / Obsidian; AI langsung fokus ke logika bisnis. |
| **Bug Report** | Screenshot UI + ketik manual deskripsi error. | Screenshot UI + DevTools Network (API payload & status) + Console error. |
| **Kualitas TC** | Sering ada langkah yang tidak 1:1 dengan expected result. | Divalidasi otomatis dengan *Quality Checklist* sebelum output final disajikan. |
| **Retest** | Kirim screenshot lepas ke chat. | Update langsung ke tabel matriks status retest terstruktur. |

---
*Terkait:*
- [[00 - Index Masterclass QA]]
- [[01 - Format & Styling]]
- [[02 - Alur Bisnis & Judul]]
- [[03 - Steps & Expected]]
- [[04 - Aturan Khusus Fitur]]
- [[02 - Arsitektur Otomasi Dokumen Hasil Uji (GDrive & Python)]]
- [[10 - Tips Praktis & Troubleshooting Automation]]
