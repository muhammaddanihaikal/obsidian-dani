---
title: FSD BSN Lelang - 01 Alur & Flowchart Fitur Internal (Backoffice)
project: BSN Lelang
tags:
  - fsd
  - bsn
  - flow-process
  - use-case
  - internal
  - backoffice
---

# 🔄 01 - Alur & Flowchart Fitur Internal (Backoffice)

> [!IMPORTANT] Fokus Modul Internal
> Modul ini merangkum seluruh **alur proses bisnis (business workflow)** dan **use case** untuk pengguna Internal Bank (Admin Pusat, Admin Cabang, Verifikator, Approver, dan Komite Lelang).

---

## 🔀 1. Alur Proses Bisnis Utama (Core Workflows)

Berikut adalah diagram alur proses utama yang berjalan pada sistem internal BSN Lelang:

### 1.1 Flow Leads ➔ Ticket (Peminatan Aset)
Alur ketika minat nasabah (Leads) yang masuk dari web publik diverifikasi dan dikonversi menjadi Ticket tindak lanjut oleh tim internal.

![Flow Leads ke Ticket Peminatan](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_01_leads_to_ticket.png)

- **Input**: Data Leads peminat aset (Nama, Kontak, Minat Aset).
- **Proses**: Verifikasi kelayakan peminat, pengecekan ketersediaan agunan, alokasi PIC cabang/unit.
- **Output**: Ticket aktif dengan nomor tiket unik untuk penanganan lebih lanjut.

---

### 1.2 Flow Staging Ticket – Aset Lelang
Tahapan siklus hidup (staging) penanganan ticket peminatan aset lelang dari status baru hingga selesai lelang/pemenang ditetapkan.

![Flow Staging Ticket Aset Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_02_staging_ticket_aset_lelang.png)

- **Tahapan Status**:
  1. `New / Open`: Tiket baru diterima dari leads peminatan.
  2. `In Progress / Follow Up`: Petugas menghubungi nasabah, verifikasi dokumen & kesiapan uang jaminan.
  3. `Jadwal Ditetapkan`: Nasabah diarahkan mendaftar ke portal KPKNL / jadwal lelang resmi.
  4. `Pemenang Lelang`: Nasabah memenangkan lelang dan proses pelunasan berjalan.
  5. `Closed (Won / Lost)`: Tiket selesai dengan status berhasil atau batal.

---

### 1.3 Flow Staging Ticket – Aset Baru (Non-Lelang)
Alur staging untuk aset properti baru (bekerjasama dengan developer/rekanan):

![Flow Staging Ticket Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_03_staging_ticket_aset_baru.png)

- Penanganan leads peminat properti developer rekanan, pengajuan KPR/pembiayaan, survei lokasi, hingga akad jual beli.

---

### 1.4 Flow Input Asset Lelang (Wizard 4 Tahap)
Proses input dan validasi data aset lelang baru ke dalam sistem sebelum diajukan approval:

![Flow Input Asset Lelang Wizard Bagian 1](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_04a_input_asset_lelang_wizard_p1.png)
![Flow Input Asset Lelang Wizard Bagian 2](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_04b_input_asset_lelang_wizard_p2.png)
![Flow Input Asset Lelang Wizard Bagian 3](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_04c_input_asset_lelang_wizard_p3.png)

- **Tahap 1 - Data Pokok Properti**: Jenis aset, lokasi, nomor agunan/CIF, nilai limit lelang, uang jaminan.
- **Tahap 2 - Dokumen Legalitas**: Sertifikat (SHM/SHGB), IMB/PBG, SPPT PBB, surat persetujuan lelang KPKNL.
- **Tahap 3 - Penilaian & Kondisi**: Hasil appraisal/taksasi, kondisi fisik bangunan, fasilitas air/listrik.
- **Tahap 4 - Media & Foto**: Upload foto tampak depan, dalam, denah lokasi, dan video virtual tour.

---

### 1.5 Flow Input Asset Baru
Alur input properti baru dari developer mitra:

![Flow Input Asset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_05_input_asset_baru.png)

---

