---
tags:
  - SIT
  - BSN
  - External
  - QA
  - TestScript
date: 2026-10-27
project: BSN Lelang
platform: External
source_file: SIT_Script_External_-BSN Lelang.docx
total_script: 98
converter: markitdown
---

|  |  |  |
| --- | --- | --- |
| **Application : BSN Lelang** | **Jumlah Script : 98** | **Version :** 1.0 |
| **Modul :**   * **Modul Akun – Daftar Akun** * **Modul Akun – Login** * **Modul Akun – Lupa kata Sandi** * **Modul Beranda – Home Page** * **Modul Beranda – After Search** * **Modul Jenis Angunan** * **Modul Estimasi Lelang** * **Modul Detail Aset – Detail** * **Modul Detail Aset – Favorite** * **Modul Detail Aset – Formulir Pemesanan** * **Modul Detail Aset – Simulasi Pembiayaan** * **Modul Bandingkan** | **Estimasi Jangka Waktu Pengujian :** 1 hari |  |
|  |  |

# Modul Akun - Daftar Akun

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Masuk ke Menu Login | Klik pada Button masuk di Header | Direct user ke menu Login | Direct user ke menu Login | P | - |
| 2 | Melakukan daftar dengan mengisi semua data dengan benar | Klik daftar gratis sekarang - masukan semua data dengan benar - checklis TnC - kemudian klik button daftar sekarang | Berhasil daftar dan masuk ke halaman verifikasi / OTP | Validasi konfirmasi kata sandi tidak sinkron saat input data; submit pendaftaran tidak menampilkan notifikasi berhasil dan gagal redirect ke OTP / login (tertahan di form) | F | Issue: 01 - Validasi Konfirmasi Kata Sandi & 02 - Submit Pendaftaran Gagal Redirect |
| 3 | Melakukan daftar dengan mengosongkan salah satu atau beberapa field | Kosongkan beberapa field lalu klik pada Daftar sekarang | Menampilkan validasi field tidak boleh kosong, gagal direct ke proses selanjutnya | Menampilkan validasi field tidak boleh kosong, gagal direct ke proses selanjutnya | P | - |
| 4 | Melakukan input email dengan data tidak valid | Input field email dengan data tidak valid, contoh dengan email yang tidak terdaftar atau struktur yang tidak valid, contoh "fuji" tanpa bagan "@email" lalu klik Daftar | Menampilkan validasi error handling saat mencoba klik Daftar | Menampilkan validasi error handling saat mencoba klik Daftar | P | - |
| 5 | Melakukan input Kata Sandi kurang dari 8 karakter | Input kata sandi dengan karakter kurang dari 8 | Menampilkan validasi karakter kurang dari 8 | Menampilkan validasi karakter kurang dari 8 | P | - |
| 6 | Melakukan input Kata Sandi dengan tidak sesuai ketentuan penulisan | Input tanpa salah satu karakter khusus, huruf besar, huruf kecil dan angka | Menampilkan validasi kata sandi tidak sesuai ketentuan | Menampilkan validasi kata sandi tidak sesuai ketentuan | P | - |
| 7 | Melakukan klik Daftar tanpa centang bagian TnC | Input data sesuai tanpa checklist di bagian TnC | Menampilkan validasi bahwa checklist harus tercentang | Menampilkan validasi bahwa checklist harus tercentang | P | - |
| 8 | Melakukan daftar dengan email yang sudah terdaftar | Input email dengan yang sudah terdaftar lalu klik pada daftar | Menampilkan validasi email sudah terdaftar / email sudah digunakan. | Menampilkan validasi email sudah terdaftar / email sudah digunakan. | P | - |
| 9 | Melakukan login menggunakan akun google | Klik masuk dengan google - pilih email aktif - klik lanjutkan | Berhasil daftar dan masuk ke halaman verifikasi / OTP | Button berubah menjadi "Memproses" secara terus-menerus (stuck loading) dan tidak terjadi redirect ke Google OAuth | F | Issue: 07 - Button Daftar dengan Google Stuck Memproses dan Tidak Berfungsi |

