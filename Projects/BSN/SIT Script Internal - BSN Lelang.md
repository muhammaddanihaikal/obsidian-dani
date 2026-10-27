---
tags:
  - SIT
  - BSN
  - Internal
  - QA
  - TestScript
date: 2026-10-27
project: BSN Lelang
platform: Internal
source_file: SIT_Script_Internal_-_BSN Lelang.docx
total_script: 181
converter: markitdown
---

|  |  |  |
| --- | --- | --- |
| **Application : BSN Lelang** | **Jumlah Script : 181** | **Version :** 1.0 |
| **Modul :**   * **Modul Login** * **Modul User Authority – Role** * **Modul User Authority – User** * **Modul Dashboard** * **Modul Inventory Aset – Aset** * **Modul Inventory Aset – Approval aset** * **Modul Inventory Aset – Katalog Marketing** * **Modul Customer Management – Ticket** * **Modul Customer Management – Leads** * **Modul Audit Trail** | **Estimasi Jangka Waktu Pengujian :** 1 hari |  |
|  |  |

# Modul Login

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Mengakses website BSN Lelang | Buka Akses Link Web BSN Lelang Internal | Berhasil menampilkan halaman form login | Berhasil menampilkan halaman form login | P | - |
| 2 | Melakukan login | Input email & Password - Klik button Login | Login Berhasil dan menampilkan halaman Dashboard | Login Berhasil dan menampilkan halaman Dashboard | P | Catatan: Button 'Masuk dengan akun lain' pada halaman konfirmasi identitas tidak berfungsi (Issue 02 Internal) |
| 3 | Melakukan login hanya menggunakan email | Input email - Klik button Login | Login Gagal dan Menampilkan alert "Isian password tidak boleh kosong." | Login Gagal dan Menampilkan alert "Isian password tidak boleh kosong." | P | - |
| 4 | Melakukan login dengan Password Salah | Input email - Input Password salah - Klik button Login | Login Gagal dan Menampilkan alert "Email atau kata sandi salah" | Login Gagal dan Menampilkan alert "Email atau kata sandi salah" | P | - |

# Modul User Authority - Role

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman Role | Klik menu User Management - Klik Sub menu Role | Menampilkan halaman Role |  |  |  |
| 2 | Menambahkan data Role | Klik button Add Role - Input data Role - Klik button Submit | Berhasil menambahkan data Role |  |  |  |
| 3 | Mengubah data dan Akses role | Klik Action titik tiga - Klik Edit - Ubah data - Klik button Submit | Berhasil mengubah data dan akses Role |  |  |  |
| 4 | Menghapus data Role | Klik Action titik tiga - Klik Delete - Klik button Delete | Berhasil Menghapus data Role |  |  |  |
| 5 | Filter Data Role yang sesuai | Input nama role - Klik button Search | Menampilkan data sesuai dengan kata kunci yang di cari |  |  |  |
| 6 | Filter Data Role yang tidak sesuai | Input kata kunci tidak ada pada list data - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 7 | Cek pagination data Role | Klik pagination sesuai dengan data yang ingin di tampilkan (10/page) | Menampilkan data Role sesuai dengan pagination yang di pilih |  |  |  |

# Modul User Authority - User

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman user | Klik menu User Management - Klik Sub menu User | Menampilkan list data user |  |  |  |
| 2 | Menambahkan data User AD | Klik button +Add New User - Input data New User - Klik toggle switch User AD - input user AD - klik button Cari - Pilih role - Pilih kantor - Klik button Submit | Berhasil menambahkan user AD |  |  |  |
| 3 | Tidak menginput data mandatory saat add user menggunakan AD | Tidak menginput data mandatory bertanda (\*) | Menampilkan alert bahwa data mandatory (harus diisi) |  |  |  |
| 4 | Menginput email tidak sesuai format saat menambahkan user AD | Input email tidak menggunakan '@' atau tidak menggunakan domain | Menampilkan alert 'Email tidak Valid!' pada form inputan email |  |  |  |
| 5 | Menginput user AD yang tidak sinkron dengan hasil inquiry | Input user AD - Klik button cari - Ganti user AD dengan yang lain - Klik button Submit | Menampilkan alert bahwa data konflik karena tidak sinkron antara user AD dengan hasil inquiry |  |  |  |
| 6 | Menambahkan data User non AD | Klik button +Add New User - Input data New User - Klik button Submit | Berhasil menambahkan user non AD |  |  |  |
| 7 | Tidak menginput data mandatory saat input user non AD | Tidak menginput data mandatory bertanda (\*) | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 8 | Menginput email tidak sesuai format saat input user non AD | Input email tidak menggunakan '@' atau tidak menggunakan domain | Menampilkan alert 'Email tidak Valid!' pada form inputan email |  |  |  |
| 9 | Menginput password tidak sesuai dengan ketentuan (8 digit, Angka, dan simbol) saat input user non AD | Input Password tidak sesuai ketentuan | Menampilkan alert bahwa data belum memenuhi ketentuan |  |  |  |
| 10 | Melihat detail data User | Klik Action titik tiga - Klik Detail | Menampilkan detail data user |  |  |  |
| 11 | Mengubah data User | Klik Action titik tiga - Klik Edit - Ubah data user - Input Password - Klik button Submit | Berhasil mengubah data User |  |  |  |
| 12 | Menghapus data User | Klik icon titik tiga - Klik icon Delete - Klik Delete | Berhasil Menghapus data User |  |  |  |
| 13 | Mengunduh data User | Klik button Download data | Berhasil Mengunduh data User |  |  |  |
| 14 | Melihat status unduhan data | Klik titik tiga yang ada di sebelah button Download Data - Klik See Status | Menampilkan status Memproses jika sedang mengunduh data, dan menampilkan data yang sudah di unduh per hari ini dan kemarin |  |  |  |
| 15 | Mengaktifkan User | Klik Action Titik Tiga - Klik Unblock - Klik Unblock User | Berhasil Mengaktifkan User |  |  |  |
| 16 | Menonaktifkan User | Klik Action titik tiga - Klik Block - Klik Block User | Berhasil Menonaktifkan User |  |  |  |
| 17 | Validasi Last Login Information | Melakukan login dengan menggunakan browser lain - Cek pada tabel last login | Informasi last login akan terupdate pada tabel last login |  |  |  |
| 18 | Pagination data User | Klik pagination sesuai dengan data yang ingin di tampilkan (10/page) | Menampilkan data User sesuai dengan pagination yang di pilih |  |  |  |