### 1.6 Flow Approval Request (Persetujuan Berjenjang)
Alur validasi dan otorisasi aset sebelum tayang di katalog publik:

![Flow Approval Request Bagian 1](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_06a_approval_request_p1.png)
![Flow Approval Request Bagian 2](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_06b_approval_request_p2.png)

- **Checker / Reviewer**: Memeriksa kelengkapan berkas dan kepatuhan data limit lelang.
- **Approver**: Menyetujui atau menolak dengan catatan perbaikan (*Return to Maker*).
- **Notifikasi**: Sistem mengirimkan push notifikasi dan email otomatis ke pihak terkait.

---

### 1.7 Flow Publish & Unpublish Aset
Alur penayangan aset ke halaman publik website atau penarikan aset dari peredaran jika sudah laku/ada sengketa hukum:

![Flow Publish dan Unpublish](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_08_publish_unpublish.png)

---

## 📱 2. Daftar Use Case & Antarmuka Internal

### 2.1 Autentikasi & Login
- **Use Case**: ![Use Case Login Internal](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_01_use_case_login_autentikasi_internal.png)
- **Tampilan UI**: ![UI Login Internal](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_01_login.png)

---

### 2.2 Dashboard & Overview
- **Aset Lelang**:
  - Use Case: ![Use Case Dashboard Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_02_use_case_dashboard_overview_-_aset_lelang.png)
  - UI Mockup: ![UI Dashboard Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_02_dashboard_overview_-_aset_lelang.png)
- **Aset Baru**:
  - Use Case: ![Use Case Dashboard Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_03_use_case_dashboard_overview_-_aset_baru.png)
  - UI Mockup: ![UI Dashboard Aset Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_03_dashboard_overview_-_aset_baru.png)

---

### 2.3 Customer Management (Leads & Ticket)
- **Leads Aset Lelang**:
  - Use Case: ![Use Case Leads Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_04_use_case_customer_management_-_leads_-_aset_lelang.png)
  - UI Mockup: ![UI Leads Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_04_customer_management_-_leads_-_aset_lelang.png)
- **Leads Aset Baru**:
  - Use Case: ![Use Case Leads Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_05_use_case_customer_management_-_leads_-_aset_baru.png)
  - UI Mockup: ![UI Leads Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_05_customer_management_-_leads_-_aset_baru.png)
- **Ticket Aset Lelang**:
  - Use Case: ![Use Case Ticket Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_06_use_case_customer_management_-_ticket_-_aset_lelang.png)
  - UI Mockup: ![UI Ticket Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_06_customer_management_-_ticket_-_aset_lelang.png)
- **Ticket Aset Baru**:
  - Use Case: ![Use Case Ticket Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_07_use_case_customer_management_-_ticket_-_aset_baru.png)
  - UI Mockup: ![UI Ticket Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_07_customer_management_-_ticket_-_aset_baru.png)

---

### 2.4 Stock Management & Katalog Marketing
- **Stock Aset Lelang**:
  - Use Case: ![Use Case Stock Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_08_use_case_stock_management_-_aset_lelang.png)
  - UI Mockup: ![UI Stock Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_08_stock_management_-_aset_lelang.png)
- **Stock Aset Baru**:
  - Use Case: ![Use Case Stock Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_09_use_case_stock_management_-_aset_baru.png)
  - UI Mockup: ![UI Stock Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_09_stock_management_-_aset_baru.png)
- **Katalog Marketing**:
  - Lelang Use Case: ![Use Case Katalog Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_10_use_case_katalog_marketing_-_aset_lelang.png) | UI: ![UI Katalog Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_10_katalog_marketing_-_aset_lelang.png)
  - Aset Baru Use Case: ![Use Case Katalog Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_11_use_case_katalog_marketing_-_aset_baru.png) | UI: ![UI Katalog Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_11_katalog_marketing_-_aset_baru.png)

---

### 2.5 Sold Out, Favorit & Investor
- **Sold Out Aset**:
  - Use Case: ![Use Case Sold Out](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_12_use_case_sold_out_aset.png) | UI: ![UI Sold Out](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_12_sold_out_aset.png)
