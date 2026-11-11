# LAPORAN TUGAS MANDIRI 2
## Dokumentasi dan Pengujian Web Service Katalog Buku

### 1. Tujuan
Tugas ini bertujuan untuk melengkapi dokumentasi Web Service Katalog Buku menggunakan OpenAPI dan Swagger UI. Dokumentasi diperjelas dengan menambahkan deskripsi endpoint serta contoh respons kesalahan agar pengguna API lebih mudah memahami cara penggunaan layanan.

### 2. Rancangan Endpoint

| Metode | Endpoint | Fungsi | Respons Berhasil |
|---|---|---|---|
| GET | `/api/buku` | Menampilkan seluruh buku | 200 OK |
| GET | `/api/buku/{id}` | Menampilkan buku berdasarkan ID | 200 OK |
| POST | `/api/buku` | Menambahkan buku baru | 201 Created |
| PUT | `/api/buku/{id}` | Mengubah data buku | 200 OK |
| DELETE | `/api/buku/{id}` | Menghapus buku | 204 No Content |

Data buku terdiri dari:
- `id`: ID buku yang dibuat otomatis oleh server.
- `judul`: Judul buku berupa teks dengan panjang 1–120 karakter setelah trim.
- `tersedia`: Status ketersediaan buku berupa Boolean (`true` atau `false`).

### 3. Pembagian Tanggung Jawab File

| File | Tanggung Jawab |
|---|---|
| `app.cjs` | Mengatur aplikasi Express dan middleware. |
| `server.cjs` | Menjalankan server. |
| `buku.routes.cjs` | Mengatur rute API. |
| `buku.controller.cjs` | Menangani request dan response. |
| `buku.service.cjs` | Menjalankan logika layanan buku. |
| `buku.repository.cjs` | Mengelola penyimpanan data buku. |
| `errors.cjs` | Mengelola kesalahan aplikasi. |
| `client.cjs` | Membantu menguji endpoint API. |
| `generate-openapi.cjs` | Menghasilkan dokumentasi OpenAPI. |
| `openapi.json` | Menyimpan spesifikasi dokumentasi API. |

### 4. Penyempurnaan Dokumentasi
Penyempurnaan dilakukan pada generator OpenAPI dengan menambahkan deskripsi yang lebih jelas pada setiap endpoint dan contoh respons kesalahan, seperti:
- 400 Bad Request: data atau parameter tidak valid.
- 404 Not Found: data buku atau rute tidak ditemukan.
- 413 Payload Too Large: ukuran data melebihi batas.
- 415 Unsupported Media Type: format konten tidak sesuai.
- 500 Internal Server Error: terjadi kesalahan pada server.

Penambahan deskripsi dan contoh respons hanya memperjelas dokumentasi. Kontrak API dan perilaku implementasi tetap dipertahankan.

### 5. Matriks Pengujian

| No. | Pengujian | Hasil yang Diharapkan | Hasil Aktual |
|---|---|---|---|
| 1 | GET daftar buku | 200 OK | Isi setelah pengujian |
| 2 | GET detail buku | 200 OK | Isi setelah pengujian |
| 3 | POST tambah buku | 201 Created | Isi setelah pengujian |
| 4 | PUT ubah buku | 200 OK | Isi setelah pengujian |
| 5 | DELETE buku | 204 No Content | Isi setelah pengujian |
| 6 | ID tidak valid | 400 Bad Request | Isi setelah pengujian |
| 7 | Buku tidak ditemukan | 404 Not Found | Isi setelah pengujian |
| 8 | Format data salah | 400 Bad Request | Isi setelah pengujian |
| 9 | Content-Type salah | 415 Unsupported Media Type | Isi setelah pengujian |

### 6. Petunjuk Menjalankan Ulang
1. Buka folder proyek melalui VS Code.
2. Buka terminal pada folder proyek.
3. Jalankan perintah `npm ci` untuk memasang dependensi.
4. Jalankan `npm run docs` untuk menghasilkan dokumentasi OpenAPI.
5. Jalankan `npm start` untuk mengaktifkan server.
6. Buka `http://127.0.0.1:3200/api/buku` untuk melihat data buku.
7. Buka `http://127.0.0.1:3200/docs/` untuk melihat dokumentasi Swagger UI.

### 7. Kesimpulan
Berdasarkan pengerjaan Tugas Mandiri 2, dokumentasi Web Service Katalog Buku telah dilengkapi dengan deskripsi endpoint dan contoh respons kesalahan. Swagger UI digunakan untuk melihat dan mencoba endpoint API. Penyempurnaan dokumentasi dilakukan tanpa mengubah kontrak maupun fungsi utama layanan.