# 13 - Tips Lanjutan API Teardown & UI Desync

## 1. Logika "Tukang Sapu" (Kenapa Mengabaikan Error 404)

Dalam *teardown* (fase pembersihan) menggunakan API, kita sering menemui logika seperti ini:

```python
if delete_response.status != 404:
    assert delete_response.ok, f"Error: {delete_response.text()}"
```

**Analogi Tukang Sapu:**
- Tugas API Delete di fase *teardown* adalah memastikan "ruangan bersih" (user terhapus).
- Jika API mencoba menghapus user, tapi ternyata user itu **sudah dihapus** (misal oleh fungsi `test_delete_user` melalui UI), server akan membalas **404 Not Found**.
- Kita **MEMAAFKAN (mengabaikan) 404** karena tujuan kita (database bersih) sebenarnya **sudah tercapai**.
- Jika tidak diabaikan, test UI kita yang aslinya berhasil malah akan dianggap GAGAL (merah) oleh Pytest hanya karena si tukang sapu telat membersihkan.
- **Peringatan:** Kita HANYA memaafkan 404. Jika statusnya 500 (Server Error) atau 401 (Unauthorized), kode di atas akan tetap meneriakkan `assert` error (test gagal).

## 2. Frontend State Desync (Masalah Autocomplete Modern)

Di aplikasi berbasis React/Vue (seperti OrangeHRM), kolom *Autocomplete* punya dua lapis data:
1. **Teks yang tampil di layar** (contoh: "Budi Santoso")
2. **State rahasia di belakang layar** (contoh: `ID = 2`)

**Penyebab Error (Desync):**
Jika di layar sudah terpilih "Budi Santoso" (ID 2), lalu robot Playwright secara instan menghapus dan mengetik ulang kata "Budi" lalu mengeklik pilihan "Budi Santoso" lagi, sistem *frontend* bisa nge-bug.
- Sistem merasa: *"Lho, ID yang diklik masih ID 2, nggak ada perubahan. Aku abaikan saja kliknya."*
- Akibatnya, input box tertahan dengan tulisan `"Budi"` (tidak *auto-fill* menjadi nama lengkap).
- Saat di-Save, muncul pesan **Invalid**.

**Solusi:**
Pastikan skenario pengujian *Edit* benar-benar memicu "Perubahan State". Hindari mengetik ulang dan mengklik orang/entitas yang **sama persis** dengan *state* yang sedang terpilih saat itu. Ganti target edit ke orang lain (misal dari Budi ke Dani), agar sistem mendeteksi ada perubahan data.
