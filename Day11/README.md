# Docker Network

Beberapa driver tersedia secara default, dan menyediakan fungsionalitas jaringan inti:

* bridge: Driver jaringan default. Jika tidak menentukan driver, ini adalah jenis jaringan yang dibuat. Jaringan jembatan biasanya digunakan saat aplikasi berjalan dalam wadah mandiri yang perlu berkomunikasi.

* host: Untuk kontainer mandiri, hapus isolasi jaringan antara kontainer dan host Docker, dan gunakan jaringan host secara langsung.

* overlay: Jaringan overlay menghubungkan beberapa daemon Docker secara bersamaan dan memungkinkan layanan swarm berkomunikasi satu sama lain. Kita juga dapat menggunakan jaringan overlay untuk memfasilitasi komunikasi antara layanan swarm dan kontainer mandiri, atau antara dua kontainer mandiri pada daemon Docker yang berbeda. Strategi ini menghilangkan kebutuhan untuk melakukan perutean tingkat OS di antara kontainer-kontainer ini.

* macvlan: Jaringan macvlan memungkinkan untuk menetapkan alamat MAC ke suatu kontainer, membuatnya tampak sebagai perangkat fisik di jaringan. Daemon Docker merutekan lalu lintas ke kontainer berdasarkan alamat MAC-nya. Menggunakan driver macvlan terkadang merupakan pilihan terbaik saat menangani aplikasi lama yang berharap untuk terhubung langsung ke jaringan fisik, daripada dirutekan melalui tumpukan jaringan hos Docker.

* none: Untuk kontainer ini, nonaktifkan semua jaringan. Biasanya digunakan bersama dengan driver jaringan khusus. none tidak tersedia untuk layanan swarm.

* Networks Plugin: dapat menginstal dan menggunakan pengaya jaringan pihak ketiga dengan Docker. Plugin ini tersedia dari Docker Hub atau dari vendor pihak ketiga.


### Example Connecting other containers using link system

1. jalankan container webapp dengan image nginx

```syntax
docker container run \
--name webapp -d nginx
```

2. Jalankan container test_curl dengan image ubuntu 22.04
```syntax
sudo docker run \
--name test_curl \
-it --rm ubuntu:22.04 bash
```

```curl http://localhost:80```
=> failed karena curl belum diinstall

```apt update -y && apt install curl -y```
=> working

```curl http://localhost:80```
=> curl: (7) Failed to connect to localhost port 80 after 0 ms: Connection refused.
Karena web server belum didefenisikan di container test_curl using image ubuntu:22.04


3. hubungkan dua container atau container lain using link system
example:

connecting container using link system:

```syntax
sudo docker run \
--name test_curl \
--link webapp:nginx-dev \
-it --rm ubuntu:22.04 bash
```

update and install curl in container using ubuntu image:

```apt update -y && apt install curl -y```

akses container webapp di container using ubuntu:

```apt update -y && apt install curl -y```

```curl http://localhost:80```

4. testing

* masuk ke container webapp using image nginx:

```docker exec -it webapp bash```

=> maka akan muncul
```root@4c0342e4d917:/#```

Gunakan **4c0342e4d917** untuk menguji apakah benar container sudah saling terhubung

Ex:

```curl http://4c0342e4d917:80```





 