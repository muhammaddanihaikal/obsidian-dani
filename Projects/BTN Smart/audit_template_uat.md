# Audit Template Dokumen Hasil Uji (UAT) BTN SMART

Tanggal audit: 15 Oktober 2026
Terakhir diupdate: 15 Oktober 2026, pukul 09:43 WIB (02:43 UTC)

## File yang diaudit

| Dokumen | File | Jumlah TC | Jumlah modul |
|---|---|---|---|
| UAT Web | Dokumen_Hasil_Uji_Web_0123f7.docx | 865 | 79 |
| UAT Mobile | Dokumen_Hasil_Uji_Mobile_1.docx | 260 | 20 |

## Hasil ringkas

**Belum sesuai template.** Dari 7 kriteria, hanya kriteria 7 (jumlah TC dan status) yang sepenuhnya sesuai di kedua dokumen. Kriteria lain punya temuan di web, mobile, atau keduanya.

## Ringkasan per kriteria

| No | Kriteria | Web | Mobile | Status |
|---|---|---|---|---|
| 1 | Satu tabel utuh per modul | 865 tabel untuk 79 modul (setiap TC dipisah) | 204 tabel: 200 tabel untuk 1 TC, 4 tabel untuk banyak TC | Tidak sesuai |
| 1 | Tabel rata tengah (jc="center") | Tidak di-set di semua tabel (865/865) | Tidak di-set di semua tabel (204/204) | Tidak sesuai |
| 2 | Header biru #2C5293, teks putih bold | Sesuai (79/79) | Sesuai (20/20) | Sesuai |
| 2 | Kolom No dan Nama rata tengah di header | Sesuai | Sesuai | Sesuai |
| 2 | Repeat header (tblHeader) | Tidak ada (0/79) | Tidak ada (0/20) | Tidak sesuai |
| 3 | Judul TC abu-abu #D0CECE, No rata tengah | Sesuai | Sesuai | Sesuai |
| 3 | Judul TC rata kiri dengan spasi awal | 18 TC tanpa spasi awal | Sesuai | Tidak sesuai (web) |
| 3 | Judul TC keep_with_next | 27 TC tidak ada | Sesuai | Tidak sesuai (web) |
| 3 | Judul TC Arial 10pt hitam (eksplisit) | 20 TC font tidak di-set | Sesuai | Tidak sesuai (web) |
| 4 | Kolom 0 baris screenshot vMerge | 18 TC tidak vMerge | Sesuai | Tidak sesuai (web) |
| 4 | Gambar screenshot rata tengah | 23 TC tidak rata tengah | Sesuai | Tidak sesuai (web) |
| 4 | Tidak ada paragraf kosong di atas gambar | 16 TC ada paragraf kosong | Sesuai | Tidak sesuai (web) |
| 4 | Tidak ada trHeight paksa di baris screenshot | 89 TC ada trHeight | 2 TC ada trHeight | Tidak sesuai |
| 5 | Kolom 0 baris hasil vMerge | 11 TC tidak vMerge | Sesuai | Tidak sesuai (web) |
| 5 | Label hasil hitam bold, vAlign center, tanpa trHeight | Sesuai | Sesuai | Sesuai |
| 5 | Narasi dan tag [Success] biru #2C5293 non-bold | 100 TC hitam (41, 42, 46, 51, 52, 53) | Sesuai | Tidak sesuai (web) |
| 6 | Judul modul "N. Modul Nama" | Sesuai (79/79) | Sesuai (20/20) | Sesuai |
| 6 | Tidak ada paragraf kosong sebelum tabel | Sesuai | Sesuai | Sesuai |
| 6 | Judul modul keep_with_next | 8 modul tidak (72 s/d 79) | Sesuai | Tidak sesuai (web) |
| 6 | Logo header wrapNone | Sesuai | Sesuai | Sesuai |
| 7 | Jumlah TC (web 865, mobile 260) | 865 | 260 | Sesuai |
| 7 | Semua TC berstatus [Success] | 865/865 | 260/260 | Sesuai |

## Daftar temuan per TC

### Kriteria 1: tabel per modul dan alignment tabel

- **Web:** setiap TC dibuat sebagai tabel sendiri, jadi 865 tabel untuk 79 modul. Ini memunculkan border ganda di tiap pemisahan. Semua tabel juga belum di-set rata tengah.
- **Mobile:** 200 dari 204 tabel hanya berisi 1 TC. Modul masih terpecah. Semua tabel juga belum di-set rata tengah.

### Kriteria 2: baris header modul

- Warna dan font sudah sesuai di kedua dokumen.
- Repeat header (tblHeader) belum dipasang di semua baris header modul, baik web (79) maupun mobile (20).

