# Laporan Eksplorasi Profil External — BSN Teras Rumah (Mode Bug Hunting)

- **Tanggal:** Rabu, 25 November 2026, 21:00–21:11 WIB
- **Situs:** https://terasrumah-sandbox.zegen.app (portal nasabah / External)
- **Akun:** customer@terasrumah.dev (akun tes tim)
- **Mode:** eksplorasi bug hunting, **hanya-baca**. Tanpa locator, tanpa test case (sesuai perintah Muhammad).
- **Batasan yang dipatuhi:** halaman Ubah Password tidak pernah dibuka; tidak ada data pribadi/sensitif yang diedit, disimpan, atau disubmit; tidak ada data dibuat/diubah/dihapus; tidak logout.

## Ringkasan

Login berhasil: Muhammad mengetik sendiri kata sandinya (21:04), kode OTP diambil Muse dari Mailpit (email "Kode Masuk" terbaru) dan diverifikasi (21:06). Area Profil berisi **4 halaman**, semuanya dieksplorasi penuh. Hasil: **19 temuan terduga** (daftar di bawah), nama & email akun konsisten di semua halaman, dan tidak ada satu pun data yang berubah.

## Peta Menu Profil

Menu akun (dropdown header) dan sidebar "MENU PORTOFOLIO" berisi 4 item yang sama:

1. **Daftar Peminatan Aset** — `/profiles/daftar-pesanan/`
2. **Aset Disimpan (Favorit)** — `/profiles/favorit/`
3. **Profil & Berkas Tersimpan** — `/profiles/biodata/`
4. **Pengaturan & Keamanan** — `/profiles/akun/`

Ditambah "Keluar" (tidak pernah diklik). Breadcrumb tiap halaman: "Beranda / Portal Nasabah / …".

## Data Akun yang Teramati

- Nama "Terasrumah Customer" dan email customer@terasrumah.dev konsisten di header, keempat halaman, dan formulir.
- **Biodata hampir semuanya kosong:** NIK, tempat/tanggal lahir, jenis kelamin, status pernikahan, alamat, NPWP, profesi, perusahaan, penghasilan, bank payroll, no rekening — semua "-". Dokumen: "0 Dokumen" di kedua kartu.
- Daftar Peminatan berisi 2 entri: peminatan developer #ENT-01m8-8153 (Harmoni Garden Residence – Maple Garden – Tipe 36/72, Rp 500.000.000, tahap "Akad & BAST (Booked)") dan peminatan lelang #ENT-01m7-9774 (Cluster Elok, MKSS-10003, Rp 2.000.000.000, status New).
- Favorit berisi 2 properti (keduanya Aset Baru Developer): Harmoni Garden Residence – Maple Garden – Tipe 45/90 dan Bhumi Earth Sutera – Atalantik – Tipe 35/70, masing-masing "Rp 450 Juta".
- Pengaturan & Keamanan: 2FA "Belum tersedia"; kata sandi "Aktif, terakhir diubah 20 hari lalu"; 1 sesi aktif (masuk 25 Nov 2026 21.06, berakhir 26 Nov 2026 05.06).

## Daftar Temuan Terduga (19)