# Modul Akun - Login

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Melakukan Login menggunakan data yang benar | Input email dan kata sandi dengan data yang benar > klik masuk | Masuk ke halaman beranda/Home page | Masuk ke halaman beranda/Home page | P | Catatan: Teks 'Anda masuk sebagai' kosong pada konfirmasi identitas (Issue 13) dan label tanpa bintang mandatory (Issue 10) |
| 2 | Melakukan Login dengan mengosongkan email | Input kata sandi, kosongkan email dan klik masuk | Gagal login dan menampilkan validasi field email kosong | Gagal login dan menampilkan validasi field email kosong | P | - |
| 3 | Melakukan Login dengan email invalid pada form | Input data dengan email invalid lalu klik masuk | Menampilkan validasi email tidak valid / tidak ditemukan | Menampilkan validasi email tidak valid / tidak ditemukan | P | - |
| 4 | Melakukan Login dengan mengosongkan kata sandi | Input email, kosongkan kata sandi dan klik masuk | Gagal login dan menampilkan validasi field kata sandi kosong | Gagal login dan menampilkan validasi field kata sandi kosong | P | - |
| 5 | Melakukan Login dengan kata sandi salah | Input email dan kata sandi yang salah lalu klik masuk | Menampilkan validasi value field salah | Menampilkan validasi value field salah | P | - |
| 6 | Klik pada tombol Lupa Kata Sandi | Klik pada tombol Lupa Kata Sandi | Direct user ke page lupa kata sandi | Sistem malah mengarahkan user ke halaman sesi auth (/auth) dengan pesan "Anda belum masuk ke akun manapun" | F | Issue: 05 - Klik Lupa Kata Sandi Malah Diarahkan ke Halaman Sesi |
| 7 | Melakukan input email dengan data valid lalu klik lanjutkan | input email yang relevan lalu klik lanjutkan | Direct user ke halaman proses selanjutnya untuk memasukkan kata sandi baru | Direct user ke halaman proses selanjutnya untuk memasukkan kata sandi baru | P | - |
| 8 | Melakukan input email yang tidak sesuai | imput email yang tida relevan lalu klik lanjutkan | Menampilkan alert "email tidak sesuai" | Menampilkan alert "email tidak sesuai" | P | - |

# Modul Akun - lupa kata sandi

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Masuk ke halaman Ubah Kata Sandi | Klik pada button Kirim di menu OTP > Direct user ke menu | Menampilkan komponen : 1. Field Kata Sandi Baru 2. Field Konfirmasi Kata Sandi Baru 3. Button simpan 4. Eye icon | Menampilkan komponen : 1. Field Kata Sandi Baru 2. Field Konfirmasi Kata Sandi Baru 3. Button simpan 4. Eye icon | P | Catatan: Label kata sandi baru & konfirmasi tanpa bintang mandatory (Issue 11) |
| 2 | Melakukan Simpan dengan menginput semua data di field | Input semua data > Simpan | Berhasil menyimpan kata sandi baru | Berhasil menyimpan kata sandi baru | P | - |
| 3 | Melakukan Simpan dengan tidak menginput semua data di field | Input salah satu data > Simpan | Menampilkan validasi terkait data yang belum diinput | Menampilkan validasi terkait data yang belum diinput | P | - |
| 4 | Melakukansimpan setelah mengisi kata sandi dan konfirmasi kata sandi dengan data yang berbeda | Input semua data dengan data yang tidak sama > Simpan | Menampilkan validasi konfirmasi kata sandi tidak sama dengan kata sandi | Menampilkan validasi konfirmasi kata sandi tidak sama dengan kata sandi | P | - |
| 5 | Menginput kata sandi tidak valid / tidak sesuai ketentuan | Input kata sandi dengan value tidak valid / seperti email pengguna | menampilkan validasi value tidak valid / tidak sesuai ketentuan | menampilkan validasi value tidak valid / tidak sesuai ketentuan | P | - |
| 6 | Melakukan Login dengan kata sandi baru | Input kata sandi baru pada form login lalu klik login | Berhasil login menggunakan kata sandi baru | Setelah reset kata sandi, button Masuk Sekarang terpental kembali ke halaman sesi (/auth) dan gagal membuka form login | F | Issue: 12 - Button Masuk Sekarang Terpental ke Halaman Sesi dan Gagal Membuka Login |
| 7 | Melakukan Login dengan kata sandi lama | Input kata sandi lama pada form login lalu klik login | Gagal Login dengan kata sandi lama | Gagal Login dengan kata sandi lama | P | - |
| 8 | Melakukan Logout | Klik profile = klik keluar - konfirmasi "ya keluar" | Berhasil logout akun | Setelah logout akun, header navbar tetap mempertahankan badge profil dan tidak kembali ke button Masuk | F | Issue: External Beranda 02 - Setelah Logout Navbar Profil Tidak Berubah Menjadi Button Masuk |

