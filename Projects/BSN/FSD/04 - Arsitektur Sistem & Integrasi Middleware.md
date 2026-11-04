---
title: FSD BSN Lelang - 04 Arsitektur Sistem & Integrasi Middleware
project: BSN Lelang
tags:
  - fsd
  - bsn
  - architecture
  - middleware
  - integration
  - api
---

# 🏗️ 04 - Arsitektur Sistem & Integrasi Middleware

> [!NOTE] Arsitektur & Antarmuka Sistem
> Modul ini menjelaskan arsitektur teknologi, lapisan middleware, dan mekanisme pertukaran data antar sistem pada platform BSN Lelang.

---

## 🏛️ 1. Diagram Arsitektur Aplikasi

Platform BSN Lelang dibangun dengan arsitektur modular yang terpisah antara Frontend (Web Nasabah & Web Backoffice), API Gateway, Service Layer, dan Integrasi Host Bank Syariah Nasional.

![Arsitektur Aplikasi BSN Lelang](file:///D:/Project/BSN/Fase%201/FSD/assets/05_architecture/architecture_01_arsitektur_aplikasi.png)

---

## 🔌 2. Integrasi Data & Middleware

Berikut adalah diagram alur data dan integrasi antar aplikasi via middleware:

![Integrasi Data dan Middleware](file:///D:/Project/BSN/Fase%201/FSD/assets/05_architecture/architecture_02_integrasi_middleware_data.png)

### 2.1 Matriks Integrasi Aplikasi & Service Interface
| No | Nama Menu atau Fitur | Nama Aplikasi A (Aplikasi yang Akan Dibangun) | Nama Aplikasi B (Aplikasi Lain yang Terintegrasi) | Nama Middleware / Interface /Messaging A (Nama Middleware dari Aplikasi yang Akan Dibangun) | Nama Middleware / Interface /Messaging B (Nama Middleware dari Aplikasi Lain) | Nama Service A (Nama Service Milik Aplikasi A) | Nama Service B (Nama Service yang digunakan Aplikasi B) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Login | BSN Properti | LDAP | direct | direct | Autentikasi SSO LDAP | Login Auth |
| 2 | Inquiry | BSN Properti | API Core | - | - | Inquiry data nasabah | … |
| 3 | Simulasi KPR | BSN Properti | API Simulasi KPR | - | - | Simulasi KPR web BSN Properti | … |
| 4 | - | BSN Properti | EDW | - | - | belum diketahui | … |
| 5 | Email OTP | BSN Properti | SMTP | - | - | Email OTP | … |
| dst |  | … | … | … | … | … | … |


---

### 2.2 Pemetaan Data Aplikasi A dan B
| Nama Aplikasi A (Nama aplikasi yang dibangun sebagai sudut pandang utama) | Nama Aplikasi B (Nama aplikasi tujuan) | Data Aplikasi A (Data dari Aplikasi A ke aplikasi B) | Data Aplikasi B (Data dari Aplikasi B ke aplikasi A) |
| --- | --- | --- | --- |
| BSN Lelang | Core Banking Syariah | Referensi, No. Rekening Pembiayaan | No. Rekening, Nama Debitur, DPD, Kolektibilitas, Outstanding, Jenis Pembiayaan, Kantor Cabang, Status Rekening, Tunggakan Margin, Tunggakan Denda, Total Kewajiban |
| BSN Lelang | LDAP | Username, Password, Apps | Status, Data, Nama, Divisi, Kantor, NIP, Email, userAD |


---

### 2.3 Standar Teknologi Pengembangan (Technology Stack)
| Technology Development | Value Properties Technology Development |
| --- | --- |
| Platform Technology | Echo v4 (Backend) & Next JS v14 + Node JS v20 (Frontend) |
| Bahasa Pemrograman | Golang v1.27 + JavaScript ES6 |
| Web Service | Nginx v1.27 |

