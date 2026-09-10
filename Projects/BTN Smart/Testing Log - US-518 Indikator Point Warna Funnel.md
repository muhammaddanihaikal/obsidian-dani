# Testing Log - US-518 (Indikator Point Warna Personal Funnel)

Catatan pengetesan tiket **US-518** pada modul **Report Lending → Personal Funnel**.

---

## 📌 Informasi Tiket

* **Tiket ID**: US-518 (Bug)
* **Judul**: [BUG] | Indikator Point Warna di Personal Funnel masih belum sesuai dengan Pengaturan Funnel
* **Modul**: Report Lending → Personal Funnel & Pengaturan Funnel Lending
* **Status**: **DONE / PASSED ✅**
* **Tanggal Re-test**: 10 September 2026

---

## 🔍 Ringkasan & Solusi

1. **Masalah Awal**: Kolom Point di Personal Funnel tidak memiliki warna indikator performa (polos/putih), dan sempat muncul salah pewarnaan akibat operator pada menu *Pengaturan Funnel* terpasang >= 50% untuk Merah.
2. **Setup Pengaturan Funnel yang Benar**:
   * **Kondisi 1 (Merah 🔴)**: Nilai Performa <= 49 %
   * **Kondisi 2 (Kuning 🟡)**: Nilai Performa >= 50 % dan <= 80 %
   * **Kondisi 3 (Hijau 🟢)**: Nilai Performa >= 81 % dan <= 100 %
3. **Hasil Validasi**:
   * Seluruh tab (**Semua**, **Non PKS**, **PKS**) terbukti membaca aturan warna secara dinamis dan presisi sesuai % pencapaian baris dan rata-rata point.

---

## 💬 Draft Komentar Huly

`markdown
**Update Re-test (10 Sep 2026): DONE ✅**

Indikator warna point di Personal Funnel sudah sesuai dengan Pengaturan Funnel:
- Nilai <= 49% tampil **Merah** 🔴 (capaian 0.00%).
- Nilai 50% - 80% tampil **Kuning** 🟡 (capaian 50.00%).
- Nilai >= 81% tampil **Hijau** 🟢 (capaian 100.00% & rata-rata point 97.50%).

**Bukti Pengaturan:**
- Pengaturan Indikator Funnel: [https://files.catbox.moe/in9oge.png](https://files.catbox.moe/in9oge.png)

**Bukti Hasil Personal Funnel:**
- Tab Semua (Atas): [https://files.catbox.moe/5em7vl.png](https://files.catbox.moe/5em7vl.png)
- Tab Semua (Bawah): [https://files.catbox.moe/kf4l6t.png](https://files.catbox.moe/kf4l6t.png)
- Tab Non PKS: [https://files.catbox.moe/3zc9zq.png](https://files.catbox.moe/3zc9zq.png)
- Tab PKS: [https://files.catbox.moe/u3i5l6.png](https://files.catbox.moe/u3i5l6.png)
`

---

## 📎 Bukti Evidence Links (Permanen - Catbox)

* **Pengaturan Indikator Funnel**: [https://files.catbox.moe/in9oge.png](https://files.catbox.moe/in9oge.png)
* **Personal Funnel - Tab Semua (Atas)**: [https://files.catbox.moe/5em7vl.png](https://files.catbox.moe/5em7vl.png)
* **Personal Funnel - Tab Semua (Bawah)**: [https://files.catbox.moe/kf4l6t.png](https://files.catbox.moe/kf4l6t.png)
* **Personal Funnel - Tab Non PKS**: [https://files.catbox.moe/3zc9zq.png](https://files.catbox.moe/3zc9zq.png)
* **Personal Funnel - Tab PKS**: [https://files.catbox.moe/u3i5l6.png](https://files.catbox.moe/u3i5l6.png)