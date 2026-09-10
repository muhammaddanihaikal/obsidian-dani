# Testing Log - US-513 (Report Funding: Personal Funnel Export)

Catatan pengetesan dan validasi bug untuk tiket **US-513** pada modul **Report Funding → Personal Funnel**.

---

## 📌 Informasi Tiket

* **Tiket ID**: US-513 (Bug)
* **Judul**: [BUG] | Di data Export Data Nilai Rata2 Belum benar / tidak sesuai dengan di web
* **Modul**: Report Funding → Personal Funnel
* **User / Akun**: report_funding_pbo@gmail.com / Batara123!
* **Environment**: Sales / Staging
* **Filter Digunakan**:
  * Bisnis Unit: Priority Banking Office
  * Fee Based: Banking
  * Produk: Mobile Banking
  * Bulan: Agustus
  * Tahun: 2026

---

## 🔍 Detail 2 Masalah / Bug Utama

### 1. Nilai Rata-Rata Point di File Export Beda / Salah Hitung (❌ Masih Reproduce)
* **Tampilan Web**: 88,50% | Kinerja: ★★★
* **Hasil Export Excel**: Masih 11,06% | Kinerja: ★☆☆
* **Root Cause**:
  * Total akumulasi point dari semua baris adalah 88,5% (10 + 2 + 1,5 + 5 + 10 + 50 + 10 = 88,5%).
  * Developer keliru membagi total point tersebut dengan jumlah baris (8 baris):
    88,5% / 8 = 11,0625%
  * *Padahal nilai point per staging sudah weighted (bobot × pencapaian), jadi cukup dijumlahkan saja, tidak boleh dibagi jumlah baris lagi.* Karena nilainya anjlok ke 11,06%, rating bintang kinerja otomatis turun jadi bintang 1 (★☆☆).

### 2. Header / Judul Excel Masih Menggunakan ID Unit (❌ Masih Reproduce)
* **Aktual Hasil Export**: Personal Funnel - 5 - August 2026
* **Ekspektasi**: Menggunakan nama unitnya: Personal Funnel - Priority Banking Office - August 2026

---

## 📋 Draft Komentar untuk Huly (Siap Pakai)

Tinggal salin blok di bawah ini saat mau komentar/update di Huly:

`markdown
**Update Re-test (09 Sep 2026 - 13:15 WIB): STILL FAILED ❌**

1. **Rata-Rata Point di Excel Masih Salah**
- Web: 88,50% (★★★)
- Excel: Masih 11,06% (★☆☆)
*(Catatan: Total point 88,5% masih keliru dibagi 8 baris).*

2. **Header Excel Masih Pakai ID Unit**
- Aktual: Personal Funnel - 5 - August 2026 (angka 5 masih ID, belum nama unit).

**Bukti:**
- Screenshot Excel: [https://files.catbox.moe/fco6fv.png](https://files.catbox.moe/fco6fv.png)
- Screenshot Web: [https://files.catbox.moe/4ylmcc.png](https://files.catbox.moe/4ylmcc.png)
- File Excel: [https://gofile.io/d/xqUkL3yR](https://gofile.io/d/xqUkL3yR)
`

---

## 📎 Bukti / Evidence Links

* **Screenshot Error Excel (Box Merah)**: [https://files.catbox.moe/fco6fv.png](https://files.catbox.moe/fco6fv.png)
* **Screenshot Web (88,50%)**: [https://files.catbox.moe/4ylmcc.png](https://files.catbox.moe/4ylmcc.png)
* **Screenshot Filter**: [https://files.catbox.moe/u4efkp.png](https://files.catbox.moe/u4efkp.png)
* **File Excel Export (Terbaru 09/09 13:15 WIB)**: [https://gofile.io/d/xqUkL3yR](https://gofile.io/d/xqUkL3yR)
* *(Backup Filebin)*: [https://filebin.net/btnsmart-us513](https://filebin.net/btnsmart-us513)