### Kriteria 3: judul TC (web)

- Tanpa spasi awal: 34.2 sampai 34.13 (12 TC), 35.2 sampai 35.7 (6 TC).
- Tanpa keep_with_next: 26.14 sampai 26.22 (9 TC), 34.2 sampai 34.13 (12 TC), 35.2 sampai 35.7 (6 TC).
- Font tidak di-set eksplisit: 34.2 sampai 34.13, 35.2 sampai 35.7, 42.1 sampai 42.2 (20 TC).

### Kriteria 4: baris screenshot (web)

- Kolom 0 tidak vMerge: 16.1 sampai 16.10, 26.7, 57.11 sampai 57.13, 57.19 sampai 57.20, 59.4, 63.4 (18 TC).
- Gambar tidak rata tengah: 17.8, 34.13, 35.7, 42.1, 46.3 sampai 46.4, 46.6, 55.6 sampai 55.7, 69.9 sampai 69.17, 79.1 sampai 79.5 (23 TC).
- Paragraf kosong di atas gambar: 16.4, 16.6, 16.8 sampai 16.10, 66.1 sampai 66.7, 68.1 sampai 68.4 (16 TC).
- trHeight paksa: web di 89 TC (antara lain 2.36, 16.4, 16.6, 16.8 sampai 16.10, 17.4 sampai 17.5, 18.9, 21.1 sampai 21.3, 21.5 sampai 21.6, 22.2 sampai 22.18, 23.1 sampai 23.7, 27.6, 36.2 sampai 36.6, 41.1 sampai 41.15, 41.17 sampai 41.25, 42.1 sampai 42.11, 43.2 sampai 43.8, 46.5, 50.4, 56.6). Mobile di 20.3 dan 20.8.

### Kriteria 5: baris hasil yang diharapkan (web)

- Kolom 0 tidak vMerge: 12.9, 13.14, 13.16, 26.7, 57.11 sampai 57.13, 57.19 sampai 57.20, 59.4, 63.4 (11 TC).
- Narasi dan tag [Success] tidak biru: 41.1 sampai 41.25, 42.3, 46.5, 51.1 sampai 51.9, 52.1 sampai 52.33, 53.1 sampai 53.31 (100 TC).

### Kriteria 6: judul modul (web)

- keep_with_next belum ada di modul 72 sampai 79 (8 modul).

### Kriteria 7: jumlah dan status

- Web 865 TC dan mobile 260 TC sudah sesuai.
- Semua TC berstatus [Success].

## Catatan

- Modul 41, 42, 46, 51, 52, dan 53 masih dalam status ditahan untuk diskusi tim. Formatnya juga menyimpang di bagian narasi dan tag (kriteria 5), dan sebagian punya trHeight paksa (kriteria 4).
- Screenshot belum lengkap: web 3 TC (41.16, 51.7, 52.2), mobile 5 TC (2.16, 8.11, 12.6, 12.20, 13.9). Ini di luar kriteria template, tapi perlu dicatat.
- Logo header menggunakan wrapNone di kedua dokumen, sehingga judul modul tidak terpotong logo.

## Rekomendasi perbaikan

1. **Gabungkan TC per modul menjadi satu tabel** di web (865 tabel menjadi 79) dan mobile (204 tabel menjadi 20). Setelah itu set tabel ke rata tengah.
2. **Pasang repeat header** (tblHeader) di baris header modul, web dan mobile.
3. **Web, judul TC:** tambahkan spasi awal, pasang keep_with_next, dan set font Arial 10pt hitam eksplisit di 34.2 sampai 34.13, 35.2 sampai 35.7, 26.14 sampai 26.22, dan 42.1 sampai 42.2.
4. **Web, baris screenshot:** tambahkan vMerge di kolom 0 pada 16.1 sampai 16.10 dan TC lain yang disebut di atas. Rata tengahkan gambar pada TC yang disebut di atas. Hapus paragraf kosong di atas gambar pada 16.4, 16.6, 16.8 sampai 16.10, 66.1 sampai 66.7, dan 68.1 sampai 68.4. Hapus trHeight paksa pada 89 TC web dan 2 TC mobile (20.3 dan 20.8).
5. **Web, baris hasil:** tambahkan vMerge di kolom 0 pada 11 TC yang disebut di atas. Ubah narasi dan tag [Success] menjadi biru #2C5293 non-bold pada 100 TC. Ini paling banyak ada di modul 41 sampai 53, jadi tunggu keputusan tim untuk 6 modul yang ditahan.
6. **Web, modul 72 sampai 79:** pasang keep_with_next pada judul modul.
7. **Lengkapi screenshot:** web 3 TC, mobile 5 TC.