# Modul Dashboard

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman dashboard | Klik menu Dashboard | Menampilkan halaman dashbaord |  |  |  |
| 2 | Filter Data Dashboard dengan data yang sesuai | Pilih/ketik Kantor cabang - Pilih Filter tanggal - Klik button Cari | Menampilkan Data sesuai data secara filter yang sudah di pilih |  |  |  |
| 3 | Filter data dashboard yang tidak sesuai | Ketik Kantor cabang yang tidak sesuai - Pilih Filter tanggal - Klik button Cari | Tidak menampilkan apapun (no data) |  |  |  |
| 4 | Pengecekan card aser demografi | klik dashboard - pilih filter tanggal dan kantor cabang - klik button cari | Menampilkan Data Map Demographic |  |  |  |
| 5 | Pengecekan data top 2 provinsi dengan aset terbanyak | cek data provinsi terbanyak di menu aset | Menampilkan 2 Top Provinsi dengan Jumlah Aset terbanyak pada Aset Demographic |  |  |  |
| 6 | Menampilkan Titik Aset pada Daerah yang ada di Map Demographic | cek titik maps | Menampilkan Titik Aset pada Daerah yang ada di Map Demographic |  |  |  |
| 7 | Menampilkan section Aset Overview | Cek data yang tampil pada section Aset Overview | Menampilkan jumlah total data Aset Overview |  |  |  |
| 8 | Pengecekan data Aset overview (total) | Cek data jumlah total aset dan nominal nya sesuai dengan data yang ada pada menu aset | Menampilkan jumlah data aset yang terdapat pada rumah murah dengan status publish, unpublish (General, pasca lelang, pembayaran) |  |  |  |
| 9 | Pengecekan data Aset overview (pembayaran) | Cek data jumlah total pembayaran dan nominal nya sesuai dengan data yang ada pada menu aset | Menampilkan jumlah data aset pembayaran (aset yang statusnya closing) |  |  |  |
| 10 | Pengecekan data Aset overview (publish) | Cek data jumlah total aset yang publish dan nominal nya sesuai dengan data yang ada pada menu aset | Menampilkan jumlah data yang status asetnya publish |  |  |  |
| 11 | Pengecekan data Aset overview (unpublish) | Cek data jumlah total aset yang unpublish dan nominal nya sesuai dengan data yang ada pada menu aset | Menampilkan jumlah data yang staus asetnya unpublish (General, pasca lelang, pembayaran) |  |  |  |
| 12 | Pengecekan Data Aset Overview (Aset Draft) | Cek data jumlah total aset yang draft dan nominal nya sesuai dengan data yang ada pada menu aset | Jumlah Data Aset Draft sesuai dengan data yang ada pada menu Aset |  |  |  |
| 13 | Pengecekan Data Aset Overview (Kredit Lunas) | Cek data jumlah total aset yang kredit lunas dan nominal nya sesuai dengan data yang ada pada menu aset | Jumlah Data Aset Kredit Lunas sesuai dengan data yang ada pada menu Aset |  |  |  |
| 14 | Pengecekan Data Aset Overview (Kol Membaik) | Cek data jumlah total aset yang kol membaik dan nominal nya sesuai dengan data yang ada pada menu aset | Jumlah Data Aset Kol Membaik sesuai dengan data yang ada pada menu Aset |  |  |  |
| 15 | Menampikan Data Aset Penjualan NoA & VoA dengan Pola Penjualan Lelang | Scroll halaman Dashboard hingga Section Penjualan | Berhasil Menampilkan NoA dan VoA data Aset dengan pola penjualan Lelang sesuai dengan data yang ada pada halaman Aset |  |  |  |
| 16 | Menampikan Data Aset Penjualan NoA & VoA dengan Pola Penjualan SKM | Scroll halaman Dashboard hingga Section Penjualan | Berhasil Menampilkan NoA dan VoA data Aset dengan pola penjualan Lelang sesuai dengan data yang ada pada halaman Aset |  |  |  |
| 17 | Menampikan Data Aset Penjualan NoA & VoA dengan Pola Penjualan Jual Bersama | Scroll halaman Dashboard hingga Section Penjualan | Berhasil Menampilkan NoA dan VoA data Aset dengan pola penjualan Lelang sesuai dengan data yang ada pada halaman Aset |  |  |  |
| 18 | Menampikan Data Aset Penjualan NoA & VoA dengan Pola Penjualan Cessie | Scroll halaman Dashboard hingga Section Penjualan | Berhasil Menampilkan NoA dan VoA data Aset dengan pola penjualan Lelang sesuai dengan data yang ada pada halaman Aset |  |  |  |
| 19 | Menampilkan Grafik lingkaran total aset | Menampilkan grafik lingkaran total aset berdasarkan Bisnis Unit (konsumer, komersial) | Menampilkan grafik lingkaran total aset berdasarkan bisnis unit |  |  |  |
| 20 | Pengecekan Data Aset Total Aset (Jumlah Total Aset Approve) | Cek data jumlah total aset approve | Menampilkan jumlah total aset approve sesuai dengan data aset yang sudah di approve sesuai dengan filter kantor dan tanggal yang sebelumnya sudah di pilih |  |  |  |
| 21 | Pengecekan Data Aset Total Aset (Jumlah Total Aset Reject) | Cek data jumlah total aset reject | Menampilkan jumlah total aset approve sesuai dengan data aset yang di reject sesuai dengan filter kantor dan tanggal yang sebelumnya sudah di pilih |  |  |  |
| 22 | Menampikan Data Aset Lelang NoA & VoA dengan Status Lelang Berjalan | Scroll halaman Dasboard hingga Section Lelang | Menampilkan jumlah NoA dan VoA dari Aset yang berstatus Lelang Berjalan |  |  |  |
| 23 | Menampikan Data Aset Lelang NoA & VoA dengan Status Laku Lelang | Scroll halaman Dasboard hingga Section Lelang | Menampilkan jumlah NoA dan VoA dari Aset yang berstatus Laku Lelang |  |  |  |
| 24 | Menampikan Data Aset Lelang NoA & VoA dengan Status Batal Lelang | Scroll halaman Dasboard hingga Section Lelang | Menampilkan jumlah NoA dan VoA dari Aset yang berstatus Batal Lelang |  |  |  |
| 25 | Menampikan Data Aset Lelang NoA & VoA dengan Status Pasca Lelang | Scroll halaman Dasboard hingga Section Lelang | Menampilkan jumlah NoA dan VoA dari Aset yang berstatus Pasca Lelang |  |  |  |
| 26 | Menampilkan data Status Input | Cek data status input pada section status input aset | Menampilkan data status input aset dan sesuai dengan filter yang sudah di pilih |  |  |  |
| 27 | Pengecekan data berdasarkan Status Input | Cek data yang ditampilkan pada status input aset berdasarkan fase inputnya | Menampilkan jumlah data berdasarkan status input aset |  |  |  |
| 28 | Menampilkan data VOA Status Peminataan Aset | Data Status Peminataan Aset | Menampilkan data VOA (Volume of Asset) berdasarkan jumlah nominal aset peminat |  |  |  |
| 29 | Menampilkan data NOA Status Peminataan Aset | Data Status Peminataan Aset | Menampilkan data NOA (Number of Asset) berdasarkan jumlah peminat aset |  |  |  |
| 30 | Menampilkan data peringkat aset yang diminati berdasarkan jumlah view | Cek pada tabel peringkat aset diminati tab view | Menampilkan data aset berdasarkan data peringkat aset yang diminati berdasarkan jumlah view |  |  |  |
| 31 | Mengunduh data peringkat aset diminati - View | Klik View pada peringkat aset diminati | Berhasil mengunduh data peringkat aset diminati |  |  |  |
| 32 | Menampilkan data peringkat aset yang diminati berdasarkan jumlah favorit | Cek pada tabel peringkat aset diminati tab favorit | Menampilkan data aset berdasarkan data peringkat aset yang diminati berdasarkan jumlah favorit |  |  |  |
| 33 | Mengunduh data peringkat aset diminati - Favorit | Klik Favorit pada peringkat aset diminati | Berhasil mengunduh data peringkat aset diminati |  |  |  |
| 34 | Melihat status unduhan data | Klik titik tiga yang ada di sebelah button Download Data - Klik See Status | Menampilkan status Memproses jika sedang mengunduh data, dan menampilkan data yang sudah di unduh per hari ini dan kemarin |  |  |  |
| 35 | pengecekan pagination | Klik pagination sesuai dengan data yang ingin di tampilkan (10/page) | Menampilkan data sesuai dengan jumlah yang dipilih |  |  |  |

