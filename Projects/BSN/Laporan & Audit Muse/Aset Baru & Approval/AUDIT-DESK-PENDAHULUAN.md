# Audit TC Aset Baru + Approval Aset Baru — Analisis Desk (PENDAHULUAN)

> Status: analisis awal dari TC (Google Sheets SIT "Script Internal", diekstrak 23 Nov 2026)
> vs temuan eksplorasi 23 Nov 2026. **Belum final** — setiap poin wajib dikonfirmasi pada
> eksplorasi ulang sebelum masuk laporan pagi.
> Sumber TC: `tc-aset-baru-approval.json` (42 TC: Aset Baru baris 190–209, Approval baris 250–271).

## Aset Baru (20 TC)

| Baris | TC | Penilaian awal | Catatan |
|---|---|---|---|
| 190 | Membuka halaman Aset Baru | Sesuai | Halaman + summary card + tabel tampil. Bug angka card Stok (BSN_I-169) adalah bug aplikasi, bukan kesalahan TC — TC tidak memverifikasi nilai card. |
| 191 | Memilih tab status aset | Perlu verifikasi ulang | Tab bekerja, tapi label tab menggabungkan status ("NONAKTIF/DRAF 14" = Draf 3 + Menunggu 11) dan ada tab "Stok" yang menampilkan 0 — cocokkan per tab. |
| 192 | Search keyword valid | Perlu verifikasi ulang | Search kode bekerja (MKSS-10013 ketemu). Skenario menyebut "nama aset" — padahal tidak ada nama properti bebas di UI; yang searchable tampaknya kode. Cek juga pencarian lokasi. |
| 193 | Search keyword tidak valid | Perlu verifikasi ulang | Cek teks persis keterangan tabel kosong di UI aktual. |
| 194 | Filter data sesuai | Perlu verifikasi ulang | Panel filter ada (kode, status publish, status verifikasi, developer, klaster). Uji hasil aktual per kombinasi. |
| 195 | Filter data tidak sesuai | Perlu verifikasi ulang | Idem — hasil kosong + keterangan. |
| 196 | Reset filter | Perlu verifikasi ulang | Reset di Aset Baru belum terkonfirmasi (yang bermasalah adalah Reset di Approval). |
| 197 | Toggle status publish | Tidak dapat diverifikasi penuh | Toggle = mengubah data existing (dilarang). Hanya bisa diuji pada aset uji sendiri yang sudah Terverifikasi; MKSS-10013 masih Draf. Catat sebagai keterbatasan audit. |
| 198 | Ekspor rekap data | Perlu verifikasi ulang | Belum pernah diuji. Cocokkan alur aktual (Unduh Rekap → titik tiga → ikon download) dengan UI; download bersifat read-only, aman diuji. |
| 199 | Wizard Step 1 Informasi | Sesuai | Terbukti saat Create MKSS-10013 (dengan catatan: tidak ada field nama properti bebas; nama masuk Deskripsi). |
| 200 | Wizard Step 2 Harga | Sesuai, 1 catatan | Kalkulasi DP tampil; temuan kemarin: DP di bawah minimum di-clamp diam-diam — tidak ada TC validasi untuk ini. Promo coret + harga normal belum pernah diuji. |
| 201 | Wizard Step 3 Galeri Foto | Perlu verifikasi ulang | Kemarin hanya upload 1 foto dummy; skenario TC: 4–10 foto + kategori. Uji sesuai skenario. |
| 202 | Wizard Step 4 Legalitas | Sesuai, 1 catatan | Alur centang + unggah bekerja. Catatan: temuan SHM tercentang otomatis (ditahan, belum terkonfirmasi) berkaitan dengan step ini. |
| 203 | Wizard Step 5 Lokasi & GIS | Sesuai | Alamat + wilayah + kode pos + titik peta terisi saat Create. |
| 204 | Tambah destinasi strategis Step 5 | Belum terverifikasi | Belum pernah diuji kemarin — wajib diuji pada eksplorasi ulang (pada data uji sendiri). |
| 205 | Step 6 Fasilitas + ajukan | Sesuai sebagian | Create sampai Draf terbukti; pengajuan (Simpan dan Ajukan) belum dieksekusi pada MKSS-10013 (keputusan user ditunda) — verifikasi alur tanpa submit final bila memungkinkan. |
| 206 | Simpan sebagai Draft | Sesuai | MKSS-10013 tersimpan sebagai Draf Pengajuan. Catatan: validasi draft lemah (BSN_I-172, stok 0 lolos) — TC data valid tetap sesuai. |
| 207 | Mengubah data aset baru | Sesuai | Edit MKSS-10013 stok 5→7 terbukti dan terverifikasi ulang. |
| 208 | Melihat detail aset baru | Sesuai, cek istilah | Detail tampil dengan 6 tab jangkar. Expected menyebut "akurasi data" dan "riwayat aktivitas" — cocokkan label persis di UI. |
| 209 | Mengajukan pengurangan unit | Sesuai | Formulir pengesahan terkirim; permohonan masuk Approval dengan status Menunggu Verifikasi (stok belum terpotong sebelum approval — sesuai desain). |

