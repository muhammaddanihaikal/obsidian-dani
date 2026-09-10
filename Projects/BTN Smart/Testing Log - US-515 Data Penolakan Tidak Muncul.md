# Testing Log - US-515 (Data Actual Menolak Tidak Muncul)

Catatan pengetesan bug **US-515** pada modul **Report Lending → Personal Funnel**.

---

## 📌 Informasi Tiket

* **Tiket ID**: US-515 (Bug)
* **Judul**: [BUG] | Data Actual Menolak Tidak Muncul
* **Modul**: Report Lending → Personal Funnel
* **User / Akun**: report_lending@gmail.com / Batara123!
* **Role**: CLS Non Sub
* **Produk**: Kredit Agunan Rumah (KAR)
* **Filter**: Staging Penolakan, Bulan September, Tahun 2026

---

## 🔍 Ringkasan Masalah

* Di **Lead Qualification** (Staging: Penolakan, KAR, Sep 2026) ada **4 data penolakan** yang muncul.
* Namun di **Report Lending Personal Funnel** tab Non PKS, baris **Penolakan (No. 9)** masih menampilkan nilai **0** (tidak terbaca sama sekali).
* Kesimpulan: Data aktual penolakan dari Lead Qualification tidak nyambung/tidak terbaca di Personal Funnel.

---

## 💬 Draft Komentar Huly (Siap Pakai)

`markdown
**Update Re-test (09 Sep 2026 - 14:00 WIB): STILL FAILED ❌**

Data penolakan di Lead Qualification ada **4 data** (KAR, September 2026),
tapi di Personal Funnel baris **Penolakan** masih **0** (tidak terbaca).

**Bukti:**
- Lead Qualification (4 data penolakan): [https://files.catbox.moe/6xye3l.png](https://files.catbox.moe/6xye3l.png)
- Personal Funnel (Penolakan = 0): [https://files.catbox.moe/x32lk5.png](https://files.catbox.moe/x32lk5.png)
`

---

## 📎 Bukti / Evidence Links

* **Lead Qualification - 4 Data Penolakan**: [https://files.catbox.moe/6xye3l.png](https://files.catbox.moe/6xye3l.png)
* **Personal Funnel - Penolakan = 0**: [https://files.catbox.moe/x32lk5.png](https://files.catbox.moe/x32lk5.png)