# Modul Inventory Aset - Aset

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman Aset | Klik menu Inventory Aset - Klik sub menu Aset | Menampilkan Halaman Aset |  |  |  |
| 2 | Menambahkan data aset | Klik button +Add New Aset | Menampilkan form input data set baru |  |  |  |
| 3 | Menginput data aset baru pada step 1 (No rek debitur) | Menginput data step 1(No.Rek Debitur) - Pilih Bisnis Unit - Pilih Kantor - Input no rekening debitur > search | Dapat mengisi data bisnis unit, kantor dan melakukan inquiry debitur |  |  |  |
| Kemudian klik button next | Berhasil menginput data step 1 dan dapat melanjutkan ke step selanjutnya |  |  |  |
| 4 | Tidak menginput data mandatory step 1 | Tidak menginput data mandatory bertanda (\*) | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 5 | Save As Draft sampai pengisian step 1 | Menginput data step 1 (No.Rek Debitur) - kemudian Klik button Save As Draft | Berhasil menginput data step 1 dan menyimpan data sebagai Draft |  |  |  |
| 6 | Menginput data aset baru pada step 2 dengan input kategori aset | Mengiput data step 2 (Informasi aset) - Input nama Aset - Pilih Kategori Aset | Dapat mengisi data nama aset dan kategori aset, kemudian akan muncul detail isian sesuai pilihan kategori aset yang dipilih |  |  |  |
| - Lengkapi detail sesuai pilihan kategori aset yang dipilih - kemudian Klik button next untuk melanjutkan ke step selanjutnya | Berhasil menginput data step 2 dan dapat melanjutkan ke step selanjutnya |  |  |  |
| 7 | Tidak menginput data mandatory step 2 | Tidak menginput data mandatory bertanda (\*) - Nama aset - Kategori aset - field mandatory sesuai aset yang dipilih | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 8 | Save As Draft sampai pengisian step 2 | step 2 (Informasi aset) - kemudian Klik button Save As Draft Mengiput data sampai | Berhasil menginput data step 2 dan menyimpan data Aset sebagai Draft |  |  |  |
| 9 | Menginput data step 3 (Pola penjualan) | Mengiput data step 3 (Pola penjualan) - Pilih kategori penjualan | Dapat mengisi data pola penjualan dan menampilkan field harga sesuai pola penjualan yang dipilih |  |  |  |
| 10 | - Input Harga Aset sesuai kategori penjualan yang dipilih - Jika memilih lelang maka muncul toggle ketika terdapat tanggal dan lokasi lelang - PIC menampilkan sesuai dengan user yang login - Klik button next untuk melanjutkan ke step selanjutnya | Berhasil menginput data step 3 dan dapat melanjutkan ke step selanjutnya |  |  |  |
| 11 | Tidak menginput data mandatory step 3 | Tidak menginput data mandatory bertanda (\*) - kategori penjualan - harga aset - Tanggal dan lokasi lelang jika toogle diaktifkan | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 12 | Save As Draft sampai pengisian step 3 | Mengiput data step 3 (Pola penjualan) - kemudian Klik button Save As Draft | Berhasil menginput data step 3 dan menyimpan data sebagai Draft |  |  |  |
| 13 | Menginput data step 4 (Dokumen) | Menginput data step 4 (Dokumen) - Pilih salah satu nama dokumen - Klik Upload Dokumen | Berhasil menginput data nama dokumen dan muncul pop up pilih file upload |  |  |  |
| - Pilih file dokumen yang ingin di upload (rar, zip, pdf) - Klik button next untuk melanjutkan ke step selanjutnya | Berhasil menginput data step 4 dan dapat melanjutkan ke step selanjutnya |  |  |  |
| 14 | Menginput data step 5 (Lokasi) | Mengiput data step 5 (Lokasi) - Pilih provinsi - Pilih kota/ kabupaten - Pilih kecamatan - Pilih kelurahan/desa - Input kode pos - Field lain yang menyesuaikan inputan kategori aset | Berhasil menginput data provinsi, kota/kabupaten, kecamatan, kelurahan/desa, kode pos dan field lain yang sesuai dengan inputan kategori aset |  |  |  |
| Menentukan titik lokasi pada maps | Berhasil menentukan titik lokasi pada maps |  |  |  |
| Mengisi lokasi strategis | Berhasil menginput lokasi strategis |  |  |  |
| Klik button next untuk melanjutkan ke step berikutnya | Berhasil menginput data step 5 dan dapat melanjutkan ke step selanjutnya |  |  |  |
| 15 | Tidak menginput data mandatory step 4 | Tidak menginput data mandatory bertanda (\*) - Nama dokumen | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 16 | Save As Draft sampai pengisian step 4 | - Mengiput data step 4 (Dokumen) - kemudian Klik button Save As Draft | Berhasil menginput data step 4 dan menyimpan data sebagai Draft |  |  |  |
| 17 | Menginput data step 6 (Fasilitas) dan Menyimpan data Aset | Mengiput data step 6 (Fasilitas) Fasilitas > Klik Toggle sesuai fasilitas yang ada - Kamar Tidur (input jumlah kamar tidur) - Kamar Mandi (input jumlah kamar mandi) - Ruang Tamu - Ruang Keluarga - Ruang Makan - Dapur | Berhasil menginput data fasilitas |  |  |  |
| Fasilitas Umum > Klik Toggle sesuai fasilitas yang ada - Garasi/Area Parkir - Jaringan Air bersih - Jaringan Listrik - One Gate System - Keamanan 24 jam - Mesjid/tempat ibadah - alat pemadam api ringan (APAR) - Taman Terbuka Hijau - Taman bermain anak - Auditorium - Kolam renang - Lintasan lari - Pusat kebugaran - Gimnasium - Area komersial | Berhasil menginput data fasilitas umum |  |  |  |
| Klik button submit | Berhasil melakukan sumbit data aset dan menunggu approval |  |  |  |
| 18 | Tidak menginput data mandatory step 5 | Tidak menginput data mandatory bertanda (\*) | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 19 | Save As Draft sampai pengisian step 5 | Mengiput data step 5 (Lokasi) - Pilih provinsi - Pilih kota/ kabupaten - Pilih kecamatan - Pilih kelurahan/desa - Input kode pos - Field lain yang menyesuaikan inputan kategori aset - Klik button Save As Draft | Berhasil menginput data step 5 dan menyimpan data sebagai Draft |  |  |  |
| 20 | Mengubah data aset | Klik icon titik tiga - Klik action edit - Ubah data - klik button submit untuk menyimpan perubahan | Berhasil mengubah data aset |  |  |  |
| 21 | Melihat detail data aset | klik icon detail | Menampilkan detail data aset |  |  |  |
| 22 | Melakukan Filter Data Aset yang | Pilih kode aset - Pilih Kantor cabang - pilih lokasi - pilih status publikasi - klik button cari | Menampilkan data sesuai dengan kata kunci yang di cari |  |  |  |
| 23 | Filter Data Aset yang tidak sesuai | Input kata kunci tidak ada pada list data - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 24 | Mengunggah gambar aset sesuai ketentuan (4 - 10 Gambar) | Klik Unggah Gambar - Pilih gambar dengan ukuran dan format gambar yang sesuai - Klik button Open pada file manager | Berhasil menambahkan gambar aset |  |  |  |
| 25 | Mengunggah gambar Aset kurang dari ketentuan < 4 gambar | Upload file kurang dari 4 gambar | Menampilkan alert 'Gambar minimal 4" |  |  |  |
| 26 | Mengunggah gambar Aset lebih dari 10 | Upload file lebih dari 10 gambar | Menampilkan alert ‘Gamabar Maximal 10’ |  |  |  |
| 27 | Mengunggah gambar aset dengan ukuran file melebihi ketentuan | Klik Unggah Gambar - Pilih gambar dengan ukuran gambar yang tidak sesuai (max 5 mb) - Klik button Open pada file manager | Menampilkan alert "size gambar tidak sesuai max 5 mb" |  |  |  |
| 28 | Mengunggah gambar dengan format selain JPG, JPEG, dan PNG | Klik Unggah Gambar - Pilih gambar dengan format file selain JPG, JPEG, dan PNG - Klik button Open pada file manager | Menampilkan alert "format file tidak sesuai, gunakan JPG, JPEG dan PNG" |  |  |  |
| 29 | Unpublish data aset | Klik icon titik tiga - klik action Delete - Klik button Delete | Berhasil mengubah status Aset menjadi Unpublish dan general |  |  |  |
| 30 | Melakukan upload bulk data aset | Klik button upload bulk - klik download template - kemudian isi excell template - kembali ke web BSN - klik upload data - kemudian pilih file | Berhasil mengupload data aset secara bulk |  |  |  |