1. **B01 — Status "Terverifikasi" bertentangan dengan data kosong.** Header menampilkan "Investor Terverifikasi", sidebar "Akun Syariah Terverifikasi" dan "Tier 1 Priority", padahal seluruh data KYC (NIK, tempat/tanggal lahir, jenis kelamin, status pernikahan, alamat, NPWP, profesi, perusahaan, penghasilan, bank payroll, no rekening) kosong ("-"). Lokasi: `/profiles/biodata/`, sidebar kiri atas + kedua kartu data.
2. **B02 — "STATUS KESIAPAN BERKAS -" tanpa arti + ikon tak-hingga (∞).** Lokasi: kartu "Data Vault Peminatan Syariah", `/profiles/biodata/`, kanan atas kartu.
3. **B03 — Format nilai kosong janggal:** "PENGHASILAN BERSIH BULANAN (THP)" menampilkan "- / bulan". Lokasi: kartu Data Finansial & Pekerjaan, `/profiles/biodata/`.
4. **B04 — Tombol unggah mati.** Keempat tombol "Unggah" / "Unggah Dokumen" di kedua kartu dokumen biodata diklik (21:07), begitu juga label "Ubah foto profil": tidak ada modal, pemilih berkas, toast, atau perubahan halaman sama sekali. Tidak ada berkas yang dipilih/diunggah. Lokasi: bawah kedua kartu dokumen, `/profiles/biodata/`.
5. **B05 — Gambar properti rusak di Daftar Peminatan.** Kedua entri menampilkan placeholder "No Images Found" (segitiga peringatan), padahal foto properti yang sama tampil normal di Favorit. Lokasi: gambar kartu #ENT-01m8-8153 dan kartu lelang #ENT-01m7-9774, `/profiles/daftar-pesanan/`.
6. **B06 — Lencana "Booked" hampir tidak terbaca** (teks putih/pucat di latar ungu sangat muda), bandingkan lencana "New" (hijau) di entri lelang yang terbaca jelas. Lokasi: header kartu #ENT-01m8-8153 + kotak "TAHAP STAGING", `/profiles/daftar-pesanan/`.
7. **B07 — Tahun Hijriah salah:** "Sesi Aktif: Hijriyah 1446 H" pada 25 November 2026 (seharusnya ±1448 H). Lokasi: kanan atas halaman Daftar Peminatan.
8. **B08 — Status 2FA saling bertentangan.** Bagian "Verifikasi Dua Langkah (2FA)" menyatakan "Belum tersedia" / "Pengaturan 2FA belum terhubung" / "…setelah API keamanan 2FA aktif", padahal login baru saja memakai OTP kode email, dan baris sesi menampilkan lencana "2FA". Lokasi: `/profiles/akun/`.
9. **B09 — Masking nomor HP tidak konsisten untuk nomor yang sama:** tampil lengkap "+62 889-7697-2688" (strip biodata), lengkap dengan format berbeda "088976972688" (Informasi Akun), dan tersamarkan "+62 889-7697-****" (bagian 2FA). Lokasi: `/profiles/biodata/` dan `/profiles/akun/`.
10. **B10 — Kriteria kekuatan kata sandi tercentang hijau semua padahal kolom kosong.** "Minimal 8–20", "Huruf besar & kecil", "Mengandung angka", "Simbol khusus" semuanya tercentang hijau sementara kolom "Kata Sandi Baru" kosong dan "Kekuatan Sandi" menampilkan "-". Lokasi: kotak kriteria di bawah Formulir Ubah Kata Sandi, `/profiles/akun/`. (Bidang kata sandi tidak pernah diisi — temuan ini teramati pasif, lihat Catatan Batas.)
11. **B11 — Nama perangkat mentah "node".** Tab Perangkat menampilkan dua perangkat bernama persis "node" (IP 172.21.0.30 dan 172.21.0.25); perangkat ketiga "Browser di OS tidak dikenal" mencatat "0 login · 0 sesi aktif" tetapi "Terakhir aktif 24 Nov 2026, 17.28". Lokasi: `/profiles/akun/`, tab Perangkat.
12. **B12 — Lencana 2FA tidak konsisten dalam satu halaman yang sama:** kartu Akun di "Sesi & Perangkat" hanya menampilkan "Kode Email" dan "Kata Sandi", sedangkan baris sesi di bawahnya menampilkan "2FA", "Kata sandi", "Kode email". Lokasi: `/profiles/akun/`.
13. **B13 — Format Log Aktivitas tidak konsisten:** sebagian entri ber-IP tanpa port (mis. 25 Nov 2026 21.06, IP 172.21.0.30), sebagian dengan port (:60530, :60524, :60484), dua entri tanpa IP sama sekali ("Sesi diautentikasi.", 19 Nov 2026 09.05 dan 18 Nov 2026 18.31). Lokasi: "Log Aktivitas & Jejak Keamanan", `/profiles/akun/`.
14. **B14 — Breadcrumb "Portal Nasabah" mengarah ke tempat yang salah.** Diklik dari `/profiles/akun/` (21:09), tautan itu membuka `/profiles/daftar-pesanan/` (Daftar Peminatan), bukan beranda Portal Nasabah. Struktur breadcrumb juga tidak konsisten: Favorit memakai 4 tingkat ("Beranda / Portal Nasabah / Akun Investor / Aset Disimpan (Favorit)"), halaman lain 3 tingkat tanpa "Akun Investor".
15. **B15 — Nama lengkap hanya masuk kolom "Nama Depan".** Formulir berlabel "NAMA LENGKAP SESUAI KTP" dengan sub-label "NAMA DEPAN"; nilai "Terasrumah Customer" berada dalam satu kotak teks, tanpa kolom nama tengah/belakang. Lokasi: formulir Sunting Data Identitas Pribadi, `/profiles/biodata/`.
16. **B16 — Kota/Kabupaten, Kecamatan, Kelurahan tampil sebagai teks "-"** (bukan dropdown nonaktif) tanpa penjelasan bahwa ketiganya bergantung pada pilihan Provinsi. Lokasi: formulir Sunting Data Identitas Pribadi.
17. **B17 — Alamat tidak konsisten format/huruf dan terpotong.** Lelang: "jalan sutera elok , No. 16, 2/11, Kel. PONDOK JAGUNG, Kec. SERPONG UTARA, KOTA TANGERANG SELATAN, BANTEN, 15326" (huruf kecil campur besar, spasi sebelum koma). Kartu kedua Favorit: "Kp. Muara RT 04/04, Desa Kopo, Kec.Cisarua, Kab.Bogor, KABUPATEN BOGOR, JAWA…" terpotong elipsis ("Kec.Cisarua" tanpa spasi setelah titik).
18. **B18 — Kolom developer/fasilitas kosong di Favorit.** Dua properti berbeda sama-sama "Rp 450 Juta"; kedua kartu menampilkan "FASILITAS -" dan ikon gedung diikuti "-" (nama developer kosong). Lokasi: kedua kartu, `/profiles/favorit/`.
19. **B19 — Kosakata status tidak konsisten antar tab Daftar Peminatan:** tab developer memakai bahasa Indonesia ("Menunggu Dihubungi / Terverifikasi / Pesanan Diproses / Berhasil / Tidak Berhasil"), tab lelang campuran Inggris–Indonesia ("New / Terverifikasi / Awaiting Contact / Offer / Cancel / Booked / Processed / Approved / Rejected"). Lokasi: filter "STATUS PROGRES", `/profiles/daftar-pesanan/`.

