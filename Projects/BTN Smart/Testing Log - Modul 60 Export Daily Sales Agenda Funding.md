# Testing Log - Modul 60 (Report Funding: Daily Sales Agenda Export Issue)

Catatan issue fitur export pada modul **Report Funding → Daily Sales Agenda** (TC 60.8, 60.13, 60.18, 60.23).

---

## 📌 Informasi Modul

* **Modul**: Report Funding → Daily Sales Agenda
* **Menu Terkait**:
  * Tab Prospek Masuk (TC 60.8)
  * Tab Prospek Closing (TC 60.13)
  * Tab Prospek Referal (TC 60.18)
  * Tab Prospek Referal Closing (TC 60.23)
* **Status Pengujian**: ⚠️ Issue / Pending Screenshot

---

## 🔍 Detail Masalah / Bug Utama

### Klik Tombol Export Belum Terhubung ke Export Center (❌ Masih Reproduce)
* **Kondisi Aktual**:
  Saat user menekan button **Export** di pojok kanan atas tabel pada setiap tab Daily Sales Agenda, sistem belum mengarahkan atau membuka panel **Download Export / Export Center**.
* **Ekspektasi**:
  1. Tombol Export memicu proses generate data.
  2. Muncul notifikasi atau panel riwayat Download Export (Export Center) untuk mengunduh file `.xlsx`.
* **Dampak**:
  Screenshot hasil uji untuk 4 Test Case Export di bawah ini dikosongkan sementara hingga perbaikan selesai:
  1. `60.8 Mengekspor data tab Prospek Masuk`
  2. `60.13 Mengekspor data tab Prospek Closing`
  3. `60.18 Mengekspor data tab Prospek Referal`
  4. `60.23 Mengekspor data tab Prospek Referal Closing`