# Modul Inventory Aset - Approval Aset

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman Approval Aset | Klik menu Inventory Aset - Klik submenu Approval Aset | Berhasil menampilkan halaman Approval Aset dan berada di tab semua menampilkan semua list data approval aset |  |  |  |
| 2 | Tab Request Input | Klik tab Request Input | Berhasil menampilkan list data semua aset yang berstatus request input |  |  |  |
| 3 | Tab Request Input - melihat detail data di tab semua | Klik icon > atau Detail | Menampilkan halaman detail data aset request input |  |  |  |
| 4 | Melihat informasi akurasi aset pada halaman detail request input - semua | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 5 | Tab Request Input - Menunggu Diproses | Klik tab Request Input - Klik tab Menunggu Diproses | Berhasil menampilkan list data aset yang berstatus verifikasi menunggu diproses untuk publish |  |  |  |
| 6 | Melihat Detail Request Input - Menunggu Diproses | Klik tab Request Input - Klik tab Menunggu Diproses - Klik icon > atau Detail | Berhasil menampilkan halaman detail data request input yang menunggu diproses |  |  |  |
| 7 | Melihat informasi akurasi aset pada halaman detail request input - menunggu diproses | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 8 | Tab Request Input - Disetujui | Klik tab Request Input - Klik tab Disetujui | Berhasil menampilkan list data aset yang sudah di Disetujui |  |  |  |
| 9 | Melihat Detail Request Input - Disetujui | Klik tab Request Input - Klik tab Disetujui - Klik icon > atau Detail | Menampilkan halaman detail data request input yang disetujui |  |  |  |
| 10 | Melihat informasi akurasi aset pada halaman detail request input - Disetujui | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 11 | Tab Request Input - Ditolak | Klik tab Request Input - Klik tab Ditolak | Menampilkan list data aset yang Ditolak |  |  |  |
| 12 | Melihat Detail Request Input - Ditolak | Klik tab Request Input - Klik tab Ditolak - Klik icon > atau Detail | Menampilkan halaman detail data request input yang ditolak |  |  |  |
| 13 | Melihat informasi akurasi aset pada halaman detail request input - Ditolak | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 14 | Tab Request Unpublish | Klik tab Request Unpublish | Menampilkan list data semua aset yang berstatus request unpublish |  |  |  |
| 15 | Tab Request Unpublish - melihat detail data di tab semua | Klik icon > atau Detail | Menampilkan halaman detail data aset request unpublish |  |  |  |
| 16 | Melihat informasi akurasi aset pada halaman detail request unpublish - semua | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 17 | Tab Request Unpublish - Menunggu Diproses | Klik tab Request Unpublish - Klik tab Menunggu Diproses | Menampilkan list data aset yang berstatus menunggu diproses untuk unpublish |  |  |  |
| 18 | Melihat Detail Request Unpublish - Menunggu Diproses | Klik tab Request Unpublish - Klik tab Menunggu Diproses - Klik icon > atau Detail | Menampilkan halaman detail data request unpublish yang menunggu diproses |  |  |  |
| 19 | Melihat informasi akurasi aset pada halaman detail request unpublish - menunggu diproses | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 20 | Tab Request Unpublish - Disetujui | Klik tab Request Unpublish - Klik tab Disetujui | Menampilkan list data aset yang berstatus Disetujui |  |  |  |
| 21 | Melihat Detail Request Unpublish - Disetujui | Klik tab Request Unpublish - Klik tab Menunggu Disetujui - Klik icon > atau Detail | Menampilkan halaman detail data request unpublish yang disetujui |  |  |  |
| 22 | Melihat informasi akurasi aset pada halaman detail request unpublish - Disetujui | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 23 | Tab Request Unpublish - Ditolak | Klik tab Request Unpublish - Klik tab Ditolak | Menampilkan list data aset yang berstatus Ditolak |  |  |  |
| 24 | Melihat Detail Request Unpublish - Ditolak | Klik tab Request Unpublish - Klik tab Ditolak - Klik icon > atau Detail | Menampilkan halaman detail data request unpublish yang ditolak |  |  |  |
| 25 | Melihat informasi akurasi aset pada halaman detail request unpublish - Ditolak | Klik icon > atau Detail | Menampilkan informasi akurasi aset |  |  |  |
| 26 | Filter data berdasarkan Kode Aset yang sesuai | Pilih kode aset - Klik button Search | Berhasil Menampilkan list data approval sesuai dengan kode aset yang di pilih |  |  |  |
| 27 | Filter data berdasarkan kantor cabang | Pilih kantor cabang - Klik button Search | Berhasil Menampilkan list data approval aset sesuai dengan kantor cabang yang di pilih |  |  |  |
| 28 | Filter data berdasarkan PIC Approval | Pilih PIC Approval - Klik button Search | Menampilkan list data approval aset sesuai dengan PIC approval yang di pilih |  |  |  |
| 29 | Filter data berdasarkan tanggal pengajuan | Pilih tanggal pengajuan - Klik button Search | Berhasil Menampilkan list data approval aset sesuai dengan tanggal yang di pilih |  |  |  |
| 30 | Filter data kombinasi yang sesuai | Pilih kode Aset - Pilih kantor cabang - Pilih PIC Approval - Pilih tanggal pengajuan - Klik button Search | Menampilkan list data approval sesuai dengan filter yang di pilih |  |  |  |
| 31 | Filter berdasarkan kantor cabang yang tidak ada pada list | Pilih kantor cabang yang tidak ada data nya pada list - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 32 | Filter berdasarkan PIC Approval yang tidak ada pada list | Pilih PIC Approval yang tidak ada data nya pada list - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 33 | Filter berdasarkan tanggal pengajuan yang tidak ada pada list | Pilih tanggal pengajuan yang tidak ada data nya pada list - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 34 | Filter data kombinasi berdasarkan data yang tidak ada pada list | Pilih kode Aset - Pilih kantor cabang secara acak - Pilih PIC Approval secara acak - Pilih tanggal pengajuan secara acak - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 35 | Download attachment | Klik button Download pada kolom Attachment | Berhasil mengunduh attachment |  |  |  |
| 36 | Melakukan Approval untuk Request Input | Klik tab Request Input - Klik tab Menunggu Diproses - Scroll ke kanan untuk melihat action - Klik button Approve - Input approval reason - Klik button Approve | Berhasil melakukan approval kemudian status aset menjadi Publish dan data masuk pada tab Request Input - Disetujui |  |  |  |
| 37 | Membatalkan approval | Klik button Cancel | Berhasil membatalkan approval |  |  |  |
| 38 | Melakukan Reject untuk Request Input | Klik tab Request Input - Klik tab Menunggu Diproses - Scroll ke kanan untuk melihat action - Klik button Reject - Input rejection reason - Klik button Reject | Berhasil melakukan reject verifikasi aset kemudian status aset akan berubah menjadi Revisi dan data akan masuk pada tab Request Input - Ditolak |  |  |  |
| 39 | Membatalkan reject | Klik button Cancel | Berhasil membatalkan reject |  |  |  |
| 40 | Melakukan Approval untuk Request Unpublish | Klik tab Request Unpublish - Klik tab Menunggu Diproses - Scroll ke kanan untuk melihat action - Klik button Approve - Input approval reason - Klik button Approve | Berhasil melakukan approval untuk request unpublish dan data aset tidak akan muncul di external, status aset menjadi unpublish |  |  |  |
| 41 | Membatalkan approval | Klik button Cancel | Berhasil membatalkan approval |  |  |  |
| 42 | Melakukan Reject untuk Request Unpublish | Klik tab Request Unpublish - Klik tab Menunggu Diproses - Scroll ke kanan untuk melihat action - Klik button Reject - Input rejection reason - Klik button Reject | Berhasil melakukan reject unpublish aset dan status aset tetap menjadi publish |  |  |  |
| 43 | Membatalkan reject | Klik button Cancel | Berhasil membatalkan reject |  |  |  |