# Modul Beranda - Home Page

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Melakukan Search menggunakan Lokasi dan Jenis Property | Pada section search asset isi Lokasi - isi Jenis Property - klik cari | Direct ke halaman after search dan menampilkan hasil pencarian yang relevan, menampilkan wording khusus "\*Jenis Properti\* dijual di \*Lokasi Pilihan\*" |  |  |  |
| 2 | Melakukan Search menggunakan Lokasi saja | Pada section search asset isi Lokasi - klik cari dan pilih Lokasi | Direct ke halaman after search dan menampilkan hasil pencarian yang relevan, menampilkan wording khusus "Properti dijual di \*Lokasi Pilihan\*" |  |  |  |
| 3 | Melakukan Search menggunakan Lokasi Dekat Saya | Pada section search asset, klik Lokasi dan Pilih Dekat Saya | Direct ke halaman after search dan menampilkan hasil pencarian yang relevan, menampilkan wording khusus "Properti dijual di \*Dekat Saya\*" |  |  |  |
| 4 | Melakukan Search menggunakan Jenis Property saja | Pada section search asset, isi Jenis Property lalu klik cari | Direct ke halaman after search dan menampilkan hasil pencarian yang relevan, menampilkan wording khusus "\*Pilihan Properti\* dijual di semua Lokasi" |  |  |  |
| 5 | Melakukan Search tanpa mengisi kolom Lokasi dan Jenis Property | Pada section search asset, klik cari tanpa mengisi kolom | Direct ke halaman after search dan menampilkan hasil pencarian yang relevan, menampilkan wording khusus "Properti dijual di semua Lokasi" |  |  |  |
| 6 | Melakukan Search dengan hasil akhir berupa data tidak tersedia | Pada section search asset, isi Jenis Property dan Lokasi dengan data tidak cocok lalu klik cari | Menampilkan empty page dengan Wording yang sesuai |  |  |  |
| 7 | Melakukan Pengecekkan Section Rekomendasi hunian untuk Kamu | Scroll slider untuk menemukan section Rekomendasi | Menampilkan aset rekomendasi hunian kamu | Section rekomendasi hunian kosong dan memunculkan empty state "Oops! Tidak Ada Data Rekomendasi Yang Ditemukan" | Catatan | Catatan: Perlu konfirmasi ke tim terkait ketersediaan data dinamis aset rekomendasi (Issue External Beranda 03) |
| 8 | Melakukan pengecekkan Slider pada Section Rekomendasi Aset Idaman Kam | Klik pada button < atau > pada Section Rekomendasi Asset Idaman Kamu | Saat di klik dapat menggeser asset sesuai arah slider yang di klik |  |  |  |
| 9 | Melihat lebih banyak aset | Klik button selengkapnya | Direct ke halaman after search dan menampilkan list semua aset yang tersedia |  |  |  |

