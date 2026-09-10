# Testing Log - US-512 (Pengecekan Flow PBO Untuk Non Banking)

Catatan klarifikasi alur bisnis dan tiket **US-512** pada modul **Report Funding → Personal Funnel**.

---

## 📌 Informasi Tiket

* **Tiket ID**: US-512 (Bug / Clarification)
* **Judul**: [BUG] | Pengecekan Flow PBO Untuk Non Banking
* **Modul**: Report Funding → Personal Funnel
* **User Role**: Sales / PBO
* **Pelapor**: Mukhlis Rifai

---

## 🔍 Ringkasan Masalah

1. Di produk **Non-Banking** (misal Bancassurance / Asuransi), proses closing langsung ke Staging 7 melalui approval atasan saja (tanpa input rekening).
2. Di sistem tidak ada alur maupun tombol penginputan **Top Up** untuk produk Non-Banking.
3. Namun di tabel Personal Funnel, baris **NOA Top Up (Bobot 10%)** dan **Posisi** tetap ditampilkan dengan nilai 0.
4. Akibatnya, nilai sales otomatis kehilangan potensi 10% (poin akhir anjlok jadi merah/0,00%).

---

## 💬 Draft Komentar Huly untuk Dev / PO

`markdown
**Konfirmasi Flow Non-Banking (US-512):**

Di produk Non-Banking kan alurnya langsung closing via approve atasan (tanpa rekening & tidak ada fitur Top Up).

Tapi di tabel, baris **NOA Top Up (Bobot 10%)** dan **Posisi** tetap muncul dengan nilai 0, jadi poin sales otomatis rugi 10%.

**Pertanyaan:**
1. Apakah baris **NOA Top Up & Posisi** untuk Non-Banking seharusnya **dihapus/di-hide** dari tabel?
2. Atau sebenarnya ada flow penginputan Top Up khusus Non-Banking yang mau dibuat?

**Bukti:**
- Screenshot: [https://files.catbox.moe/5nrke2.png](https://files.catbox.moe/5nrke2.png)
`

---

## 📎 Bukti / Evidence Link

* **Screenshot Funnel Non-Banking (Kotak Merah di NOA Top Up & Posisi)**: [https://files.catbox.moe/5nrke2.png](https://files.catbox.moe/5nrke2.png)