# Modul Inventory Aset - Katalog Marketing

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman katalog marketing | 1. Klik menu inventory aset 2. klik submenu catalog marketing | Menampilkan halaman katalog marketing |  |  |  |
| 2 | Melakukan setting background katalog | 1. Klik button setting background 2. upload gambar cover image dan fill image 3. klik button submit untuk menyimpan data | Berhasil melakukan setting data backgound |  |  |  |
| 3 | Mengubah setting background yang sudah di setting katalog dengan gambar baru | 1. Klik button setting background 2. klik pada gambar yang sudah diupload 3. klik button submit untuk menyimpan data | Berhasil memperbaharui setting data backgound |  |  |  |
| 4 | Mengunggah gambar background dengan ukuran file yang tidak sesuai ketentuan | 1. Klik button setting background 2. upload gambar (cover image, coven-consumer, Sharia- komersial, sharia - consumer) dengan ukuran yang tidak sesuai (max 5 mb) 3. klik button submit untuk menyimpan data | Menampilkan alert "size dokumen tidak sesuai mas 5 mb" |  |  |  |
| 5 | Mengunggah gambar background dengan format gambar selain JPG, JPEG, dan PNG | 1. Klik button setting background 2. upload gambar (cover image, coven-consumer, Sharia- komersial, sharia - consumer) Pilih gambar dengan format file selain JPG, JPEG, dan PNG 3. klik button submit untuk menyimpan data | Menampilkan alert "format gambar tidak sesuai, gunakan JPG, JPEG dan PNG" |  |  |  |
| 6 | Membatalkan background setting | klik (x) pada ujung kanan atas pop up | Membatalkan background setting dan kembali ke halaman utama menu catalog marketing |  |  |  |
| 7 | Membuat Katalog Marketing Syariah - konsumer | 1. Klik Konsumer pada halaman katalog 2. Pilih template (tersedia 4 pilihan cover yaitu Nasional, KC, Kanwil dan Area) 3. Klik button Lanjut ke Pilih Aset | Menampilkan pilihan template katalog dan menampilkan halaman inputan katalog konsumer |  |  |  |
| 8 | Menginput form inputan data katalog Syariah - konsumer | 1. Input nama file katalog 2. klik pada card untuk memilih aset yang akan diinput 3. Centang aset yang ingin diinput 4. Klik button tambah aset | Aset yang dipilih muncul pada halaman input katalog konsumer |  |  |  |
| 9 | Expand All / Collaps All | Klik button Expand All / Collaps All | Menampilkan semua card aset sesuai dengan action expand / collaps |  |  |  |
| 10 | Expand / Collaps di setiap card aset | Klik button Expand / Collaps yang ada pada setiap card aset | Menampilkan card aset sesuai dengan action expand / collaps |  |  |  |
| 11 | Pengecekan nilai jaminan lelang, nilai pasar dan nilai likuidasi pada katalog marketing yang sebelumnya sudah di input pada halaman update katalog di menu aset | 1. Pilih aset yang sudah di input nilai jaminan lelang, nilai pasar, dan nilai likuidasi nya (nilai jaminan lelang khusus untuk pola penjualan lelang) 2. Cek nilai jaminan lelang, nilai pasar dan nilai likuidasi yang muncul harus sesuai dengan yang di input | Menampilkan nilai jaminan, nilai pasar, dan nilai likuidasi sesuai dengan yang di input pada menu aset |  |  |  |
| 12 | Melakukan input data aset yang belum lengkap | 1. Input Perkiraan nilai pasar 2. Input nilai likuidasi 3. Input nilai Jaminan 4. Input nomor telepon 5. Klik button Submit & Next | Berhasil menginput data dan menampilkan halaman generate katalog |  |  |  |
| 13 | Melakukan Simpan dan Generate Katalog Marketing Syariah - Konsumer | Klik button Generate PDF | Berhasil melakukan generate katalog syariah - konsumer |  |  |  |
| 14 | Pengecekan template katalog siap lelang | Cek template katalog siap lelang | Menampilkan katalog konsumer dengan template siap lelang yang sesuai dengan dokumen mock up katalog |  |  |  |
| 15 | Pengecekan template katalog siap jual | Cek template katalog siap jual | Menampilkan katalog konsumer dengan template siap jual yang sesuai dengan template siap jual yang sesuai dengan dokumen mock up katalog |  |  |  |
| 16 | Menampilkan tanggal generate pdf terakhir | 1. Klik menu inventory aset 2. klik submenu Katalog Marketing | Berhasil menampilkan halaman katalog marketing dan menampilkan list katalog yang sudah di buat dengan tanggal generate pdf terakhir di setiap katalog |  |  |  |
| 17 | Membuat Katalog Marketing Syariah - Komersial Proyek | 1. Klik katalog komersial 2. Klik button Kategori Proyek 3. Pilih template 4. Klik button Lanjut ke Pilih Aset | Menampilkan pilihan template katalog komersial proyek dan menampilkan halaman inputan katalog Syariah Proyek |  |  |  |
| 18 | Menginput data katalog (tema dan benefit proyek) | 1. Input tema dan benefit katalog 2. Klik button Simpan dan generate katalog | Berhasil menginput data dan menampilkan halaman generate katalog |  |  |  |
| 19 | Harga penawaran bank yang muncul adalah harga tertinggi dari beberapa skema penjualan (Cessie, jual bersama, lelang, dll) | Cek field harga penawaran bank | Menampilkan harga penawaran bank tertinggi dari beberapa skema penjualan |  |  |  |
| 20 | Ubah data harga penawaran bank | Ubah harga penawaran bank | Berhasil mengubah harga penawaran bank |  |  |  |
| 21 | Melakukan input data aset yang belum lengkap | 1. Input Perkiraan nilai pasar 2. Input nilai likuidasi 3. Input nilai Jaminan 4. Input nomor telepon 5. Klik button Submit & Next | Berhasil menginput data aset dan menampilkan halaman generate katalog |  |  |  |
| 22 | Pengecekan data benefit proyek di katalog marketing setelah di input dari halaman update katalog di menu Aset | 1. Pilih aset yang sudah di input data benefit nya di halaman update katalog 2. Cek data benefit proyek | Menampilkan data benefit proyek sesuai dengan yang di input pada halaman update katalog |  |  |  |
| 23 | Melakukan Generate Katalog Marketing Syariah - Komersial | Klik button Genertae PDF | Berhasil melakukan generate katalog marketing Syariah - komersial |  |  |  |
| 24 | Menampilkan tanggal generate pdf terakhir | 1. Klik menu inventory aset 2. klik submenu Katalog Marketing | Berhasil menampilkan halaman katalog marketing dan menampilkan list katalog yang sudah di buat dengan tanggal generate pdf terakhir di setiap katalog |  |  |  |
| 25 | Membuat Katalog Marketing Syariah - komersial Non Proyek | 1. Klik katalog komersial 2. Klik button Kategori Non Proyek 3. Pilih template 4. Klik button Lanjut ke Pilih Aset | Menampilkan pilihan template katalog dan menampilkan halaman inputan katalog Syariah komersial Non Proyek |  |  |  |
| 26 | Menginput form inputan data katalog Syariah - komersial Non Proyek | 1. Input tema katalog 2. klik pada card untuk memilih aset yang akan diinput 3. Centang aset yang ingin diinput 4. Klik button tambah aset | Berhasil menampilkan aset yang dipilih pada halaman input katalog komersial |  |  |  |
| 27 | Expand All / Collaps All | Klik button Expand All / Collaps All | Menampilkan semua card aset sesuai dengan action expand / collaps |  |  |  |
| 28 | Expand / Collaps di setiap card aset | Klik button Expand / Collaps yang ada pada setiap card aset | Menampilkan card aset sesuai dengan action expand / collaps |  |  |  |
| 29 | Pengecekan nilai jaminan lelang, nilai pasar dan nilai likuidasi pada katalog marketing yang sebelumnya sudah di input pada halaman update katalog di menu aset | 1. Pilih aset yang sudah di input nilai jaminan lelang, nilai pasar, dan nilai likuidasi nya (nilai jaminan lelang khusus untuk pola penjualan lelang) 2. Cek nilai jaminan lelang, nilai pasar dan nilai likuidasi yang muncul harus sesuai dengan yang di input | Menampilkan nilai jaminan, nilai pasar, dan nilai likuidasi sesuai dengan yang di input pada menu aset |  |  |  |
| 30 | Melakukan input data aset yang belum lengkap | 1. Input Perkiraan nilai pasar 2. Input nilai likuidasi 3. Input nilai Jaminan 4. Input nomor telepon 5. Klik button Submit & Next | Berhasil menginput data aset dan menampilkan halaman generate katalog |  |  |  |
| 31 | Melakukan Simpan dan Generate Katalog Marketing syariah - komersial | Klik button Generate PDF | Berhasil melakukan generate katalog konven - komersial |  |  |  |
| 32 | Menampilkan tanggal generate pdf terakhir | 1. Klik menu inventory aset 2. klik submenu Katalog Marketing | Berhasil menampilkan halaman katalog marketing dan menampilkan list katalog yang sudah di buat dengan tanggal generate pdf terakhir di setiap katalog |  |  |  |