# Modul Beranda - After Search

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | mencari data pada search bar | Input nama aset pada kolom pencarian lalu klik cari | Menampilkan data aset yang sesuai |  |  |  |
| 2 | Klik pada button Filter pencarian aset | Klik pada button Filter disamping search bar | Menampilkan popup Filter dengan banyak opsi untuk dikombinasikan |  |  |  |
| 3 | Filter menggunakan Lokasi pada Filter Pencarian Aset | Klik Filter - Pilih Lokasi lalu Terapkan | Saat di terapkan akan menampilkan data sesuai dengan lokasi yang dipilih |  |  |  |
| 4 | Filter menggunakan Tipe aset pada Filter Pencarian Aset | Klik Filter - Pilih satu atau beberapa Tipe Properti lalu Terapkan | Saat di terapkan akan menampilkan data sesuai dengan tipe properti yang dicentang |  |  |  |
| 5 | Filter menggunakan status properti pada filter pencarian | klik filter - checklis status properti lalu terapkan | Saat di terapkan akan menampilkan data sesuai dengan status properti yang diinput |  |  |  |
| 6 | Filter menggunakan Luas Tanah pada Filter Pencarian Aset | Klik Filter - Pilih atau masukkan Luas Tanah lalu Terapkan | Saat di terapkan akan menampilkan data sesuai dengan luas tanah yang diinput |  |  |  |
| 7 | Filter menggunakan Harga pada Filter Pencarian Aset | klik filter - pilih atau masukan harga minimun dan maximum yang diinginkan lalu terapkan | Saat di terapkan akan menampilkan data sesuai dengan harga yang diinput |  |  |  |
| Klik Filter - Pilih atau masukkan Harga lalu Terapkan | Saat di terapkan akan menampilkan data sesuai dengan range harga yang diinput |  |  |  |
| 8 | Klik Reset Filter | Setelah melakukan filter data - klik button reset | Filter akan reset ke state default |  |  |  |
| 9 | Mencoba mencari data dengan hasil tidak ada menggunakan search bar | Input nama aset pada kolom search dengan data invalid - klik pada button cari | Menampilkan state empty page pada after search |  |  |  |
| 10 | Melakukan filter menggunakan kategori aset | klik salah satu button kategori aset (lelang, cassie, skm atau jual bersama) | saat di klik menampilkan data sesuai dengan kategori aset yang dipilih |  |  |  |
| 11 | Mencoba Sorting berdasarkan Aset Terbaru | Klik filter "Urutan" - Pilih pada Terbaru | Menampilkan hasil sorting sesuai dengan pilihan |  |  |  |
| 12 | Mencoba Sorting berdasarkan Aset Terlama | Klik filter "Urutan" - Pilih pada Terlama | Menampilkan hasil sorting sesuai dengan pilihan |  |  |  |
| 13 | Mencoba Sorting berdasarkan Harga Tertinggi | Klik filter "Urutan" - Pilih pada Harga Tertinggi | Menampilkan hasil sorting sesuai dengan pilihan |  |  |  |
| 14 | Mencoba Sorting berdasarkan Harga Terendah | Klik filter "Urutan" - Pilih pada Harga Terendah | Menampilkan hasil sorting sesuai dengan pilihan |  |  |  |
| 15 | Mencoba Sorting berdasarkan Tanggal Lelang Terdekat | Klik filter "Urutan" - Pilih pada Tanggal Lelang Terdekat | Menampilkan hasil sorting sesuai dengan pilihan |  |  |  |
| 16 | Mencoba Sorting berdasarkan Tanggal Lelang Terjauh | klik filter "Urutan" - Pilih pada Tanggal Lelang Terjauh | Menampilkan hasil sorting sesuai dengan pilihan |  |  |  |
| 17 | Melskukan pengeceka Asset terdekat dengan Maps | Scroll pada Maps disamping | Menampilkan data asset yang berada di jangkauan maps dengan mark merah |  |  |  |
| 18 | Melakukan pengecekkan sinkronisasi paginasi yang dipilih dan data Aset yang tampil | Ganti Paginasi dengan data semisal 10 ke 20 | Menampilkan banyak data 20 per halaman, mengganti wording 1-10 ke 1-20 |  |  |  |
| 19 | Klik Favorit aset | klik favorit pada salah satu data aset | Aset akan ditambahkan ke menu favorit, text akan berubah menjadi Difavoritkan |  |  |  |
| 20 | Membagikan Aset | klik bagikan pada salah satu data aset | Memberi banyak opsi default share |  |  |  |

