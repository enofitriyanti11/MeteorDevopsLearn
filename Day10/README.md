# DOCKER COMPOSE

Docker compose adalah sebuah alat untuk mendefenisikan dan menjalankan beberapa docker container yang saling terkait dengan sebuah command.
Docker compose dibuat dengan file berekstensikan .yml 

Proses dasar Docker Compose:
1. mendefenisikan environment aplikasi dengan membuat Dockerfile sehingga bisa digunakan kembali dimana saja.
2. mendefenisikan service lainnya (termasuk aplikasi yang ada di lokal) di dalam docker-compose.yml sehingga semua bisa berjalan bersamaan dalan environment yang terisolasi.
3. jalankan ```docker-compose build``` dan ```docker-compose up``` di terminal dan pastikan running di path yang sama dengan ```docker-compose.yml```




Berikut contoh membuat docker compose dengan pull image dari docker registry:

1. Buat docker-compose.yml

```docker-compose.yml
version: '3.8'
services:
  webapp:
    image: nginx
    ports:
      - "8080:80"
  db:
    image: postgres:12.6
    ports:
      - "5432:5432"
    environment:
      - POSTGRES_PASSWORD=password
```
```version``` digunakan untuk menentukan versi docker-compose dan menentukan format pembuatan services seperti apa
```services``` digunakan untuk  menentukan layanan apa saja yang akan didefenisikan.
```webapp``` services webapp menggunakan docker image nginx yang dijalankan di port 80 dan diarahkan ke port 8080
```db``` services db yang menjalankan docker image postgres dengan port yang diarahkan ke 5432 dan environment yang ditentukan adalah POSTGRES_PASSWORD=password

2. run ```docker-compose pull```



