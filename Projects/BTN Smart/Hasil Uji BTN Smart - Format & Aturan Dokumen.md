---
tags:
  - SIT
  - UAT
  - BTN
  - QA
  - Format
  - Word
  - HasilUji
date: 2026-09-18
project: BTN Smart
type: standard
---

# 📄 Hasil Uji BTN Smart - Format & Aturan Dokumen Word

> Standar format dokumen Word Hasil Uji yang digunakan untuk **BTN SMART**.
> Di-generate secara otomatis menggunakan script Python berbasis struktur folder Google Drive.

---

## 📐 Layout Halaman

| Property | Value |
|---|---|
| **Orientasi** | Portrait |
| **Ukuran Kertas** | A4 (21.01 cm × 29.7 cm) |
| **Margin Atas** | 1.48 cm |
| **Margin Bawah** | 0.49 cm |
| **Margin Kiri** | 1.55 cm |
| **Margin Kanan** | 0.35 cm |

---

## 🗂️ Struktur Dokumen Keseluruhan

```
Cover Page
├── Table 0 - Informasi Dokumen (6 baris × 2 kolom)
├── Table 1 - Penandatangan Penyedia Jasa (5 baris × 4 kolom)
├── Table 2 - Diketahui Oleh BTN (4 baris × 1 kolom)
└── Table 3 - Histori Perbaikan (2 baris × 5 kolom)

Isi (per Modul)
├── Heading 1: "Modul [Nama Modul]"
├── Paragraf kosong
├── TC Table PERTAMA (4 baris: header + judul + ss + expected)
├── TC Table KEDUA (3 baris: tanpa header row)
└── ... dst
```

> **Pola kunci:** TC **pertama** per modul punya **header row biru**. TC berikutnya **tidak punya header row** (langsung data).

---

## 📌 Struktur Tiap TC Table

### TC Pertama Per Modul — 4 Rows

| Row | Isi | BG Color | Style |
|---|---|---|---|
| Row 0 (Header) | `No.` / `User Acceptance Testing (UAT)` | `2C5293` (biru tua) | Bold, White, Center |
| Row 1 (Judul TC) | `1.1` / `[Judul TC]` | `D0CECE` (abu-abu) | Normal, Hitam |
| Row 2 (Screenshot) | kosong / gambar | None (putih) | Center (gambar) |
| Row 3 (Expected) | kosong / teks expected | None (putih) | Lihat di bawah |

### TC Kedua dst — 3 Rows (tanpa header)

| Row | Isi |
|---|---|
| Row 0 (Judul TC) | `1.2` / `[Judul TC]` — bg abu D0CECE |
| Row 1 (Screenshot) | gambar — putih |
| Row 2 (Expected) | teks expected — putih |

---

## 🎨 Styling Detail

### Warna
| Elemen | HEX | Keterangan |
|---|---|---|
| Header row bg | `2C5293` | Biru tua |
| Judul TC row bg | `D0CECE` | Abu-abu muda |
| Teks header | `FFFFFF` | Putih |
| Teks No / Judul TC | `000000` | Hitam |
| `"Hasil yang diharapkan [STATUS]:"` | `000000` | Hitam Bold |
| Expected result content | `2C5293` | Biru |

### Font
- **Font family**: Arial (semua elemen)
- **Ukuran**: 10pt (127000 EMU)
- Header row: **Bold**
- Judul TC: Normal
- `"Hasil yang diharapkan [STATUS]:"`: **Bold**
- Expected result content: Normal, warna biru `2C5293`

### Spacing (space_before per paragraf)
- Header row & Judul TC: `5.8pt`
- Screenshot row: `5.8pt`
- `"Hasil yang diharapkan [STATUS]:"`: `5.8pt`
- Expected result content: `6.5pt`

---

## 🖼️ Gambar Screenshot

- **Tipe**: Inline image
- **Alignment**: CENTER dalam cell
- **Target lebar maks**: `15.0 cm` (5.400.000 EMU)
- **Tinggi**: Proporsional otomatis sesuai aspek rasio gambar asli

---

## 📊 Ukuran Kolom

| Kolom | Lebar (dxa) | ≈ cm |
|---|---|---|
| Col 0 (No.) | 709 dxa | ~1.25 cm |
| Col 1 (Content) | 9084 dxa | ~16.0 cm |
| **Total** | **9793 dxa** | **~17.25 cm** |

---

## 🔲 Border Tabel

- Style: `single`, sz: `4` (0.5pt), warna: `000000`
- Berlaku untuk semua sisi: top, left, bottom, right, insideH, insideV

---

## 🏷️ Heading 1

- Style name: `Heading 1`
- Format teks: `"Modul [Nama Modul]"`
- Space before: `1.8pt`

---

## 🔗 Referensi Terkait
- [[Hasil Uji BTN Smart - Panduan Generator & Siklus Uji]] — Panduan SOP perubahan TC, script sinkronisasi, dan troubleshooting teknis.