# Modul Customer Management - Ticket

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka Halaman Tiket | Klik menu Customer Management - Klik Sub menu Tiket | Menampilkan Halaman Tiket |  |  |  |
| 2 | Menampilkan ticket dengan tampilan kanban | Cek tabel list data pada halaman ticket | Menampilkan data dengan tampilan kanban |  |  |  |
| 3 | Menampilkan ticket dengan tampilan list | Cek tabel list data pada halaman ticket | Menampilkan data dengan tampilan list |  |  |  |
| 4 | Mengubah Tampilan Data Tiket dari Kanban ke List | Klik Icon List yang terletak diatas data | Menampilkan Daftar Tiket dengan Tampilan List |  |  |  |
| 5 | Mengubah Tampilan Data Tiket dari List ke Kanban | Klik Icon Kanban | Menampilkan Daftar Tiket dengan Tampilan Kanban |  |  |  |
| 6 | Melihat detail data dari tampilan kanban | 1. Pilih salah satu Tiket di Staging New/On Going/Deals 2. Klik Action titik tiga di Tiket | menampilkan halaman detail data |  |  |  |
| 7 | Membuka Mini Detail Tiket | 1. Pilih salah satu Tiket di Staging New/On Going/Deals 2. Klik dua kali Tiket | Menampilkan Detail Mini Tiket |  |  |  |
| 8 | Kembali ke halaman ticket saat melihat detail data (tampilan kanban) | klik back pada browser | Menampilkan halaman ticket dengan posisi tampilan kanban |  |  |  |
| 9 | Mengunggah Lampiran ke dalam Tiket di Mini Detail | 1. Klik button +Tambah Dokumen 2. Klik upload dokumen 3. Pilih dokumen | Berhasil Mengunggah lampiran |  |  |  |
| 10 | Mengunggah lampiran dengan ukuran dokumen yang tidak sesuai ketentuan dalam mini detail | 1. Klik button +Tambah Dokumen 2. Klik upload dokumen 3. Pilih dokumen yang tidak sesuai ketentuan (max size 5 mb) | Menampilkan alert "size dokumen tidak sesuai max 5 mb" |  |  |  |
| 11 | Mengunggah lampiran dengan format file selain RAR, ZIP dan PDF dalam mini detail | 1. Klik button +Tambah Dokumen 2. Klik upload dokumen 3. Pilih dokumen yang tidak sesuai ketentuan | Menampilkan alert "format file tidak sesuai, gunakan RAR atau PDF" |  |  |  |
| 12 | Mengunduh Lampiran Tiket di Mini Detail | 1. Klik button Download pada file yang diinginkan 2. buka hasil download berupa file pdf | Berhasil mengunduh File lampiran tiket |  |  |  |
| 13 | Mengunduh Lampiran secara bulk di Mini Detail | 1. Klik button Download Semua 2. buka hasil download berupa .zip | Berhasil mengunduh File lampiran tiket secara bulk |  |  |  |
| 14 | Menghapus lampiran tiket di halaman detail | 1. klik icon Delete 2. klik button Delete | Berhasil menghapus Lampiran Tiket |  |  |  |
| 15 | Melihat detail data dari tampilan list | Klik pada icon mata pada salah satu data | menampilkan halaman detail data |  |  |  |
| 16 | Mengunggah Lampiran ke dalam Tiket di halaman detail | 1. Klik button +Tambah Dokumen 2. Klik upload dokumen 3. Pilih dokumen | Berhasil Mengunggah lampiran |  |  |  |
| 17 | Mengunggah lampiran dengan ukuran dokumen yang tidak sesuai ketentuan di halaman detail | 1. Klik button +Tambah Dokumen 2. Klik upload dokumen 3. Pilih dokumen yang tidak sesuai ketentuan (max size 5 mb) | Menampilkan alert "size dokumen tidak sesuai max 5 mb" |  |  |  |
| 18 | Mengunggah lampiran dengan format file selain RAR, ZIP dan PDF di halaman detail | 1. Klik button +Tambah Dokumen 2. Klik upload dokumen 3. Pilih dokumen yang tidak sesuai ketentuan | Menampilkan alert "format file tidak sesuai, gunakan RAR atau PDF" |  |  |  |
| 19 | Mengunduh Lampiran Tiket di halaman detail | 1. Klik button Download pada file yang diinginkan 2. buka hasil download berupa file pdf | Berhasil mengunduh File lampiran tiket |  |  |  |
| 20 | Mengunduh Lampiran secara bulk di halaman detail | 1. Klik button Download Semua 2. buka hasil download berupa .zip | Berhasil mengunduh File lampiran tiket secara bulk |  |  |  |
| 21 | Menghapus lampiran tiket di halaman detail | 1. klik icon Delete 2. klik button Delete | Berhasil mengunduh File lampiran tiket |  |  |  |
| 22 | Kembali ke halaman ticket saat melihat detail data (tampilan list) | klik back pada browser | Menampilkan halaman ticket dengan posisi tampilan list |  |  |  |
| 23 | Menyalin nomor tiket | Klik icon copy yang ada di sebelah nomor tiket | Menampilkan pop up berhasil menyalin nomor tiket |  |  |  |
| 24 | Menyalin kode aset | Klik icon copy yang ada di sebelah nomor tiket | Menampilkan pop up berhasil menyalin kode aset |  |  |  |
| 25 | Mengubah Status Staging Tiket dari New ke On Going pada tampilan Kanban | 1. Pilih tiket 2. tekan dan geser tiket dari staging new ke on going | Menampilkan Daftar perubahan Staging Status Tiket dari New ke On Going |  |  |  |
| 26 | Mengubah Status Staging Tiket dari New ke On Going pada tampilan Kanban namun belum terdapat PIC | 1. Pilih tiket 2. tekan dan geser tiket dari staging new (namun belum terdapat PIC) ke on going | Muncul pop up untuk mengisi PIC terlebih dahulu |  |  |  |
| 27 | Mengubah Status Staging Tiket dari New ke On Going pada tampilan list | 1. Pilih tiket > klik detail pada tampilan list 2. Pada halaman detail, klik "confirm to next step" 3. klik ok pada pop up | Dapat melakukan perubahan Staging Status Tiket dari New ke On Going |  |  |  |
| 28 | Mengubah Status Staging Tiket dari New ke On Going pada tampilan list namun belum terdapat PIC | 1. Pilih tiket > klik detail pada tampilan list 2. Pada halaman detail, pada kondisi data belum terdapat PIC klik "confirm to next step" 3. klik ok pada pop up | Muncul pop up untuk mengisi PIC terlebih dahulu |  |  |  |
| 29 | Mengembalikan status staging dari On going ke fase sebelumnya (New) | 1. Pilih tiket 2. tekan dan geser ke staging on going ke new | muncul pop up error "tiket tidak bisa dipindahkan ke staging sebelumnya" |  |  |  |
| 30 | Membatalkan "confirm to next step" pada staging on going | Saat di halaman detail "on going", klik confirm to next step > ketika muncul pop up klik cancel | data tidak dapat lanjut ke halaman nominal pembayaran dan kembali ke halaman detail data |  |  |  |
| 31 | Mengubah Status Staging Tiket dari On Going menjadi Deals dengan di drag dari halaman kanban | 1. Pilih salah satu Tiket di Staging On Going 2. Drag ticket dari staging on going ke deals | Muncul pop up konfirmasi dan Menampilkan halaman pengisian nominal pembayaran setelah di klik OK |  |  |  |
| 1. Input Nominal Angka 2. Klik button Submit Closing 3. Klik "OK' | Berhasil melakukan Persetujuan nominal dan Mengubah status staging tiket menjadi Deals dari tampilan kanan |  |  |  |
| 32 | Mengubah Status Staging Tiket dari On Going ke Deals (dari detail kanban/detail list) | 1. Pilih Tiket di Staging On Going > klik icon detail 2. klik button "confirm to next step" > pop up klik ok | Menampilkan pop up konfirmasi dan ke halaman untuk Input nominal pembayaran |  |  |  |
| Input nominal pembayaran Klik button Submit deals | Berhasil melakukan Persetujuan nominal dan Mengubah status staging tiket menjadi Deals dan aktivitas terupdate |  |  |  |
| 33 | tidak melakukan input nominal pembayaran | Tidak melakukan input nominal pembayaran pada halaman nominal pembayaran | Muncul alert nominal pembayaran harus di isi |  |  |  |
| 34 | Membatalkan ticket yang ada di staging on going melalui halaman kanban | 1. Pilih salah satu Tiket di Staging On Going atau Deals, Tekan dan Geser ke Staging Cancel | Menampilkan Popup untuk Input cancel tiket |  |  |  |
| 1. Input alasan status cancel dan keterangan 2. Klik button confirm Unqualified | Berhasil Membatalkan tiket dan Mengubah status staging tiket menjadi Cancel, status akan berubah menjadi cancel |  |  |  |
| 35 | Membatalkan ticket yang ada di staging on going melalui halaman detail data | 1. Pada halaman detail klik button "cancel tiket" > Input alasan status cancel dan keterangan 2. Klik button confirm Unqualified | Berhasil Membatalkan tiket dan Mengubah status staging tiket menjadi Cancel, status akan berubah menjadi cancel |  |  |  |
| 36 | Melakukan cek aktivitas tiket pada staging cancel (cencel dari on going) | Cek pada staging cancel setelah melakukan cancel data pada on going | pada log aktivitas terlihat history cancel dari ongoing ke cancel |  |  |  |
| 37 | tidak input alasan status cancel ketika membatalkan ticket yang ada di staging on going | 1. tidak melakukan Input alasan status cancel dan keterangan 2. Klik button confirm Unqualified | Muncul alert status cancel harus di isi |  |  |  |
| 38 | Mengubah Status Staging Tiket dari Staging on going ke sebelumnya pada tampilan kanban | 1. Pilih Tiket di Staging On Going 2. Tekan dan Geser tiket ke Staging sebelumnya | Menampilkan Alert Tiket tidak bisa di pindahkan ke staging sebelumnya dan Status staging tiket tidak berubah |  |  |  |
| 39 | Mengubah Status Staging Tiket dari On Going menjadi Deals di Detail Tiket dari list | 1. Pilih salah satu Tiket di Staging On Going 2. Klik Action titik tiga di Tiket 3. Klik button Continue to Next Step 4. Klik "OK" 5. Input Nominal Angka 6. Klik button Submit Closing 6. Klik "OK' | Berhasil melakukan Persetujuan nominal dan Mengubah status staging tiket menjadi Deals dari tampilan list |  |  |  |
| 40 | Membatalkan mengubah status staging dari On Going menjadi Deals dari halaman detail | Pada halaman detail ticket Klik button back pada browser | Membatalkan perubahan status staging kemudian kembali ke halaman utama menu Tiket dan status dan status staging tidak berubah (masih di on going) |  |  |  |
| 41 | Membatalkan mengubah status staging dari On Going menjadi Deals dari halaman nominal pembayaran | Pada halaman nominal Klik button back pada browser 2x | Membatalkan perubahan status staging kemudian kembali ke halaman utama menu Tiket dan status dan status staging tidak berubah (masih di on going) |  |  |  |
| 42 | Mengubah status staging dari on going ke deals dalam kondisi sudah ada ticket lain di deals dengan aset tersebut dari halaman detail data | 1. Pilih salah satu Tiket di Staging On going dan klik detail 2. Cek pada button "confirm to next step" | tidak dapat melakukan update data dari staging on going ke deals dalam kondisi sudah ada ticket lain di deals dengan aset tersebut |  |  |  |
| 43 | Mengubah status staging dari on going ke deals dalam kondisi sudah ada ticket lain di deals dengan aset tersebut dari kanban | Pindah salah satu tiket dari on going ke deals yg asetnya sudah ada di deals sebelumnya dengan nomer tiket lain | tidak dapat melakukan update data dari staging on going ke deals dalam kondisi sudah ada ticket lain di deals dengan aset tersebut |  |  |  |
| 44 | Mengubah Status Staging Tiket dari Deals menjadi Closing dengan di drag dari halaman kanban | 1. Pilih salah satu Tiket di Staging Deals 2. Drag ticket dari staging deals ke closing | Kanban tidak dapat berpindah ke closing karena proses perpindahan dari staging deals ke on going berjalan di backend (otomatis berpindah menunggu pembayaran) |  |  |  |
| 45 | Cek perubahan staging dari deals ke closing setelah melakukan pembayaran | Cek salah satu ticket yang ada pada staging deals dan lakukan payment | Berhasil melakukan pembayaran dan mengubah status staging ticket menjadi closing dan aktivitas terupdate |  |  |  |
| 46 | Membuat ticket secara manual dari menu ticket | Klik button "create ticket" pada menu ticket | Muncul mini page untuk melakukan input |  |  |  |
| 47 | Memilih Peminat pada Step 1 (Peminat) | 1. Cari Peminat 2. Pilih Peminat yang Terdaftar 3. Klik Button Next | Berhasil memilih peminat pada step 1 dan bisa ke step selanjutnya |  |  |  |
| 48 | Menginput data peminat baru pada step 1 (Peminat) | 1. Input data peminat baru 2. Klik button Next | Berhasil mengisi data peminat baru pada step 1 dan bisa ke step selanjutnya |  |  |  |
| 49 | Tidak menginput data mandatory pada step 1 (Peminat) | Tidak menginput data mandatory bertanda (\*) | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 50 | Memilih Aset yang diminati pada Step 2 (Aset) | 1. Cari Kode atau Nama Aset 2. Pilih Aset yang diminati 3. Pilih Pola penjualan yang tersedia pada Aset 4. Klik Next | Berhasil memilih Aset beserta Pola Penjualan dan bisa ke step selanjutnya |  |  |  |
| 51 | Kembali ke step 1 dari step 2 saat input tiket manual | Klik button previous dari step 2 | dapat kembali ke halaman step 1 |  |  |  |
| 52 | Tidak menginput data mandatory pada step 2 (Aset) | Tidak menginput data mandatory bertanda (\*) | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 53 | Review PIC & Sales pada Step 3 | 1. Klik Next Pada Step 2 2. Pilih Sales 3. Klik Submit aset | Berhasil memilih PIC dan Berhasil membuat tiket baru |  |  |  |
| 54 | Kembali ke step 2 dari step 3 saat input tiket manual | Klik button previous dari step 3 | dapat kembali ke halaman step 2 |  |  |  |
| 55 | Tidak menginput data mandatory pada step 3 (PIC & Sales) | Tidak menginput data mandatory bertanda (\*) | Menampilkan alert bahwa data mandatory(harus diisi) |  |  |  |
| 56 | Batal membuat ticket secara manual dari menu ticket | Klik button "create ticket" pada menu ticket > klik button cancel | Tidak membuat ticket baru dan kembali ke halaman menu ticket |  |  |  |
| 57 | Filter Data Tiket yang sesuai di Kanban | 1. Klik button Filter 2. Input nomor tiket / kode aset / pilih unit bisnis 3. Klik button Search | Menampilkan data sesuai dengan kata kunci yang di cari |  |  |  |
| 58 | Filter Data Tiket yang tidak sesuai di Kanban | 1. Input kata kunci tidak ada pada list data 2. Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 59 | Filter Data Tiket yang sesuai di List | 1. Klik button Filter 2. Input nomor tiket / kode aset / pilih unit bisnis 3. Klik button Search | Menampilkan data sesuai dengan kata kunci yang di cari |  |  |  |
| 60 | Filter Data Tiket yang tidak sesuai di List | 1. Input kata kunci tidak ada pada list data 2. Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 61 | Pagination di List tiket | Klik pagination sesuai dengan data yang ingin di tampilkan (10/page) | Menampilkan data tiket sesuai dengan pagination yang di pilih |  |  |  |

