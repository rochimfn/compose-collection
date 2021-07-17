# Koleksi `docker-compose`

## Tentang
Koleksi konfigurasi docker-compose untuk keperluan belajar dan pengembangan.

## Persiapan
Seluruh konfigurasi `docker-compose.yaml` menggunakan jaringan berbagi dengan nama `database`.

```bash
docker network create database
```

## Penggunaan
Masuk ke direktori compose yang ingin dijalankan lalu jalankan `docker-compose`.

```bash
# Contoh untuk menjalankan
cd postgres
docker-compose up -d

# Contoh untuk mematikan
cd postgres
docker-compose down
```