## Approval Aset Baru (22 TC)

| Baris | TC | Penilaian awal | Catatan |
|---|---|---|---|
| 250 | Membuka halaman Approval | Sesuai, istilah outdated ringan | UI aktual memakai nama tab "Pengajuan Masuk"; TC menyebut "tab Approval Input Aset". Isi (summary card + daftar) sesuai. |
| 251 | Tab status Approval Input | TC benar — aplikasi gagal | Tab "Disetujui 4" menampilkan 0 baris (BSN_I-173). Expected TC sudah benar; perilaku aplikasi menyimpang. |
| 252 | Search keyword valid | TC benar, catatan cakupan | Search bekerja di tab Pengajuan (JPMS → 1 baris) tetapi bocor mengubah angka tab Pengurangan (BSN_I-173). Skenario "nama aset" perlu dicocokkan — kolom yang tampil adalah kode/developer/proyek. |
| 253 | Search keyword tidak valid | Perlu verifikasi ulang | Cek perilaku + keterangan kosong aktual. |
| 254 | Filter data sesuai | TC benar — aplikasi gagal | Filter Tipe Aset "Rumah" menghasilkan 0 baris padahal 16/16 Rumah (BSN_I-173). |
| 255 | Filter data tidak sesuai | Perlu verifikasi ulang | Dengan bug filter saat ini, hasil kosong juga muncul untuk filter yang sesuai — verifikasi ulang untuk memisahkan. |
| 256 | Reset filter | TC benar — aplikasi gagal | Reset tidak membersihkan tab status aktif (BSN_I-173, kasus terkait). |
| 257 | Setujui dari daftar tabel | Tidak dapat diverifikasi penuh | Tidak boleh approve data existing. Hanya dapat diuji pada pengajuan data uji sendiri (MKSS-10013 belum diajukan). Verifikasi sampai modal konfirmasi saja. |
| 258 | Tolak dari daftar tabel | Tidak dapat diverifikasi penuh | Idem — sampai modal/alasan penolakan saja. |
| 259 | Detail pengajuan | Sesuai, cek istilah | Halaman detail terpisah tampil. Expected menyebut PIC, galeri, spesifikasi, log aktivitas, "akurasi skor kelengkapan data" — cocokkan label aktual. |
| 260 | Detail Lengkap Aset dari Detail Pengajuan | Perlu verifikasi ulang | Keberadaan tombol persis "Detail Lengkap Aset" belum terkonfirmasi kemarin. |
| 261 | Setujui dari Detail Pengajuan | Tidak dapat diverifikasi penuh | Sama seperti 257. |
| 262 | Tolak dari Detail Pengajuan | Tidak dapat diverifikasi penuh | Sama seperti 258. |
| 263 | Membuka tab Approval Pengurangan Unit | Sesuai | Tab tampil: summary card + tabel 2 permohonan. |
| 264 | Tab status Pengurangan Unit | Perlu verifikasi ulang | Belum diuji per tab status kemarin. |
| 265 | Search pengurangan valid | Perlu verifikasi ulang | Search di dalam tab Pengurangan belum diuji (yang terbukti: search tab Pengajuan mengubah count tab ini). |
| 266 | Search pengurangan tidak valid | Perlu verifikasi ulang | — |
| 267 | Filter pengurangan sesuai | Perlu verifikasi ulang | Belum diuji kemarin. |
| 268 | Filter pengurangan tidak sesuai | Perlu verifikasi ulang | — |
| 269 | Reset filter pengurangan | Perlu verifikasi ulang | — |
| 270 | Setujui permohonan pengurangan | Verifikasi terbatas | Data existing tidak boleh di-approve. Permohonan uji sendiri (MKSS-10013) masih PENDING dan keputusan approve-nya ditunda user — verifikasi sampai modal konfirmasi saja. Expected "stok terpotong otomatis" belum terbukti (stok masih 7, riwayat kosong). |
| 271 | Menolak permohonan pengurangan | Verifikasi terbatas | Idem — sampai modal/catatan penolakan saja. |

