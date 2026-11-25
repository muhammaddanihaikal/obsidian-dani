# Syarat Locator — dari Muhammad (23 Nov 2026, via WhatsApp)

## Pembatasan scope (23 Nov 2026, sebelum tidur)
- Locator + test automation malam ini: ambil yang PENTING saja; elemen/test tidak penting
  dan tidak mengganggu proses bisnis di-skip dulu.
- Cakupan minimal wajib: **CRUD, Filter, Search** pada Aset Baru + Approval Aset Baru.
- Di luar itu hanya kalau kritis untuk alur utama.
- Audit TC tetap perbandingan PENUH (tidak dibatasi scope ini).

- Cari locator sampai dapat dan PASTIKAN benar (tahan banting/robust).
- Prioritas strategi (pengamatan Muhammad: kebanyakan elemen aplikasi memakai #id / data-testid):
  1. `#id`
  2. `[data-testid="..."]`
  3. Locator semantik (role / text / label / placeholder) sebagai cadangan
- Setiap locator wajib diverifikasi: benar-benar menunjuk elemen yang dimaksud dan UNIK (tidak ambigu, count = 1).
- Catat strategi yang dipakai per elemen di laporan locator.
- Catatan: prioritas ini berbeda dari AGENTS.md repo bsn-automation (role-first).
  Instruksi langsung Muhammad untuk aplikasi ini yang berlaku malam ini;
  deviasi ini ditandai di laporan pagi agar Muhammad bisa memutuskan apakah standar repo perlu diperbarui.
