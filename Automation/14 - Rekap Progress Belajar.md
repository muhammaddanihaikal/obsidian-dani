# Rekap Progress Belajar QA Automation (Dani)

Dokumen ini melacak perjalanan belajar *QA Automation* menggunakan Playwright dan Pytest.

### 📅 31 Agustus 2026
**Fokus: Konsep Dasar Framework & UI Automation**
- **Page Object Model (POM):** Memisahkan elemen web (locator) dan logika test ke file terpisah agar kode rapi dan mudah dirawat.
- **Pytest Fixtures:** Belajar membuat fungsi penolong (setup) sebelum test jalan (seperti `browser`, `page`, dan `context`).
- **Locator & Assertion:** Menemukan elemen pakai `get_by_text`, `get_by_role` serta memvalidasi hasil dengan pola AAA (*Arrange, Act, Assert*).
- **Waiting Strategy:** Meninggalkan *hard sleep* (timeout mati) dan beralih ke *dynamic wait* bawaan Playwright.
- **Data-Driven Testing (DDT):** Mengeluarkan data (seperti *username* dan *password*) ke file eksternal (`user_data.json`) dan membuat `data_factory` (faker) agar test lebih dinamis.

### 📅 1 September 2026
**Fokus: Troubleshooting & Maintenance**
- **Mengatasi Error Element:** Belajar cara *debug* elemen yang tidak ketemu atau bermasalah saat diklik.
- **Troubleshooting Database:** Belajar *fixing* masalah database *backend* secara langsung (menyelesaikan isu di *container* PostgreSQL) untuk melancarkan environment lokal OrangeHRM.

### 📅 3 Agustus 2026
**Fokus: Optimasi Kecepatan (Authentication State)**
- **Global Login (Login Cuma 1x):** Menghindari login berulang di tiap test.
- **Simpan Cookies:** Menggunakan `context.storage_state` untuk menyimpan sesi otentikasi admin ke dalam folder `.auth/admin_state.json`.
- **Hasil:** Waktu pengujian terpangkas drastis karena *robot* bisa langsung lompat ke halaman *Dashboard*.

### 📅 4 September 2026
**Fokus: Kestabilan Test & API Injection (Test Independence)**
- **Test Independence:** Memastikan `test_edit` dan `test_delete` tidak numpang data dari `test_add`.
- **Injeksi Data via API:** Menggunakan `request.post` dan Network Tab DevTools untuk bikin "User Tumbal" secara instan (0.1 detik).
- **Setup & Teardown Pytest:** Memanfaatkan perintah `yield`. (Atas `yield` = Bikin data, Bawah `yield` = Hapus data/Bersih-bersih).
- **Logika Error 404:** Belajar trik QA senior (`if != 404`) agar sistem tidak memberi *error* palsu saat mencoba menghapus user yang sudah terhapus di UI.
- **Frontend State Desync:** Belajar sifat aplikasi React/Vue yang bisa *nge-bug* atau *invalid* bila *input autocomplete* dipaksa mengetik data yang persis sama dengan yang sudah terpilih.
- **Headless Mode:** Menjalankan browser di latar belakang tanpa UI (`HEADLESS = True`) yang sukses menembus 10 UI test hanya dalam 22 detik! 🚀