# Modul Jenis agunan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman jenis angunan | Klik jenis angunan - lalu klik gedung | Menampilkan halman sesuai jenis angunan yang dipilih | Dropdown Jenis Agunan muncul sebagai kotak putih kosong (blank) tanpa pilihan item kategori, sehingga halaman kategori tidak dapat diakses | Catatan | Catatan: Perlu konfirmasi ke tim terkait integrasi menu kategori agunan (Issue 01 Jenis Agunan) |
| 2 | Melihat data rumah pada jenis angunan | Klik jenis angunan - klik rumah | Menampilkan halaman dan list data rumah |  |  |  |
| 3 | Melihat data gudang pada jenis angunan | klik jenis angunan - klik gudang | Menampilkan halaman dan list data gudang |  |  |  |
| 4 | Melihat data hotel pada jenis angunan | Klik jenis angunan - klik hotel | Menampilkan halaman dan list data hotel |  |  |  |
| 5 | Melihat data pabrik pada jenis angunan | Klik jenis angunan - klik pabrik | Menampilkan halaman dan list data pabrik |  |  |  |
| 6 | Melihat data pusat perbelanjaan pada jenis angunan | Klik jenis angunan - klik pusat perbelanjaan | Menampilkan halaman dan list data pusat perbelanjaan |  |  |  |
| 7 | Melihat data SPBU pada jenis angunan | Klik jenis angunan - klik SPBU | Menampilkan halaman dan list SPBU |  |  |  |
| 8 | Melihat data proyek rumah pada jenis angunan | Klik jenis angunan - klik proyek rumah | Menampilkan halaman dan list data proyek rumah |  |  |  |
| 9 | Melihat data apartemen pada jenis angunan | Klik jenis angunan - klik apartemen | Menampilkan halaman dan list data apartemen |  |  |  |
| 10 | Melihat data Proyek apartemen pada jenis angunan | Klik jenis angunan - klik proyek apartemen | Menampilkan halaman dan list data proyek apartemen |  |  |  |
| 11 | Melihat data kavling pada jenis angunan | Klik jenis angunan - klik kavling | Menampilkan halaman dan list data kavling |  |  |  |
| 12 | Melihat data kios pada jenis angunan | Klik jenis angunan - klik kios | Menampilkan halaman dan list data kios |  |  |  |
| 13 | Melihat data ruko pada jenis angunan | Klik jenis angunan - klik ruko | Menampilkan halaman dan list data ruko |  |  |  |
| 14 | Melihat data gedung kantor pada jenis angunan | Klik jenis angunan - klik gedung | Menampilkan halaman dan list data gedung |  |  |  |
| 15 | Melihat data rukan pada jenis angunan | Klik jenis angunan - klik rukan | Menampilkan halaman dan list data rukan |  |  |  |

# Modul Estimasi Lelang

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman estimasi lelang | klik estimasi lelang | Berhasil menampilkan Halaman Estimasi Lelang | Halaman Estimasi Lelang berhasil terbuka namun langsung memunculkan empty state "Oops! Tidak Ada Data Aset Yang Ditemukan" (0 data aset) | Catatan | Catatan: Perlu konfirmasi ke tim apakah default halaman memang kosong atau menampilkan katalog awal (Issue 01 Estimasi Lelang) |
| 2 | Filter menggunakan Lokasi Dekat Saya dan klik Cari | Pilih filter dekat saya - klik button cari | Menampilkan semua data lelang dengan lokasi radius 50 km dari lokasi pengecekan |  |  |  |
| 3 | Filter menggunakan Lokasi yang diinginkan lalu klik Cari | klik filter dekat saya - Pilih filter sesuai lokasi yang diinginkan - klik button cari | Menampilkan data lelang sesuai lokasi yang dipilih |  |  |  |
| 4 | Filter menggunakan satu tipe asset | Klik filter tipe properti (semua) - Pilih 1 tipe property - Klik button terapkan - klik button cari | Menampilkan data lelang sesuai tipe properti yang dipilih |  |  |  |
| 5 | Filter menggunakan lebih dari satu tipe asset | Klik filter tipe properti (semua) - klik tipe properti lebih dari 1 -- klik button terapkan - klik button cari | Menampilkan data lelang sesuai tipe properti yang dipilih |  |  |  |
| 6 | Filter dengan memilih semua tipe asset | Klik filter tipe properti (semua) - klik pilih semua - Klik button terapkan - klik button cari | Menampilkan data lelang dengan semua tipe properti |  |  |  |
| 7 | Filter menggunakan Harga | Klik filter harga - klik input / pilih harga - klik button terapkan - klik button cari | Menampilkan data lelang seuai harga yang dipilih |  |  |  |
| 8 | Filter menggunakan sorting Lantai | Klik filter lantai - pilih jumlah lantai dengan klik icon tambah - klik button terapkan - klik button cari | Menampilkan data aset lelang dengan keterangan lantai sesuai |  |  |  |
| 9 | Filter menggunakan Tanggal Lelang | Klik filter tanggal lelang - pilih tanggal - klik button terapkan - klik button cari | Menampilkan data lelang sesuai tanggal yang dipilih |  |  |  |
| 10 | Filter menggunakan Sorting Urutkan | Klik filter urutan - Pilih urutkan berdasarkan - klik button cari | Menampilkan data lelang sesuai sorting yang dipilih |  |  |  |
| 11 | Melakukan pengecekan pagination pada halaman estimasi lelang | klik pagination | Menampilkan data sesuai pagination yang dipilih |  |  |  |

