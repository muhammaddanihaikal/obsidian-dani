---
title: FSD BSN Lelang - 03 Matriks Fitur & Hak Akses Role (CRUD)
project: BSN Lelang
tags:
  - fsd
  - bsn
  - role
  - acl
  - matrix
  - crud
---

# 🔐 03 - Matriks Fitur & Hak Akses Role (CRUD)

> [!NOTE] Matriks Hak Akses Lengkap (505 Pemetaan)
> Tabel ini mendefinisikan secara ketat hak akses **Create (C)**, **Read (R)**, **Update (U)**, dan **Delete (D)** untuk setiap peran (*Role*) dalam aplikasi BSN Lelang.

---

## 👥 Definisi Peran (Roles)
1. **Admin Pusat (Aset Lelang / Aset Baru)**: Pengelola penuh data aset tingkat kantor pusat, persetujuan dan publish aset.
2. **Admin Cabang (Aset Lelang / Aset Baru)**: Pengelola input data aset tingkat kantor cabang.
3. **Verifikator / Approver**: Pejabat yang berwenang meninjau dan menyetujui penayangan aset.
4. **Developer**: Pengguna mitra pengembang untuk input stok unit dan leads peminat.
5. **Nasabah / User External**: Pengguna publik pembeli atau investor properti.

---

## 📊 Matriks Hak Akses (C / R / U / D)

