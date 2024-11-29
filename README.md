# docker-lamp

Docker LAMP stack by [ginginabdulgoni](https://github.com/ginginabdulgoni/docker-lamp).\
Stack ini mencakup:

* **Linux**
* **Apache** / **Nginx**
* **MySQL** / **MariaDB**
* **PHP 7.4** (default, dapat diubah ke versi lain)

## Struktur Folder

Proyek Anda harus disimpan dalam struktur folder berikut:

app/ └── yourproject/

Letakkan file proyek PHP Anda di folder `app/yourproject` agar dapat diakses melalui container.

## Fitur

* **PHP Versi**: 7.4 (default, dapat disesuaikan dengan versi lain seperti 7.4, 8.0, 8.1, 8.2)
* **phpMyAdmin**:
  * Akses melalui: [http://localhost:8080](http://localhost:8080)
  * Gunakan untuk mengelola database dengan antarmuka grafis.

## Menggunakan Multi-PHP

Jika Anda perlu menggunakan lebih dari satu versi PHP, Anda bisa menambahkan versi PHP baru dalam file `docker-compose.yml` dan mengubah konfigurasi PHP di file `nginx/default.conf`.

**Langkah-langkah untuk mengubah versi PHP:**

1. **Tambahkan Versi PHP Baru di`docker-compose.yml`**\
   Di dalam file `docker-compose.yml`, Anda dapat menambahkan versi PHP yang diinginkan dengan menambahkan service baru, misalnya:

   ```yaml
   php-fpm-8.0:
     image: php:8.0-fpm
     volumes:
       - ./app:/var/www/html
     expose:
       - "9000"
   ```

2. **Ubah Konfigurasi PHP di Nginx (`nginx/default.conf`)**\
   Setelah menambahkan versi PHP di `docker-compose.yml`, Anda perlu mengubah pengaturan Nginx di file `nginx/default.conf`. Misalnya, Anda bisa mengubah konfigurasi PHP-FPM seperti ini:

   ```nginx
   fastcgi_pass php-fpm-8.1:9000; # Specify PHP version (e.g., 7.7, 8.0, 8.1, 8.2)
   ```

3. **Restart Container Nginx**\
   Setelah Anda mengubah versi PHP di `nginx/default.conf`, Anda wajib me-restart container Nginx agar perubahan tersebut berlaku.

   Jalankan perintah berikut untuk restart Nginx:

   ```bash
   docker-compose restart nginx
   ```

## Cara Menggunakan

1. **Clone Repository**

   git clone [https://github.com/ginginabdulgoni/docker-lamp.git](https://github.com/ginginabdulgoni/docker-lamp.git)\
   cd docker-lamp
2. Simpan Proyek Anda\
   Pastikan file proyek Anda berada di folder app/yourproject.
3. Jalankan Docker Compose

docker-compose up -d

Akses proyek Anda melalui browser di: [http://localhost](http://localhost).\
Jika proyek Anda disimpan di app/yourproject, maka URL-nya akan menjadi [http://localhost/yourproject](http://localhost/yourproject).
Akses phpMyAdmin

URL: [http://localhost:8080](http://localhost:8080)\
Masukkan username dan password MySQL/MariaDB sesuai konfigurasi di docker-compose.yml. example root:root



Anda dapat memodifikasi versi PHP, MySQL/MariaDB, atau layanan lainnya dengan mengedit file docker-compose.yml.

Pastikan Docker dan Docker Compose sudah terinstal di sistem Anda sebelum menjalankan stack ini.

### Penyesuaian:

1. Nama repo dihubungkan ke akun **ginginabdulgoni**.
2. Keterangan URL `localhost:8080` untuk phpMyAdmin sudah dijelaskan.
3. Struktur folder `app/yourproject` ditekankan di bagian awal.

## Dukungan

Jika Anda merasa proyek ini bermanfaat dan ingin mendukung saya, traktir kopi saya melalui:

* [Saweria](https://saweria.co/ginginabdulgoni)
* [Trakteer](https://trakteer.id/ginginabdulgoni)
* [Trakteer Tips](https://trakteer.id/ginginabdulgoni/tip)
* [Paypal](https://paypal.me/ginginabdulgoni)