- **Favorit Aset**:
  - Lelang Use Case: ![Use Case Favorit Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_13_use_case_favorit_-_aset_lelang.png) | UI: ![UI Favorit Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_13_favorit_-_aset_lelang.png)
  - Aset Baru Use Case: ![Use Case Favorit Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_14_use_case_favorit_-_aset_baru.png) | UI: ![UI Favorit Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_14_favorit_-_aset_baru.png)
- **Investor**:
  - Lelang Use Case: ![Use Case Investor Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_15_use_case_investor_-_aset_lelang.png) | UI: ![UI Investor Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_15_investor_-_aset_lelang.png)
  - Aset Baru Use Case: ![Use Case Investor Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_16_use_case_investor_-_aset_baru.png) | UI: ![UI Investor Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_16_investor_-_aset_baru.png)

---

### 2.6 Approval Aset & Pengelolaan Developer
- **Approval Aset Lelang**:
  - Use Case: ![Use Case Approval Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_17_use_case_approval_aset_-_aset_lelang.png) | UI: ![UI Approval Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_17_approval_aset_-_aset_lelang.png)
- **Approval Aset Baru**:
  - Use Case: ![Use Case Approval Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_18_use_case_approval_aset_-_aset_baru.png) | UI: ![UI Approval Baru](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_18_approval_aset_-_aset_baru.png)
- **Pengelolaan Developer**:
  - List Developer: ![Use Case List Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_19_use_case_developer_-_list_developer.png) | UI: ![UI List Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_19_developer_-_list_developer.png)
  - Dashboard Developer: ![Use Case Dashboard Dev](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_20_use_case_developer_-_dashboard_developer.png) | UI: ![UI Dashboard Dev](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_21_developer_-_dashboard_developer.jpg)
  - Approval Developer: ![Use Case Approval Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_21_use_case_developer_-_approval_developer.png) | UI: ![UI Approval Developer](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_20_developer_-_approval_developer.png)

---

### 2.7 Media & Informasi
- **FAQ**: ![Use Case Media FAQ](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_22_media_information_-_faq.png) | UI: ![UI Media FAQ]()
- **Article**: ![Use Case Media Article](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_23_media_information_-_article.png) | UI: ![UI Media Article]()
- **Banner Setting**: ![Use Case Banner Setting](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_24_media_information_-_banner_setting.png) | UI: ![UI Banner Setting]()

---

### 2.8 User Management
- **User**: ![Use Case User](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_25_use_case_user_management_-_user.png) | UI: ![UI User]()
- **Role**: ![Use Case Role](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_26_use_case_user_management_-_role.png) | UI: ![UI Role]()
- **User External**: ![Use Case User External](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_27_use_case_user_management_-_user_external.png) | UI: ![UI User External]()
- **User Block**: ![Use Case User Block](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_28_use_case_user_management_-_user_block.png) | UI: ![UI User Block]()

---

### 2.9 Office Management & Audit Log
- **Tipe Kantor**: ![Use Case Tipe Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_29_use_case_office_management_-_tipe_kantor.png) | UI: ![UI Tipe Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_28_office_management_-_tipe_kantor.png)
- **Data Kantor**: ![Use Case Data Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_30_use_case_office_management_-_data_kantor.png) | UI: ![UI Data Kantor](file:///D:/Project/BSN/Fase%201/FSD/assets/01_ui_internal/ui_internal_29_office_management_-_data_kantor.png)
- **KPKNL**: ![Use Case KPKNL](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_31_use_case_office_management_-_kpknl.png) | UI: ![UI KPKNL]()
- **Audit Trail**: ![Use Case Audit Trail](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_32_use_case_audit_trail.png) | UI: ![UI Audit Trail]()
- **Audit Log**: ![Use Case Audit Log](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_33_use_case_audit_log.png) | UI: ![UI Audit Log]()
- **Notifikasi**: ![Use Case Notifikasi](file:///D:/Project/BSN/Fase%201/FSD/assets/03_flow_usecase_internal/flow_usecase_internal_36_use_case_notifikasi.png) | UI: ![UI Notifikasi]()
- **Akun**: UI: ![UI Akun]()
