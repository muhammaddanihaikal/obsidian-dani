# Testing Log - Lead Generation (BTN Smart Mobile)

Catatan pengetesan fitur Lead Generation / Buat Prospek pada aplikasi BTN Smart Mobile (build Firebase baru).

---

## 📌 Rangkuman Flow Bisnis Baru (#refactor Hully)
Validasi CIF kelolaan via `POST /api/v2/lead_generation/check_managed_cif` (auth).

### 3 Field Response:
1. `applicable`: Apakah aturan kelolaan berlaku untuk user ini?
2. `cif_exists`: Apakah nomor CIF benar-benar ada di core banking?
3. `is_managed`: Apakah nasabah tersebut kelolaan user ini di tahun berjalan?

### Aturan Validasi:
- **NTB**: Validasi CIF **tidak berlaku** (`applicable: false`, `cif_exists: null`, `is_managed: null`) → Langsung LOLOS.
- **ETB**:
  - Tanpa sales code aktif → Skip validasi (`applicable: false`).
  - Punya sales code aktif:
    - CIF tidak ada di core banking → Ditolak (*"CIF tidak ditemukan pada sistem."*).
    - CIF ada tapi bukan kelolaan sendiri → Ditolak (*"CIF tersebut tidak terdaftar sebagai CIF kelolaan Anda untuk periode tahun berjalan."*).
    - CIF ada & kelolaan sendiri → **LOLOS**.

---

## 📋 Status Pengetesan (QA)

### NTB:
- [x] **Funding NTB (Individu)** (Reguler: Aman | Referral: Bug self-referral)
- [x] **Lending NTB (Individu)** (Reguler: Bug Step 4 PKS | Referral: Bug self-referral)
- [x] **Funding NTB (Lembaga)** (Reguler: Aman | Referral: Bug self-referral)
- [x] **Lending NTB (Lembaga)** (Reguler: Bug Step 4 PKS | Referral: Bug self-referral)

### ETB:
- [ ] **Funding ETB (Individu & Lembaga)** (Pending - menunggu penjelasan/data dari tim)
- [ ] **Lending ETB (Individu & Lembaga)** (Pending - menunggu penjelasan/data dari tim)

---

## ⚠️ Bug Report / Isu Temuan

> **[BUG] [Mobile] Lending NTB (Individu & Lembaga) - Step 4: Issue Inputan Developer PKS**
> 
> * **Platform**: Mobile (Build Firebase)
> * **Menu / Flow**: Lead Generation → Lending → NTB (Individu & Lembaga) → Step 4
> * **Deskripsi**:
>   1. Inputan "Apakah prospek merupakan developer (PKS)?" default-nya masih "Ya".
>   2. Saat opsi diubah ke "Tidak", komponen inputan malah hilang.
>   *(Terjadi pada kedua tipe prospek: Individu maupun Lembaga)*
> * **Expected**: Default harusnya "Tidak" (sesuai web) dan inputan tidak hilang saat dipilih.
> * **Actual**: Default masih "Ya", dan saat klik "Tidak" inputan menghilang.
> * **Evidence**:
>   * Web (Default Tidak): https://prnt.sc/imzyZE0Hx-m8
>   * Mobile (Glitch hilang): https://prnt.sc/Uf9PaxB_srgr

<br>

> **[BUG] [Mobile] NTB Referral (Individu & Lembaga): Sales Bisa Memilih Akunnya Sendiri**
> 
> * **Platform**: Mobile (Build Firebase)
> * **Menu / Flow**: Lead Generation → Funding & Lending → NTB Referral (Individu & Lembaga)
> * **Deskripsi**: Pada dropdown "Nama Sales Referal", nama sales yang sedang login masih muncul dan bisa dipilih sebagai referral (terjadi di prospek Individu maupun Lembaga).
> * **Expected**: Akun sales yang sedang login di-exclude/hide dari list dropdown (sesuai web).
> * **Actual**: Nama sales sendiri masih muncul dan bisa dipilih.
> * **Evidence**:
>   * Lending: https://prnt.sc/Xegja9b5iKtq
>   * Funding: https://prnt.sc/XDXlu6j9d3ru