# Modul Customer Management - Leads

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman Leads | Klik menu Customer Management - Klik Sub menu Leads | Menampilkan Halaman Leads |  |  |  |
| 2 | Membukan Halaman Sub Tabel Tindak Lanjut | Klik Sub Tabel Tindak Lanjut pada halaman Leads | Menampilkan Data Tabel Leads yang berstatus Perlu Tindak Lanjut |  |  |  |
| 3 | Melakukan filter data pada sub tabel tindak lanjut | Cari data berdasarkan no pesanan atau filter data berdasarkan pola penjualan | Menampilkan data berdasarkan no pesanan dan pola penjualan yang dipilih |  |  |  |
| 4 | Melakukan filter data pada sub tabel tindak lanjut dengan data yang tidak sesuai | Cari data berdasarkan no pesanan atau pola penjualan yang tidak terdapat pada list | Tidak menampilkan data apapun |  |  |  |
| 5 | Membukan Halaman Sub Tabel Processing | Klik Sub Tabel Processing pada halaman Leads | Menampilkan Data Tabel Leads yang berstatus Processing |  |  |  |
| 6 | Melakukan filter data pada sub tabel processing | Cari data berdasarkan no pesanan atau filter data berdasarkan pola penjualan | Menampilkan data berdasarkan no pesanan dan pola penjualan yang dipilih |  |  |  |
| 7 | Melakukan filter data pada sub tabel processing dengan data yang tidak sesuai | Cari data berdasarkan no pesanan atau pola penjualan yang tidak terdapat pada list | Tidak menampilkan data apapun |  |  |  |
| 8 | Membukan Halaman Sub Tabel Terverifikasi | Klik Sub Tabel Terverifikasi pada halaman Leads | Menampilkan Data Tabel Leads yang berstatus terverifikasi |  |  |  |
| 9 | Melakukan filter data pada sub tabel terverifikasi | Cari data berdasarkan no pesanan atau filter data berdasarkan pola penjualan | Menampilkan data berdasarkan no pesanan dan pola penjualan yang dipilih |  |  |  |
| 10 | Melakukan filter data pada sub tabel terverifikasi dengan data yang tidak sesuai | Cari data berdasarkan no pesanan atau pola penjualan yang tidak terdapat pada list | Tidak menampilkan data apapun |  |  |  |
| 11 | Membukan Halaman Sub Tabel Selesai | Klik Sub Tabel Selesai pada halaman Leads | Menampilkan Data Tabel Leads yang berstatus Selesai |  |  |  |
| 12 | Melakukan filter data pada sub tabel selesai | Cari data berdasarkan no pesanan atau filter data berdasarkan pola penjualan | Menampilkan data berdasarkan no pesanan dan pola penjualan yang dipilih |  |  |  |
| 13 | Melakukan filter data pada sub tabel selesai dengan data yang tidak sesuai | Cari data berdasarkan no pesanan atau pola penjualan yang tidak terdapat pada list | Tidak menampilkan data apapun |  |  |  |
| 14 | Membukan Halaman Sub Tabel Batal | Klik Sub Tabel Batal pada halaman Leads | Menampilkan Data Tabel Leads yang berstatus Pembatalan |  |  |  |
| 15 | Melakukan filter data pada sub tabel batal | Cari data berdasarkan no pesanan atau filter data berdasarkan pola penjualan | Menampilkan semua data Leads berdasarkan no pesanan dan pola penjualan yang dipilih |  |  |  |
| 16 | Melakukan filter data pada sub tabel batal dengan data yang tidak sesuai | Cari data berdasarkan no pesanan atau pola penjualan yang tidak terdapat pada list | Tidak menampilkan data apapun |  |  |  |
| 17 | Filter semua data Leads yang sesuai | Input nomor pesanan - Pilih Filter Jenis Pola Penjualan - Klik Button Search | Menampilkan Data sesuai data secara filter yang sudah di set |  |  |  |
| 18 | Filter semua data Leads yang tidak sesuai | Input kata kunci tidak ada pada list data - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 19 | Membuka Detail Data Leads | Pilih salah satu data dan Klik button detail | Berhasil Menampilkan Detail Data Leads yang dipilih |  |  |  |
| 20 | Mencentang Konfirmasi Pola Pembelian pada halaman detail Leads | Klik centang Konfirmasi Pola Pembelian pada halaman detail Leads | Dapat melakukan centang Konfirmasi Pola Pembelian dan muncul dropdown list pola pembelian |  |  |  |
| 21 | Mencentang tindak lanjut pada halaman detail Leads | Klik centang tindak lanjut pada halaman detail Leads | Dapat melakukan centang tindak lanjut dan muncul kolom untuk mengisi catatan |  |  |  |
| 22 | Melakukan Tindak Lanjut Peminatan pada data yang baru sesuai dengan tipe pembelian yang diinput | Klik Button Tindak Lanjut pada data Leads - Mencentang tindak lanjut untuk memunculkan pola pembelian (mandatory) dan mengisi catatan (bisa dilakukan/tidak) | Muncul pilihan pola penjualan yang dipilih |  |  |  |
| Klik Button Selesai Konfirmasi dan Buat Tiket | Mengubah Status Data Leads Menjadi Terverifikasi sesuai input awal dan Tiket Terbuat di Halaman Tiket |  |  |  |
| 23 | Melakukan Tindak Lanjut Peminatan pada data yang baru dengan menyesuaikan tipe pembelian setelah konfirmasi | Klik Button Tindak Lanjut pada data Leads -- kemudian Mencentang tindak lanjut untuk memunculkan pola pembelian dan dirubah dengan pola yang baru - Mengisi catatan (bisa dilakukan/tidak) | Muncul pilihan pola penjualan yang dipilih dan dapat diubah dengan pola pembelian baru |  |  |  |
| Klik Button Selesai Konfirmasi dan Buat Tiket | Mengubah Status Data Leads Menjadi Terverifikasi dengan pola pembelian sesuai sesuai input baru dan Tiket Terbuat di Halaman Tiket |  |  |  |
| 24 | Melihat Tooltip informasi panduan pada "Tindak Lanjut" | Klik Button Tindak Lanjut pada data Leads yang berstatus tindak lanjut - Pada halaman detail, Klik Icon Informasi disamping checkbox Tindak Lanjut | Menampilkan Tooltip Informasi Panduan Tindak Lanjut |  |  |  |
| 25 | Tidak mencentang Konfirmasi Pola Pembelian | Pada halaman detail Leads yang perlu di tindak lanjut, tidak melakukan centang pada Konfirmasi Pola Pembelian | Button selesai konfirmasi & buat tiket disable |  |  |  |
| 26 | Melakukan pembatalan peminatan saat melakukan tindak lanjut | Klik Button Tindak Lanjut pada data Leads - Klik Button Batal peminatan | Muncul pop up alasan pembatalan |  |  |  |
| isi alasan > klik button batalkan | Berhasil membatalkan tindak lanjut dan kembali ke Halaman Leads |  |  |  |
| 27 | Melakukan pembatalan peminatan saat melakukan tindak lanjut tanpa mengisi alasan | Klik Button Tindak Lanjut pada data Leads - Klik Button cancel | Muncul pop up alasan pembatalan |  |  |  |
| tidak isi alasan > klik button batalkan | terdapat alert "Alasan pembatalan wajib diisi" |  |  |  |
| 28 | Mengunduh Data Leads | Klik Button Download data | Muncul pop up "data excel sedang di proses", Berhasil melakukan Mengunduh data Leads |  |  |  |
| 29 | Melihat status unduhan data | Klik titik tiga yang ada di sebelah button Download Data - Klik See Status | Menampilkan status Memproses jika sedang mengunduh data, dan menampilkan data yang sudah di unduh per hari ini dan kemarin |  |  |  |
| 30 | Pagination data Leads | Klik pagination sesuai dengan data yang ingin di tampilkan (10/page) | Menampilkan data peminat sesuai dengan pagination yang di pilih |  |  |  |