| No | Fitur / Menu | Role / Group | Akses (C/R/U/D) |
| --- | --- | --- | --- |
| 1 | Dashboard / Overview – Aset Lelang | Admin Pusat (Aset Lelang) | CRUD |
| 1 | Dashboard / Overview – Aset Lelang | Admin Pusat (Aset Baru) | - |
| 1 | Dashboard / Overview – Aset Lelang | Helpdesk (Aset Llelang) | R |
| 1 | Dashboard / Overview – Aset Lelang | Helpdesk (Aset Baru) | - |
| 1 | Dashboard / Overview – Aset Lelang | FSO (Aset Baru) | - |
| 1 | Dashboard / Overview – Aset Lelang | CWO (Aset Lelang) | R |
| 1 | Dashboard / Overview – Aset Lelang | DBM Supporting (Aset Lelang) | R |
| 1 | Dashboard / Overview – Aset Lelang | Nasabah | - |
| 1 | Dashboard / Overview – Aset Lelang | Developer | - |
| 2 | Dashboard / Overview – Aset Baru | Admin Pusat (Aset Lelang) | - |
| 2 | Dashboard / Overview – Aset Baru | Admin Pusat (Aset Baru) | CRUD |
| 2 | Dashboard / Overview – Aset Baru | Helpdesk (Aset Llelang) | - |
| 2 | Dashboard / Overview – Aset Baru | Helpdesk (Aset Baru) | R |
| 2 | Dashboard / Overview – Aset Baru | FSO (Aset Baru) | R |
| 2 | Dashboard / Overview – Aset Baru | CWO (Aset Lelang) | - |
| 2 | Dashboard / Overview – Aset Baru | DBM Supporting (Aset Lelang) | - |
| 2 | Dashboard / Overview – Aset Baru | Nasabah | - |
| 2 | Dashboard / Overview – Aset Baru | Developer | - |
| 3 | Customer Management – Leads (Aset Lelang) | Admin Pusat (Aset Lelang) | CRUD |
| 3 | Customer Management – Leads (Aset Lelang) | Admin Pusat (Aset Baru) | - |
| 3 | Customer Management – Leads (Aset Lelang) | Helpdesk (Aset Llelang) | R |
| 3 | Customer Management – Leads (Aset Lelang) | Helpdesk (Aset Baru) | - |
| 3 | Customer Management – Leads (Aset Lelang) | FSO (Aset Baru) | - |
| 3 | Customer Management – Leads (Aset Lelang) | CWO (Aset Lelang) | R |
| 3 | Customer Management – Leads (Aset Lelang) | DBM Supporting (Aset Lelang) | - |
| 3 | Customer Management – Leads (Aset Lelang) | Nasabah | - |
| 3 | Customer Management – Leads (Aset Lelang) | Developer | - |
| 4 | Customer Management – Leads (Aset Baru) | Admin Pusat (Aset Lelang) | - |
| 4 | Customer Management – Leads (Aset Baru) | Admin Pusat (Aset Baru) | CRUD |
| 4 | Customer Management – Leads (Aset Baru) | Helpdesk (Aset Llelang) | - |
| 4 | Customer Management – Leads (Aset Baru) | Helpdesk (Aset Baru) | R |
| 4 | Customer Management – Leads (Aset Baru) | FSO (Aset Baru) | R |
| 4 | Customer Management – Leads (Aset Baru) | CWO (Aset Lelang) | - |
| 4 | Customer Management – Leads (Aset Baru) | DBM Supporting (Aset Lelang) | - |
| 4 | Customer Management – Leads (Aset Baru) | Nasabah | - |
| 4 | Customer Management – Leads (Aset Baru) | Developer | - |
| 5 | Customer Management – Ticket (Aset Lelang) | Admin Pusat (Aset Lelang) | R |
| 5 | Customer Management – Ticket (Aset Lelang) | Admin Pusat (Aset Baru) | - |
| 5 | Customer Management – Ticket (Aset Lelang) | Helpdesk (Aset Llelang) | - |
| 5 | Customer Management – Ticket (Aset Lelang) | Helpdesk (Aset Baru) | - |
| 5 | Customer Management – Ticket (Aset Lelang) | FSO (Aset Baru) | - |
| 5 | Customer Management – Ticket (Aset Lelang) | CWO (Aset Lelang) | RUD |
| 5 | Customer Management – Ticket (Aset Lelang) | DBM Supporting (Aset Lelang) | - |
| 5 | Customer Management – Ticket (Aset Lelang) | Nasabah | - |
| 5 | Customer Management – Ticket (Aset Lelang) | Developer | - |
| 6 | Customer Management – Ticket (Aset Baru) | Admin Pusat (Aset Lelang) | - |
| 6 | Customer Management – Ticket (Aset Baru) | Admin Pusat (Aset Baru) | R |
| 6 | Customer Management – Ticket (Aset Baru) | Helpdesk (Aset Llelang) | - |
| 6 | Customer Management – Ticket (Aset Baru) | Helpdesk (Aset Baru) | - |
| 6 | Customer Management – Ticket (Aset Baru) | FSO (Aset Baru) | RUD |
| 6 | Customer Management – Ticket (Aset Baru) | CWO (Aset Lelang) | - |
| 6 | Customer Management – Ticket (Aset Baru) | DBM Supporting (Aset Lelang) | - |
| 6 | Customer Management – Ticket (Aset Baru) | Nasabah | - |
| 6 | Customer Management – Ticket (Aset Baru) | Developer | - |
| 7 | Stock Management – Aset Lelang | Admin Pusat (Aset Lelang) | CRUD |
| 7 | Stock Management – Aset Lelang | Admin Pusat (Aset Baru) | - |
| 7 | Stock Management – Aset Lelang | Helpdesk (Aset Llelang) | - |
| 7 | Stock Management – Aset Lelang | Helpdesk (Aset Baru) | - |
| 7 | Stock Management – Aset Lelang | FSO (Aset Baru) | - |
| 7 | Stock Management – Aset Lelang | CWO (Aset Lelang) | CRUD |
| 7 | Stock Management – Aset Lelang | DBM Supporting (Aset Lelang) | - |
| 7 | Stock Management – Aset Lelang | Nasabah | - |
| 7 | Stock Management – Aset Lelang | Developer | - |
| 8 | Stock Management – Aset Lelang | Admin Pusat (Aset Lelang) | - |
| 8 | Stock Management – Aset Lelang | Admin Pusat (Aset Baru) | CRUD |
| 8 | Stock Management – Aset Lelang | Helpdesk (Aset Llelang) | - |
| 8 | Stock Management – Aset Lelang | Helpdesk (Aset Baru) | - |
| 8 | Stock Management – Aset Lelang | FSO (Aset Baru) | CRUD |
| 8 | Stock Management – Aset Lelang | CWO (Aset Lelang) | - |
| 8 | Stock Management – Aset Lelang | DBM Supporting (Aset Lelang) | - |
| 8 | Stock Management – Aset Lelang | Nasabah | - |
| 8 | Stock Management – Aset Lelang | Developer | - |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | Admin Pusat (Aset Lelang) | CRUD |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | Admin Pusat (Aset Baru) | - |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | Helpdesk (Aset Llelang) | - |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | Helpdesk (Aset Baru) | - |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | FSO (Aset Baru) | - |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | CWO (Aset Lelang) | CRUD |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | DBM Supporting (Aset Lelang) | CRU |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | Nasabah | R |
| 9 | Stock Management – Katalog Marketing (Aset Lelang) | Developer | - |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | Admin Pusat (Aset Lelang) | - |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | Admin Pusat (Aset Baru) | CRUD |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | Helpdesk (Aset Llelang) | - |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | Helpdesk (Aset Baru) | - |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | FSO (Aset Baru) | CRUD |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | CWO (Aset Lelang) | - |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | DBM Supporting (Aset Lelang) | - |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | Nasabah | - |
| 10 | Stock Management – Katalog Marketing (Aset Baru) | Developer | - |
| 11 | Stock Management – Sold Out Aset | Admin Pusat (Aset Lelang) | CRUD |
| 11 | Stock Management – Sold Out Aset | Admin Pusat (Aset Baru) | CRUD |
| 11 | Stock Management – Sold Out Aset | Helpdesk (Aset Llelang) | - |
| 11 | Stock Management – Sold Out Aset | Helpdesk (Aset Baru) | - |
| 11 | Stock Management – Sold Out Aset | FSO (Aset Baru) | R |
| 11 | Stock Management – Sold Out Aset | CWO (Aset Lelang) | R |
| 11 | Stock Management – Sold Out Aset | DBM Supporting (Aset Lelang) | R |
| 11 | Stock Management – Sold Out Aset | Nasabah | - |
| 11 | Stock Management – Sold Out Aset | Developer | - |
| 12 | Stock Management – Favorit (Aset Lelang) | Admin Pusat (Aset Lelang) | CRUD |
| 12 | Stock Management – Favorit (Aset Lelang) | Admin Pusat (Aset Baru) | - |
| 12 | Stock Management – Favorit (Aset Lelang) | Helpdesk (Aset Llelang) | - |
| 12 | Stock Management – Favorit (Aset Lelang) | Helpdesk (Aset Baru) | - |
| 12 | Stock Management – Favorit (Aset Lelang) | FSO (Aset Baru) | - |
| 12 | Stock Management – Favorit (Aset Lelang) | CWO (Aset Lelang) | - |
| 12 | Stock Management – Favorit (Aset Lelang) | DBM Supporting (Aset Lelang) | - |
| 12 | Stock Management – Favorit (Aset Lelang) | Nasabah | - |
| 12 | Stock Management – Favorit (Aset Lelang) | Developer | - |
| 13 | Stock Management – Favorit (Aset baru) | Admin Pusat (Aset Lelang) | - |
| 13 | Stock Management – Favorit (Aset baru) | Admin Pusat (Aset Baru) | CRUD |
| 13 | Stock Management – Favorit (Aset baru) | Helpdesk (Aset Llelang) | - |
| 13 | Stock Management – Favorit (Aset baru) | Helpdesk (Aset Baru) | - |
| 13 | Stock Management – Favorit (Aset baru) | FSO (Aset Baru) | - |
| 13 | Stock Management – Favorit (Aset baru) | CWO (Aset Lelang) | - |
| 13 | Stock Management – Favorit (Aset baru) | DBM Supporting (Aset Lelang) | - |
| 13 | Stock Management – Favorit (Aset baru) | Nasabah | - |
| 13 | Stock Management – Favorit (Aset baru) | Developer | - |
| 14 | Stock Management – Investor (Aset Lelang) | Admin Pusat (Aset Lelang) | CRUD |
| 14 | Stock Management – Investor (Aset Lelang) | Admin Pusat (Aset Baru) | - |
| 14 | Stock Management – Investor (Aset Lelang) | Helpdesk (Aset Llelang) | - |
| 14 | Stock Management – Investor (Aset Lelang) | Helpdesk (Aset Baru) | - |
| 14 | Stock Management – Investor (Aset Lelang) | FSO (Aset Baru) | - |
| 14 | Stock Management – Investor (Aset Lelang) | CWO (Aset Lelang) | R |
| 14 | Stock Management – Investor (Aset Lelang) | DBM Supporting (Aset Lelang) | - |
| 14 | Stock Management – Investor (Aset Lelang) | Nasabah | - |
| 14 | Stock Management – Investor (Aset Lelang) | Developer | - |
| 15 | Stock Management – Investor (Aset Baru) | Admin Pusat (Aset Lelang) | - |
| 15 | Stock Management – Investor (Aset Baru) | Admin Pusat (Aset Baru) | CRUD |
| 15 | Stock Management – Investor (Aset Baru) | Helpdesk (Aset Llelang) | - |
| 15 | Stock Management – Investor (Aset Baru) | Helpdesk (Aset Baru) | - |
| 15 | Stock Management – Investor (Aset Baru) | FSO (Aset Baru) | R |
| 15 | Stock Management – Investor (Aset Baru) | CWO (Aset Lelang) | - |
| 15 | Stock Management – Investor (Aset Baru) | DBM Supporting (Aset Lelang) | - |
| 15 | Stock Management – Investor (Aset Baru) | Nasabah | - |
| 15 | Stock Management – Investor (Aset Baru) | Developer | - |
| 16 | Approval - Aset Lelang | Admin Pusat (Aset Lelang) | - |
| 16 | Approval - Aset Lelang | Admin Pusat (Aset Baru) | - |
| 16 | Approval - Aset Lelang | Helpdesk (Aset Llelang) | - |
| 16 | Approval - Aset Lelang | Helpdesk (Aset Baru) | - |
| 16 | Approval - Aset Lelang | FSO (Aset Baru) | - |
| 16 | Approval - Aset Lelang | CWO (Aset Lelang) | - |
| 16 | Approval - Aset Lelang | DBM Supporting (Aset Lelang) | CRUD |
| 16 | Approval - Aset Lelang | Nasabah | - |
| 16 | Approval - Aset Lelang | Developer | - |
| 17 | Approval - Aset Baru | Admin Pusat (Aset Lelang) | - |
| 17 | Approval - Aset Baru | Admin Pusat (Aset Baru) | CRUD |
| 17 | Approval - Aset Baru | Helpdesk (Aset Llelang) | - |
| 17 | Approval - Aset Baru | Helpdesk (Aset Baru) | - |
| 17 | Approval - Aset Baru | FSO (Aset Baru) | - |
| 17 | Approval - Aset Baru | CWO (Aset Lelang) | - |
| 17 | Approval - Aset Baru | DBM Supporting (Aset Lelang) | - |
| 17 | Approval - Aset Baru | Nasabah | - |
| 17 | Approval - Aset Baru | Developer | - |
| 18 | Developer - List Developer | Admin Pusat (Aset Lelang) | - |
| 18 | Developer - List Developer | Admin Pusat (Aset Baru) | CRUD |
| 18 | Developer - List Developer | Helpdesk (Aset Llelang) | - |
| 18 | Developer - List Developer | Helpdesk (Aset Baru) | - |
| 18 | Developer - List Developer | FSO (Aset Baru) | - |
| 18 | Developer - List Developer | CWO (Aset Lelang) | - |
| 18 | Developer - List Developer | DBM Supporting (Aset Lelang) | - |
| 18 | Developer - List Developer | Nasabah | - |
| 18 | Developer - List Developer | Developer | - |
| 19 | Developer - Approval Developer | Admin Pusat (Aset Lelang) | - |
| 19 | Developer - Approval Developer | Admin Pusat (Aset Baru) | CRUD |
| 19 | Developer - Approval Developer | Helpdesk (Aset Llelang) | - |
| 19 | Developer - Approval Developer | Helpdesk (Aset Baru) | - |
| 19 | Developer - Approval Developer | FSO (Aset Baru) | - |
| 19 | Developer - Approval Developer | CWO (Aset Lelang) | - |
| 19 | Developer - Approval Developer | DBM Supporting (Aset Lelang) | - |
| 19 | Developer - Approval Developer | Nasabah | - |
| 19 | Developer - Approval Developer | Developer | - |
| 20 | Developer - Dashboard Developer | Admin Pusat (Aset Lelang) | - |
| 20 | Developer - Dashboard Developer | Admin Pusat (Aset Baru) | CRUD |
| 20 | Developer - Dashboard Developer | Helpdesk (Aset Llelang) | - |
| 20 | Developer - Dashboard Developer | Helpdesk (Aset Baru) | - |
| 20 | Developer - Dashboard Developer | FSO (Aset Baru) | - |
| 20 | Developer - Dashboard Developer | CWO (Aset Lelang) | - |
| 20 | Developer - Dashboard Developer | DBM Supporting (Aset Lelang) | - |
| 20 | Developer - Dashboard Developer | Nasabah | - |
| 20 | Developer - Dashboard Developer | Developer | - |
| 21 | Media & Management - FAQ | Admin Pusat (Aset Lelang) | CRUD |
| 21 | Media & Management - FAQ | Admin Pusat (Aset Baru) | CRUD |
| 21 | Media & Management - FAQ | Helpdesk (Aset Llelang) | - |
| 21 | Media & Management - FAQ | Helpdesk (Aset Baru) | - |
| 21 | Media & Management - FAQ | FSO (Aset Baru) | - |
| 21 | Media & Management - FAQ | CWO (Aset Lelang) | - |
| 21 | Media & Management - FAQ | DBM Supporting (Aset Lelang) | - |
| 21 | Media & Management - FAQ | Nasabah | - |
| 21 | Media & Management - FAQ | Developer | - |
| 22 | Media & Management – Article | Admin Pusat (Aset Lelang) | CRUD |
| 22 | Media & Management – Article | Admin Pusat (Aset Baru) | CRUD |
| 22 | Media & Management – Article | Helpdesk (Aset Llelang) | - |
| 22 | Media & Management – Article | Helpdesk (Aset Baru) | - |
| 22 | Media & Management – Article | FSO (Aset Baru) | - |
| 22 | Media & Management – Article | CWO (Aset Lelang) | - |
| 22 | Media & Management – Article | DBM Supporting (Aset Lelang) | - |
| 22 | Media & Management – Article | Nasabah | - |
| 22 | Media & Management – Article | Developer | - |
| 23 | Media & Management – Banner Setting | Admin Pusat (Aset Lelang) | CRUD |
| 23 | Media & Management – Banner Setting | Admin Pusat (Aset Baru) | CRUD |
| 23 | Media & Management – Banner Setting | Helpdesk (Aset Llelang) | - |
| 23 | Media & Management – Banner Setting | Helpdesk (Aset Baru) | - |
| 23 | Media & Management – Banner Setting | FSO (Aset Baru) | - |
| 23 | Media & Management – Banner Setting | CWO (Aset Lelang) | - |
| 23 | Media & Management – Banner Setting | DBM Supporting (Aset Lelang) | - |
| 23 | Media & Management – Banner Setting | Nasabah | - |
| 23 | Media & Management – Banner Setting | Developer | - |
| 24 | User Management - User | Admin Pusat (Aset Lelang) | CRUD |
| 24 | User Management - User | Admin Pusat (Aset Baru) | CRUD |
| 24 | User Management - User | Helpdesk (Aset Llelang) | - |
| 24 | User Management - User | Helpdesk (Aset Baru) | - |
| 24 | User Management - User | FSO (Aset Baru) | - |
| 24 | User Management - User | CWO (Aset Lelang) | - |
| 24 | User Management - User | DBM Supporting (Aset Lelang) | - |
| 24 | User Management - User | Nasabah | - |
| 24 | User Management - User | Developer | - |
| 25 | User Management - Role | Admin Pusat (Aset Lelang) | CRUD |
| 25 | User Management - Role | Admin Pusat (Aset Baru) | CRUD |
| 25 | User Management - Role | Helpdesk (Aset Llelang) | - |
| 25 | User Management - Role | Helpdesk (Aset Baru) | - |
| 25 | User Management - Role | FSO (Aset Baru) | - |
| 25 | User Management - Role | CWO (Aset Lelang) | - |
| 25 | User Management - Role | DBM Supporting (Aset Lelang) | - |
| 25 | User Management - Role | Nasabah | - |
| 25 | User Management - Role | Developer | - |
| 26 | User Management – User External | Admin Pusat (Aset Lelang) | CRUD |
| 26 | User Management – User External | Admin Pusat (Aset Baru) | CRUD |
| 26 | User Management – User External | Helpdesk (Aset Llelang) | - |
| 26 | User Management – User External | Helpdesk (Aset Baru) | - |
| 26 | User Management – User External | FSO (Aset Baru) | - |
| 26 | User Management – User External | CWO (Aset Lelang) | - |
| 26 | User Management – User External | DBM Supporting (Aset Lelang) | - |
| 26 | User Management – User External | Nasabah | - |
| 26 | User Management – User External | Developer | - |
| 27 | User Management – User Block | Admin Pusat (Aset Lelang) | CRUD |
| 27 | User Management – User Block | Admin Pusat (Aset Baru) | CRUD |
| 27 | User Management – User Block | Helpdesk (Aset Llelang) | - |
| 27 | User Management – User Block | Helpdesk (Aset Baru) | - |
| 27 | User Management – User Block | FSO (Aset Baru) | - |
| 27 | User Management – User Block | CWO (Aset Lelang) | - |
| 27 | User Management – User Block | DBM Supporting (Aset Lelang) | - |
| 27 | User Management – User Block | Nasabah | - |
| 27 | User Management – User Block | Developer | - |
| 28 | Office Manegement – Tipe Kantor / Cabang | Admin Pusat (Aset Lelang) | CRUD |
| 28 | Office Manegement – Tipe Kantor / Cabang | Admin Pusat (Aset Baru) | CRUD |
| 28 | Office Manegement – Tipe Kantor / Cabang | Helpdesk (Aset Llelang) | - |
| 28 | Office Manegement – Tipe Kantor / Cabang | Helpdesk (Aset Baru) | - |
| 28 | Office Manegement – Tipe Kantor / Cabang | FSO (Aset Baru) | - |
| 28 | Office Manegement – Tipe Kantor / Cabang | CWO (Aset Lelang) | - |
| 28 | Office Manegement – Tipe Kantor / Cabang | DBM Supporting (Aset Lelang) | - |
| 28 | Office Manegement – Tipe Kantor / Cabang | Nasabah | - |
| 28 | Office Manegement – Tipe Kantor / Cabang | Developer | - |
| 29 | Office Management – Data Kantor / Cabang | Admin Pusat (Aset Lelang) | CRUD |
| 29 | Office Management – Data Kantor / Cabang | Admin Pusat (Aset Baru) | CRUD |
| 29 | Office Management – Data Kantor / Cabang | Helpdesk (Aset Llelang) | - |
| 29 | Office Management – Data Kantor / Cabang | Helpdesk (Aset Baru) | - |
| 29 | Office Management – Data Kantor / Cabang | FSO (Aset Baru) | - |
| 29 | Office Management – Data Kantor / Cabang | CWO (Aset Lelang) | - |
| 29 | Office Management – Data Kantor / Cabang | DBM Supporting (Aset Lelang) | - |
| 29 | Office Management – Data Kantor / Cabang | Nasabah | - |
| 29 | Office Management – Data Kantor / Cabang | Developer | - |
| 30 | Office Management – KPKNL | Admin Pusat (Aset Lelang) | CRUD |
| 30 | Office Management – KPKNL | Admin Pusat (Aset Baru) | - |
| 30 | Office Management – KPKNL | Helpdesk (Aset Llelang) | - |
| 30 | Office Management – KPKNL | Helpdesk (Aset Baru) | - |
| 30 | Office Management – KPKNL | FSO (Aset Baru) | CRUD |
| 30 | Office Management – KPKNL | CWO (Aset Lelang) | - |
| 30 | Office Management – KPKNL | DBM Supporting (Aset Lelang) | - |
| 30 | Office Management – KPKNL | Nasabah | - |
| 30 | Office Management – KPKNL | Developer | - |
| 31 | Audit Trail | Admin Pusat (Aset Lelang) | R |
| 31 | Audit Trail | Admin Pusat (Aset Baru) | R |
| 31 | Audit Trail | Helpdesk (Aset Llelang) | - |
| 31 | Audit Trail | Helpdesk (Aset Baru) | - |
| 31 | Audit Trail | FSO (Aset Baru) | - |
| 31 | Audit Trail | CWO (Aset Lelang) | - |
| 31 | Audit Trail | DBM Supporting (Aset Lelang) | - |
| 31 | Audit Trail | Nasabah | - |
| 31 | Audit Trail | Developer | - |
| 32 | Audit Log | Admin Pusat (Aset Lelang) | R |
| 32 | Audit Log | Admin Pusat (Aset Baru) | R |
| 32 | Audit Log | Helpdesk (Aset Llelang) | - |
| 32 | Audit Log | Helpdesk (Aset Baru) | - |
| 32 | Audit Log | FSO (Aset Baru) | - |
| 32 | Audit Log | CWO (Aset Lelang) | - |
| 32 | Audit Log | DBM Supporting (Aset Lelang) | - |
| 32 | Audit Log | Nasabah | - |
| 32 | Audit Log | Developer | - |
| 33 | Report – Aset Lelang | Admin Pusat (Aset Lelang) | CR |
| 33 | Report – Aset Lelang | Admin Pusat (Aset Baru) | - |
| 33 | Report – Aset Lelang | Helpdesk (Aset Llelang) | - |
| 33 | Report – Aset Lelang | Helpdesk (Aset Baru) | - |
| 33 | Report – Aset Lelang | FSO (Aset Baru) | - |
| 33 | Report – Aset Lelang | CWO (Aset Lelang) | R |
| 33 | Report – Aset Lelang | DBM Supporting (Aset Lelang) | - |
| 33 | Report – Aset Lelang | Nasabah | - |
| 33 | Report – Aset Lelang | Developer | - |
| 34 | Report – Aset Baru | Admin Pusat (Aset Lelang) | - |
| 34 | Report – Aset Baru | Admin Pusat (Aset Baru) | CR |
| 34 | Report – Aset Baru | Helpdesk (Aset Llelang) | - |
| 34 | Report – Aset Baru | Helpdesk (Aset Baru) | - |
| 34 | Report – Aset Baru | FSO (Aset Baru) | R |
| 34 | Report – Aset Baru | CWO (Aset Lelang) | - |
| 34 | Report – Aset Baru | DBM Supporting (Aset Lelang) | - |
| 34 | Report – Aset Baru | Nasabah | - |
| 34 | Report – Aset Baru | Developer | - |
| 35 | Notifikasi | Admin Pusat (Aset Lelang) | R |
| 35 | Notifikasi | Admin Pusat (Aset Baru) | R |
| 35 | Notifikasi | Helpdesk (Aset Llelang) | R |
| 35 | Notifikasi | Helpdesk (Aset Baru) | R |
| 35 | Notifikasi | FSO (Aset Baru) | R |
| 35 | Notifikasi | CWO (Aset Lelang) | R |
| 35 | Notifikasi | DBM Supporting (Aset Lelang) | R |
| 35 | Notifikasi | Nasabah | - |
| 35 | Notifikasi | Developer | - |
| 36 | Beranda (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 36 | Beranda (Eksternal) | Admin Pusat (Aset Baru) | - |
| 36 | Beranda (Eksternal) | Helpdesk (Aset Llelang) | - |
| 36 | Beranda (Eksternal) | Helpdesk (Aset Baru) | - |
| 36 | Beranda (Eksternal) | FSO (Aset Baru) | - |
| 36 | Beranda (Eksternal) | CWO (Aset Lelang) | - |
| 36 | Beranda (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 36 | Beranda (Eksternal) | Nasabah | R |
| 36 | Beranda (Eksternal) | Developer | - |
| 37 | Asel Lelang (Ekxternal) | Admin Pusat (Aset Lelang) | CUD |
| 37 | Asel Lelang (Ekxternal) | Admin Pusat (Aset Baru) | - |
| 37 | Asel Lelang (Ekxternal) | Helpdesk (Aset Llelang) | - |
| 37 | Asel Lelang (Ekxternal) | Helpdesk (Aset Baru) | - |
| 37 | Asel Lelang (Ekxternal) | FSO (Aset Baru) | - |
| 37 | Asel Lelang (Ekxternal) | CWO (Aset Lelang) | - |
| 37 | Asel Lelang (Ekxternal) | DBM Supporting (Aset Lelang) | - |
| 37 | Asel Lelang (Ekxternal) | Nasabah | CR |
| 37 | Asel Lelang (Ekxternal) | Developer | - |
| 38 | Aset Baru (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 38 | Aset Baru (Eksternal) | Admin Pusat (Aset Baru) | CUD |
| 38 | Aset Baru (Eksternal) | Helpdesk (Aset Llelang) | - |
| 38 | Aset Baru (Eksternal) | Helpdesk (Aset Baru) | - |
| 38 | Aset Baru (Eksternal) | FSO (Aset Baru) | - |
| 38 | Aset Baru (Eksternal) | CWO (Aset Lelang) | - |
| 38 | Aset Baru (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 38 | Aset Baru (Eksternal) | Nasabah | CR |
| 38 | Aset Baru (Eksternal) | Developer | CU |
| 39 | Jadwal Lelang (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 39 | Jadwal Lelang (Eksternal) | Admin Pusat (Aset Baru) | - |
| 39 | Jadwal Lelang (Eksternal) | Helpdesk (Aset Llelang) | - |
| 39 | Jadwal Lelang (Eksternal) | Helpdesk (Aset Baru) | - |
| 39 | Jadwal Lelang (Eksternal) | FSO (Aset Baru) | - |
| 39 | Jadwal Lelang (Eksternal) | CWO (Aset Lelang) | - |
| 39 | Jadwal Lelang (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 39 | Jadwal Lelang (Eksternal) | Nasabah | R |
| 39 | Jadwal Lelang (Eksternal) | Developer | - |
| 40 | Simulasi Pembiayaan (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 40 | Simulasi Pembiayaan (Eksternal) | Admin Pusat (Aset Baru) | - |
| 40 | Simulasi Pembiayaan (Eksternal) | Helpdesk (Aset Llelang) | - |
| 40 | Simulasi Pembiayaan (Eksternal) | Helpdesk (Aset Baru) | - |
| 40 | Simulasi Pembiayaan (Eksternal) | FSO (Aset Baru) | - |
| 40 | Simulasi Pembiayaan (Eksternal) | CWO (Aset Lelang) | - |
| 40 | Simulasi Pembiayaan (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 40 | Simulasi Pembiayaan (Eksternal) | Nasabah | CRU |
| 40 | Simulasi Pembiayaan (Eksternal) | Developer | - |
| 41 | Bandingkan Aset (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 41 | Bandingkan Aset (Eksternal) | Admin Pusat (Aset Baru) | - |
| 41 | Bandingkan Aset (Eksternal) | Helpdesk (Aset Llelang) | - |
| 41 | Bandingkan Aset (Eksternal) | Helpdesk (Aset Baru) | - |
| 41 | Bandingkan Aset (Eksternal) | FSO (Aset Baru) | - |
| 41 | Bandingkan Aset (Eksternal) | CWO (Aset Lelang) | - |
| 41 | Bandingkan Aset (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 41 | Bandingkan Aset (Eksternal) | Nasabah | CRU |
| 41 | Bandingkan Aset (Eksternal) | Developer | - |
| 42 | Panduan (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 42 | Panduan (Eksternal) | Admin Pusat (Aset Baru) | - |
| 42 | Panduan (Eksternal) | Helpdesk (Aset Llelang) | - |
| 42 | Panduan (Eksternal) | Helpdesk (Aset Baru) | - |
| 42 | Panduan (Eksternal) | FSO (Aset Baru) | - |
| 42 | Panduan (Eksternal) | CWO (Aset Lelang) | - |
| 42 | Panduan (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 42 | Panduan (Eksternal) | Nasabah | R |
| 42 | Panduan (Eksternal) | Developer | - |
| 43 | Tentang Kami (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 43 | Tentang Kami (Eksternal) | Admin Pusat (Aset Baru) | - |
| 43 | Tentang Kami (Eksternal) | Helpdesk (Aset Llelang) | - |
| 43 | Tentang Kami (Eksternal) | Helpdesk (Aset Baru) | - |
| 43 | Tentang Kami (Eksternal) | FSO (Aset Baru) | - |
| 43 | Tentang Kami (Eksternal) | CWO (Aset Lelang) | - |
| 43 | Tentang Kami (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 43 | Tentang Kami (Eksternal) | Nasabah | R |
| 43 | Tentang Kami (Eksternal) | Developer | - |
| 44 | FAQ | Admin Pusat (Aset Lelang) | - |
| 44 | FAQ | Admin Pusat (Aset Baru) | - |
| 44 | FAQ | Helpdesk (Aset Llelang) | - |
| 44 | FAQ | Helpdesk (Aset Baru) | - |
| 44 | FAQ | FSO (Aset Baru) | - |
| 44 | FAQ | CWO (Aset Lelang) | - |
| 44 | FAQ | DBM Supporting (Aset Lelang) | - |
| 44 | FAQ | Nasabah | R |
| 44 | FAQ | Developer | - |
| 45 | Artikel (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 45 | Artikel (Eksternal) | Admin Pusat (Aset Baru) | - |
| 45 | Artikel (Eksternal) | Helpdesk (Aset Llelang) | - |
| 45 | Artikel (Eksternal) | Helpdesk (Aset Baru) | - |
| 45 | Artikel (Eksternal) | FSO (Aset Baru) | - |
| 45 | Artikel (Eksternal) | CWO (Aset Lelang) | - |
| 45 | Artikel (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 45 | Artikel (Eksternal) | Nasabah | R |
| 45 | Artikel (Eksternal) | Developer | - |
| 46 | Favorit (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 46 | Favorit (Eksternal) | Admin Pusat (Aset Baru) | - |
| 46 | Favorit (Eksternal) | Helpdesk (Aset Llelang) | - |
| 46 | Favorit (Eksternal) | Helpdesk (Aset Baru) | - |
| 46 | Favorit (Eksternal) | FSO (Aset Baru) | - |
| 46 | Favorit (Eksternal) | CWO (Aset Lelang) | - |
| 46 | Favorit (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 46 | Favorit (Eksternal) | Nasabah | CRU |
| 46 | Favorit (Eksternal) | Developer | - |
| 47 | Notifikasi (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 47 | Notifikasi (Eksternal) | Admin Pusat (Aset Baru) | - |
| 47 | Notifikasi (Eksternal) | Helpdesk (Aset Llelang) | - |
| 47 | Notifikasi (Eksternal) | Helpdesk (Aset Baru) | - |
| 47 | Notifikasi (Eksternal) | FSO (Aset Baru) | - |
| 47 | Notifikasi (Eksternal) | CWO (Aset Lelang) | - |
| 47 | Notifikasi (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 47 | Notifikasi (Eksternal) | Nasabah | R |
| 47 | Notifikasi (Eksternal) | Developer | - |
| 48 | Daftar Pesanan (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 48 | Daftar Pesanan (Eksternal) | Admin Pusat (Aset Baru) | - |
| 48 | Daftar Pesanan (Eksternal) | Helpdesk (Aset Llelang) | - |
| 48 | Daftar Pesanan (Eksternal) | Helpdesk (Aset Baru) | - |
| 48 | Daftar Pesanan (Eksternal) | FSO (Aset Baru) | - |
| 48 | Daftar Pesanan (Eksternal) | CWO (Aset Lelang) | - |
| 48 | Daftar Pesanan (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 48 | Daftar Pesanan (Eksternal) | Nasabah | R |
| 48 | Daftar Pesanan (Eksternal) | Developer | - |
| 49 | Profile User (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 49 | Profile User (Eksternal) | Admin Pusat (Aset Baru) | - |
| 49 | Profile User (Eksternal) | Helpdesk (Aset Llelang) | - |
| 49 | Profile User (Eksternal) | Helpdesk (Aset Baru) | - |
| 49 | Profile User (Eksternal) | FSO (Aset Baru) | - |
| 49 | Profile User (Eksternal) | CWO (Aset Lelang) | - |
| 49 | Profile User (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 49 | Profile User (Eksternal) | Nasabah | CRU |
| 49 | Profile User (Eksternal) | Developer | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | Admin Pusat (Aset Baru) | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | Helpdesk (Aset Llelang) | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | Helpdesk (Aset Baru) | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | FSO (Aset Baru) | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | CWO (Aset Lelang) | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | Nasabah | - |
| 50 | Portal Developer – Aset Kelolaan (Eksternal) | Developer | CRUD |
| 51 | Portal Developer – Form Input Aset (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | Admin Pusat (Aset Baru) | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | Helpdesk (Aset Llelang) | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | Helpdesk (Aset Baru) | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | FSO (Aset Baru) | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | CWO (Aset Lelang) | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | Nasabah | - |
| 51 | Portal Developer – Form Input Aset (Eksternal) | Developer | CRUD |
| 52 | Portal Developer – List Aset (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 52 | Portal Developer – List Aset (Eksternal) | Admin Pusat (Aset Baru) | - |
| 52 | Portal Developer – List Aset (Eksternal) | Helpdesk (Aset Llelang) | - |
| 52 | Portal Developer – List Aset (Eksternal) | Helpdesk (Aset Baru) | - |
| 52 | Portal Developer – List Aset (Eksternal) | FSO (Aset Baru) | - |
| 52 | Portal Developer – List Aset (Eksternal) | CWO (Aset Lelang) | - |
| 52 | Portal Developer – List Aset (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 52 | Portal Developer – List Aset (Eksternal) | Nasabah | - |
| 52 | Portal Developer – List Aset (Eksternal) | Developer | R |
| 53 | Portal Developer – Form Input Aset (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | Admin Pusat (Aset Baru) | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | Helpdesk (Aset Llelang) | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | Helpdesk (Aset Baru) | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | FSO (Aset Baru) | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | CWO (Aset Lelang) | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | Nasabah | - |
| 53 | Portal Developer – Form Input Aset (Eksternal) | Developer | CRUD |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | Admin Pusat (Aset Baru) | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | Helpdesk (Aset Llelang) | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | Helpdesk (Aset Baru) | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | FSO (Aset Baru) | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | CWO (Aset Lelang) | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | Nasabah | - |
| 54 | Portal Developer – Dashboard Developer (Eksternal) | Developer | CRUD |
| 55 | Portal Developer – Akun (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 55 | Portal Developer – Akun (Eksternal) | Admin Pusat (Aset Baru) | - |
| 55 | Portal Developer – Akun (Eksternal) | Helpdesk (Aset Llelang) | - |
| 55 | Portal Developer – Akun (Eksternal) | Helpdesk (Aset Baru) | - |
| 55 | Portal Developer – Akun (Eksternal) | FSO (Aset Baru) | - |
| 55 | Portal Developer – Akun (Eksternal) | CWO (Aset Lelang) | - |
| 55 | Portal Developer – Akun (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 55 | Portal Developer – Akun (Eksternal) | Nasabah | - |
| 55 | Portal Developer – Akun (Eksternal) | Developer | CRU |
| 56 | Portal Developer – Keamanan (Eksternal) | Admin Pusat (Aset Lelang) | - |
| 56 | Portal Developer – Keamanan (Eksternal) | Admin Pusat (Aset Baru) | - |
| 56 | Portal Developer – Keamanan (Eksternal) | Helpdesk (Aset Llelang) | - |
| 56 | Portal Developer – Keamanan (Eksternal) | Helpdesk (Aset Baru) | - |
| 56 | Portal Developer – Keamanan (Eksternal) | FSO (Aset Baru) | - |
| 56 | Portal Developer – Keamanan (Eksternal) | CWO (Aset Lelang) | - |
| 56 | Portal Developer – Keamanan (Eksternal) | DBM Supporting (Aset Lelang) | - |
| 56 | Portal Developer – Keamanan (Eksternal) | Nasabah | - |
| 56 | Portal Developer – Keamanan (Eksternal) | Developer | RU |