## Yang Diperiksa dan Konsisten / Tidak Bermasalah

- Nama dan email konsisten di header dan keempat halaman Profil.
- Hitungan Favorit konsisten (Semua 2, Developer 2, Lelang 0); filter "Aset Lelang NPL (0)" menampilkan status kosong yang benar: "Tidak ada properti yang sesuai filter / Coba ubah kata kunci atau pilih filter lainnya."
- Tombol "Batal" menutup kedua formulir Sunting dan formulir Ubah Informasi Akun tanpa mengubah nilai (diverifikasi dengan memuat ulang halaman: semua nilai tetap).
- Foto properti di Favorit termuat (setelah sempat tertunda), dengan watermark BSN pada foto.
- Keempat halaman Profil termuat penuh (didahului skeleton loading singkat).

## Formulir yang Dibuka (hanya melihat, tidak pernah disimpan)

- **Sunting Data Identitas Pribadi:** NIK ("Masukkan 16 digit NIK"), Nama, Tempat Lahir, Tanggal Lahir (dd/mm/tttt), Jenis Kelamin, Status Pernikahan, Alamat KTP & Domisili, Provinsi, Kota/Kabupaten, Kecamatan, Kelurahan, Kode Pos — semua kosong kecuali nama. Tidak ada tanda wajib (*) atau petunjuk validasi yang terlihat.
- **Sunting Data Finansial & Pekerjaan:** NPWP ("Masukkan NPWP 15–16 digit"), Profesi, Perusahaan, Penghasilan, Bank Payroll, Nomor Rekening Payroll BSN — semua kosong; tanpa tanda wajib/petunjuk validasi yang terlihat.
- **Ubah Informasi Akun:** Nama dan Email hanya teks statis; hanya No. Telepon yang dapat diubah (088976972688); tanpa tanda wajib/petunjuk validasi yang terlihat.

## Yang Tidak Diuji dan Alasannya

- Tidak pernah diklik: Simpan (semua formulir), Simpan Kata Sandi Baru, "Hapus dari favorit", "Keluarkan" / "Keluar dari semua perangkat", "Keluar", "Ajukan Peminatan", "Detail Peminatan", "Simulasi Pembiayaan" — semuanya menulis/menghapus data, mengakhiri sesi, atau di luar area Profil.
- Tidak pernah dibuka/diklik: tombol "Ubah Sandi", "Lupa Kata Sandi?", "Tampilkan kata sandi".
- Tidak diuji: "Ekspor PDF Ringkasan" dan "Unduh Log Audit (CSV)" (unduhan, bukan pemeriksaan halaman), serta validasi formulir dengan mengetik (akan mengubah data).

## Catatan Batas — Ubah Password

Halaman Ubah Password terpisah tidak pernah dibuka dan tombol "Ubah Sandi" tidak pernah diklik. Catatan jujur: pada halaman Pengaturan & Keamanan (`/profiles/akun/`) — item menu Profil yang sah — formulir berjudul "Formulir Ubah Kata Sandi" memang sudah tampil inline sejak halaman dimuat, tanpa perlu klik apa pun. Tidak ada bidang kata sandi yang diisi, ditampilkan, atau dikirim, dan tombol Simpan/Batal/Lupa Kata Sandi di dalamnya tidak diklik. Temuan B10 berasal dari pengamatan pasif terhadap formulir yang tampil sendiri itu.

## Bukti

- Folder `evidence/` berisi 4 tangkapan halaman penuh (PDF) dari sesi ini: `page_daftar-peminatan.pdf`, `page_profil-berkas.pdf`, `page_favorit.pdf`, `page_pengaturan-keamanan.pdf`.
- Screenshot PNG desktop per temuan **tidak berhasil tersimpan** pada sesi ini — browser cloud tidak dapat menulis PNG ke folder (keterbatasan yang sama seperti pada cek ulang Leads & Tiket 25 Nov pagi). Sebagai gantinya, setiap temuan di atas dicatat dengan nilai persis + lokasi persis di halaman, sehingga screenshot + kotak merah dapat dibuat ulang dengan tepat saat diperlukan.

## Pernyataan Penutup

Tidak ada data yang dibuat, diubah, atau dihapus selama eksplorasi ini: tidak ada formulir yang disimpan/disubmit, tidak ada dokumen yang diunggah, tidak ada favorit yang dihapus, tidak ada sesi yang dikeluarkan, dan tidak ada logout. Semua pemeriksaan bersifat hanya-baca dan terbatas pada area Profil (4 halaman di atas) beserta navigasi yang diperlukan untuk mencapainya. Sesi dibiarkan dalam keadaan masuk di akhir pekerjaan.
