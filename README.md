# Aplikasi Buku

Aplikasi Buku adalah aplikasi berbasis mobile yang memungkinkan pengguna untuk mengelola data buku, anggota, dan peminjaman. Aplikasi ini dibuat menggunakan Flutter untuk frontend, Flask untuk backend, dan MySQL sebagai database.

## Fitur

- **Manajemen Buku**: Tambah, ubah, hapus, dan lihat daftar buku.
- **Manajemen Anggota**: Tambah, ubah, hapus, dan lihat daftar anggota.
- **Manajemen Peminjaman**: Tambah, ubah, hapus, dan lihat daftar peminjaman.

## Struktur Proyek

- **Frontend**: Flutter
  - `lib/`
    - `main.dart`
    - `screens/`
      - `books_screen.dart`
      - `members_screen.dart`
      - `loans_screen.dart`
    - `models/`
      - `book.dart`
      - `member.dart`
      - `loan.dart`
    - `services/`
      - `api_service.dart`
- **Backend**: Flask
  - `app.py`
  - `routes/`
    - `books.py`
    - `members.py`
    - `loans.py`
  - `models/`
    - `book.py`
    - `member.py`
    - `loan.py`
  - `config.py`
- **Database**: MySQL
  - Struktur tabel: `books`, `members`, `loans`

## Instalasi

### Backend

1. Clone repositori
   ```bash
   git clone <url-repo>
   cd <nama-repo>
   ```

2. Buat virtual environment dan install dependencies
   ```bash
   python -m venv venv
   source venv/bin/activate  # Untuk macOS/Linux
   venv\Scripts\activate  # Untuk Windows
   pip install -r requirements.txt
   ```

3. Konfigurasi database MySQL di `config.py`

4. Jalankan aplikasi Flask
   ```bash
   flask run
   ```

### Frontend

1. Install Flutter dan setup environment
   - Ikuti panduan [Flutter installation](https://flutter.dev/docs/get-started/install)

2. Clone repositori
   ```bash
   git clone <url-repo>
   cd <nama-repo>
   ```

3. Jalankan aplikasi Flutter
   ```bash
   flutter pub get
   flutter run
   ```

## Struktur Database

### Tabel Buku (`books`)
| Kolom        | Tipe Data    | Deskripsi                   |
|--------------|--------------|-----------------------------|
| `id`         | INT          | Primary key, auto increment |
| `title`      | VARCHAR(255) | Judul buku                  |
| `author`     | VARCHAR(255) | Penulis buku                |
| `published`  | DATE         | Tanggal terbit              |
| `cover_url`  | VARCHAR(255) | URL cover buku              |

### Tabel Anggota (`members`)
| Kolom        | Tipe Data    | Deskripsi                   |
|--------------|--------------|-----------------------------|
| `id`         | INT          | Primary key, auto increment |
| `name`       | VARCHAR(255) | Nama anggota                |
| `email`      | VARCHAR(255) | Email anggota               |
| `phone`      | VARCHAR(15)  | Nomor telepon anggota       |

### Tabel Peminjaman (`loans`)
| Kolom        | Tipe Data    | Deskripsi                   |
|--------------|--------------|-----------------------------|
| `id`         | INT          | Primary key, auto increment |
| `book_id`    | INT          | Foreign key ke tabel `books`|
| `member_id`  | INT          | Foreign key ke tabel `members`|
| `loan_date`  | DATE         | Tanggal peminjaman          |
| `return_date`| DATE         | Tanggal pengembalian        |

## API Endpoints

### Buku
- **GET /books**: Mendapatkan daftar semua buku
- **POST /books**: Menambahkan buku baru
- **PUT /books/{id}**: Mengubah data buku
- **DELETE /books/{id}**: Menghapus buku

### Anggota
- **GET /members**: Mendapatkan daftar semua anggota
- **POST /members**: Menambahkan anggota baru
- **PUT /members/{id}**: Mengubah data anggota
- **DELETE /members/{id}**: Menghapus anggota

### Peminjaman
- **GET /loans**: Mendapatkan daftar semua peminjaman
- **POST /loans**: Menambahkan peminjaman baru
- **PUT /loans/{id}**: Mengubah data peminjaman
- **DELETE /loans/{id}**: Menghapus peminjaman


## Screenshot

### Halaman Buku iOS
<img src="screenshots/1.png" alt="drawing" width="200"/>

### Halaman Tambah Buku iOS
<img src="screenshots/2.png" alt="drawing" width="200"/>

### Halaman Edit Buku iOS
<img src="screenshots/3.png" alt="drawing" width="200"/>

### Halaman Buku Android
<img src="screenshots/4.png" alt="drawing" width="200"/>

### Halaman Tambah Buku Android
<img src="screenshots/5.png" alt="drawing" width="200"/>

## Penutup

Aplikasi Buku ini adalah contoh aplikasi sederhana untuk mengelola data buku, anggota, dan peminjaman. Penggunaan Flutter untuk frontend, Flask untuk backend, dan MySQL sebagai database memberikan fleksibilitas dan kemudahan dalam pengembangan aplikasi. Silakan kembangkan dan modifikasi sesuai kebutuhan Anda