## Kandidat TC KURANG (fitur/perilaku aplikasi belum ada TC-nya)

1. **Sorting semua kolom** tabel Aset Baru + Approval — tidak ada TC sorting sama sekali; fitur ada dan rusak total (BSN_I-170).
2. **Isi kolom SPESIFIKASI UNIT & JUMLAH UNIT** di daftar Approval — tidak ada TC yang memverifikasi nilai kolom ini (BSN_I-171).
3. **Nilai summary card** (total aset, total nilai, stok unit tersedia) — TC 190 hanya memeriksa halaman tampil, bukan kebenaran angka (BSN_I-169).
4. **File bukti pengurangan dapat dibuka/diunduh** dari tab Pengurangan Unit (BSN_I-174).
5. **Validasi wizard (kasus negatif)**: stok 0 (BSN_I-172), DP di bawah minimum (clamp diam-diam), field wajib kosong — semua TC wizard saat ini positif saja.
6. **Konsistensi angka antar-tab** saat search/filter berjalan (kasus bocor antar-tab, BSN_I-173).
7. **Riwayat pengurangan unit** di halaman Detail Aset setelah pengajuan/approval — belum ada TC.
8. **Mengajukan aset Draf yang sudah tersimpan** (dari Edit/list) menuju Menunggu Verifikasi — TC 205 hanya mencakup pengajuan dari wizard baru.

## Kandidat TC BERLEBIH / OUTDATED

- Istilah tab pada TC 250 ("Approval Input Aset") vs UI aktual ("Pengajuan Masuk") — outdated ringan.
- TC 252 skenario menyebut pencarian "nama aset" — UI tidak menampilkan nama aset sebagai kolom/kriteria yang jelas (yang ada kode, developer & proyek, lokasi).
- TC 198 langkah ekspor menyebut "titik tiga → ikon download" — wajib dicocokkan dengan UI aktual; bila alurnya berbeda, TC outdated.
- TC 260 tombol "Detail Lengkap Aset" — bila tombol persis itu tidak ada, TC outdated.

## Keterbatasan audit (untuk laporan pagi)

- TC aksi persetujuan/publish (197, 257, 258, 261, 262, 270, 271) tidak dieksekusi penuh karena data existing read-only; verifikasi dibatasi sampai tampilan modal konfirmasi.
- Data uji sendiri hanya MKSS-10013 (Draf, stok 7) + 1 pengajuan pengurangan PENDING miliknya.
