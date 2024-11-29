# docker-lamp

Docker LAMP stack by [ginginabdulgoni](https://github.com/ginginabdulgoni/docker-lamp).  
Stack ini mencakup:
- **Linux**
- **Apache** / **Nginx**
- **MySQL** / **MariaDB**
- **PHP 7.4**

## Struktur Folder
Proyek Anda harus disimpan dalam struktur folder berikut:

app/ └── yourproject/




Letakkan file proyek PHP Anda di folder `app/yourproject` agar dapat diakses melalui container.

## Fitur
- **PHP Versi**: 7.4
- **phpMyAdmin**: 
  - Akses melalui: [http://localhost:8080](http://localhost:8080)
  - Gunakan untuk mengelola database dengan antarmuka grafis.

---

## Cara Menggunakan

1. **Clone Repository**
   ```bash
   git clone https://github.com/ginginabdulgoni/docker-lamp.git
   cd docker-lamp
Simpan Proyek Anda

Pastikan file proyek Anda berada di folder app/yourproject.
Jalankan Docker Compose

bash

docker-compose up -d
Akses Proyek

Akses proyek Anda melalui browser di: http://localhost.
Jika proyek Anda disimpan di app/yourproject, maka URL-nya akan menjadi http://localhost/yourproject.
Akses phpMyAdmin

URL: http://localhost:8080
Masukkan username dan password MySQL/MariaDB sesuai konfigurasi di docker-compose.yml.
Catatan
Anda dapat memodifikasi versi PHP, MySQL/MariaDB, atau layanan lainnya dengan mengedit file docker-compose.yml.
Pastikan Docker dan Docker Compose sudah terinstal di sistem Anda sebelum menjalankan stack ini.



### Penyesuaian:
1. Nama repo dihubungkan ke akun **ginginabdulgoni**.
2. Keterangan URL `localhost:8080` untuk phpMyAdmin sudah dijelaskan.
3. Struktur folder `app/yourproject` ditekankan di bagian awal. 