# Modul Detail Aset - Detail Aset

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Melihat detail aset | Klik pada salah satu nama aset di beranda maupun entry point lainya | Direct ke halaman detail aset yang dipilih |  |  |  |
| 2 | Melihat semua gambar aset yang tersedia | Klik pada button Lihat Selengkapnya | Menampilkan preview page dengan tampilan yang sesuai |  |  |  |
| 3 | Klik Favorit aset pada menu detail aset | klik favorit pada card pembelian | Aset akan ditambahkan ke menu favorit, text akan berubah menjadi Difavoritkan |  |  |  |
| 4 | Bagikan aset pada menu detail aset | Klik button Bagikan di card pembelian | Memberi banyak opsi default share |  |  |  |
| 5 | Klik Beli Sekarang pada Detail Aset | Klik pada button Beli Sekarang | Direct ke halaman Formulir Pemesanan |  |  |  |
| 6 | Klik cek simulasi pembiayaan | Klik cek simulasi pembiayaan | Direct ke halaman simulasi pembiayaan |  |  |  |
| 7 | Klik button bandingkan aset ini | Klik bandingkan aset ini | Direct ke halaman bundingkan Properti |  |  |  |

# Modul Detail Aset - Favorit

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Menampilkan data favorit di menu favorit pada profil | Tambahkan favorit dari carousel maupun detail asset > Klik Profile dan Favorit | Menampilkan data asset yang telah di mark favorit |  |  |  |
| 2 | Pengecekkan Sinkronisasi data favorit di menu favorit dan List Asset | Tambahkan favorit di List Asset dan cek pada menu favorit terkait asset tersebut | Asset yang ditambahkan favorit akan muncul di menu favorit |  |  |  |
| 3 | Mencoba hapus mark favorit | Klik Favorit pada carousel asset > Klik lagi pada favorit | Mark favorit akan hilang pada asset yang dipilih |  |  |  |

# Modul Detail Aset - Formulir pesanan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Melakukan pembelian aset | Klik beli sekarang untuk masuk ke halaman formulir pemesanan - kemudian pilih kategori penjualan dan catatan - klik checkbox "biodata sudah benar" - lalu klik kirim | Sukses mengirim data pemesanan dan direct ke detail pesanan pada menu user |  |  |  |
| 2 | Mencoba mengganti data pada Kategori Penjualan dan Catatan | Ganti tipe pembelian antara Cassie, LSM, Jual Bersama maupun tipe lainnya, dan isi catatan lalu kirim | Data tetap berhasil dikirim. kategori penjualan akan mengikuti pilihan yang dipilih user dengan harga menyesuaikan |  |  |  |
| 3 | Mencoba isi data alamat pada form profil | Isi pada data alamat di form profil | Setelah terisi, checklist akan dapat di klik |  |  |  |

# Modul Detail Aset - Simulasi Pembiayaan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Melakukan Simulasi Pembiayaan | pilih jenis bagi hasil(anuitas atau flat), jenis subsidi (subsidi atau non subsidi), input harga beli properti, uang muka, bagi pertahun, lama pembiayaan, masa pembiayaan fix dan pembiayaan perjenjang lalu klik button hitung | Menampilkan hasil rincian dan detail angsuran simulasi pembiayaan |  |  |  |

# Modul Bandingkan

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halamanan bandingkan properti | Klik bandingkan | Menampilkan halaman bandingkan properti |  |  |  |
| 2 | Melakukan perbandingan properti | Klik button + aset/ button cari properti sekarang | Menampilkan list data aset |  |  |  |
| Pilih aset dengan klik button bandingkan | Berhasil select aset yang diinginkan |  |  |  |
| klik button bandingkan | Menampilkan hasil perbandingan anatara aset yang dipilih |  |  |  |
| 3 | Melakukan perbandingan lebih dari 4 aset | klik button +aser/ button cari poperti - kemudian pilih aset lebih dari 4 | Menampilkan alert " maximal properti yang dapat di bandingkan 4" |  |  |  |
| 4 | klik button bersihkan | klik button bersihkan | Berhasil reset aset yang dipilih |  |  |  |