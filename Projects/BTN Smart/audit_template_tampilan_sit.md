# Audit Template Tampilan SIT (BTN SMART)

Tanggal audit: 15 Oktober 2026
Terakhir diupdate: 15 Oktober 2026, pukul 19:47 WIB (12:47 UTC)

## File yang diaudit

| Dokumen | File | Jumlah TC | Jumlah modul |
|---|---|---|---|
| SIT Web | SIT_BTN_SMART_Web.docx | 865 | 79 |
| SIT Mobile | SIT_BTN_SMART_Mobile.docx | 260 | 20 |

## Hasil ringkas

**Belum 100% sesuai template.** Ada 4 hal yang perlu diperbaiki di kedua dokumen, dan 1 hal tambahan khusus di web.

## Hasil per kriteria

| No | Kriteria | Web | Mobile |
|---|---|---|---|
| 1 | Penamaan judul "N. Modul Nama" | Sesuai (79/79) | Sesuai (20/20) |
| 2 | Tidak ada paragraf kosong di bawah judul modul | Sesuai | Sesuai |
| 3 | Judul modul tidak terpotong logo header | Tidak terdeteksi masalah* | Tidak terdeteksi masalah* |
| 4 | Tabel rata tengah (Center) | **Tidak sesuai**: tidak di-set, default kiri | **Tidak sesuai**: rata kiri |
| 5 | Kolom "No" rata tengah | **Tidak sesuai**: 29 baris di modul 47 sampai 50 belum rata tengah | Sesuai (260/260) |
| 6 | Kolom "Test Status" rata tengah | Sesuai (865/865) | Sesuai (260/260) |
| 7 | Header tabel biru tua, teks putih bold | **Tidak sesuai**: biru muda (BCD6ED), teks hitam | **Tidak sesuai**: biru muda (BCD6ED), teks hitam |
| 8 | Jumlah Script di header | Sesuai (865) | Sesuai (260) |
| 9 | Estimasi Waktu terisi | Terisi, tapi **teks muncul dobel** | Terisi, tapi **teks muncul dobel** |
| 10 | Last Update 09 Oktober 2026 | Sesuai | Sesuai |
| 11 | Semua baris berstatus P, tidak ada baris kosong | Sesuai (865/865) | Sesuai (260/260) |

\*Dicek dari struktur file dan render LibreOffice. Sebaiknya dicek langsung di Word.

## Yang perlu diperbaiki

1. **Tabel rata tengah (kriteria 4)**: set alignment tabel ke Center di semua modul, web dan mobile.
2. **Header tabel (kriteria 7)**: ubah warna header menjadi biru tua dengan teks putih bold, di semua modul, web dan mobile.
3. **Kolom No di web (kriteria 5)**: rata tengahkan kolom No di modul 47, 48, 49, dan 50 (29 baris).
4. **Estimasi dobel (kriteria 9)**: hapus paragraf estimasi yang dobel di header, web dan mobile. Saat ini teks "24 September 2026 s/d 09 Oktober 2026" muncul dua kali.

## Catatan tambahan

- Format judul modul di web dan mobile belum seragam. Di web judul modul tidak punya rata kiri atau kanan yang di-set, sedangkan di mobile rata kiri. Template tidak mengatur ini secara eksplisit, jadi perlu keputusan tim.
- Pengecekan logo header dan tampilan halaman depan sebaiknya diverifikasi di Microsoft Word, karena render LibreOffice bisa berbeda.