# Modul Audit Trail

| **No** | **Test Case** | **Scenario** | **Expected Result** | **Actual Result** | **Test Status (P=Passed, F=Failed)** | **Remarks** |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Membuka halaman audit trail | Klik menu Audit Trail | Menampilkan halaman Audit Trail dan menampilkan log semua menu |  |  |  |
| 2 | Mengunduh data audit trail | Klik button mengunduh data | Berhasil mengunduh data Audit Trail |  |  |  |
| 3 | Melihat status unduhan data | Klik titik tiga yang ada di sebelah button Download Data - Klik See Status | Menampilkan status Memproses jika sedang mengunduh data, dan menampilkan data yang sudah di unduh per hari ini dan kemarin |  |  |  |
| 4 | Melihat detail data audit trail | Klik button Detail | Menampilkan detail Audit Trail |  |  |  |
| 5 | Filter Data Audit Trail yang sesuai | Input nama user, Pilih Aksi, Pilih tanggal- kemudian klik button Search | Menampilkan data sesuai dengan kata kunci yang di cari |  |  |  |
| 6 | Filter Data Audit Trail yang tidak sesuai | Input kata kunci tidak ada pada list data - Klik button Search | Menampilkan tabel kosong dengan keterangan no data |  |  |  |
| 7 | Pagination data Audit Trail | Klik pagination sesuai dengan data yang ingin di tampilkan (10/page) | Menampilkan data Audit trail sesuai dengan pagination yang di pilih |  |  |  |