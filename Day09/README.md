# DOCKERFILE

Dockerfile digunakan untuk membuat image Docker menggunakan perintah build.
Dengan image Docker, pengguna mana pun dapat menjalankan kode untuk membuat kontainer Docker
kontainer.
Setelah image Docker dibuat, citra tersebut diunggah ke dalam registri Docker.
Dari registri Docker, pengguna dapat memperoleh image Docker dan membangun kontainer baru kapan pun.

![image](https://user-images.githubusercontent.com/82355684/230042067-f4d12410-ca07-4a89-bd13-e143761f673a.png)

#### Docker Image

* image Docker adalah templat dari Docker container
* Sebuah image dibangun menggunakan Dockerfile
* Ia disimpan dalam repositori Docker atau Docker hub
* Lapisan image adalah sistem berkas yang hanya dapat dibaca sistem berkas

#### Docker Container

* Container adalah contoh runtime dari citra Docker
* Container dibuat menggunakan Docker image
* Container disimpan di dalam daemon Docker
* Setiap lapisan container adalah sistem berkas baca tulis sistem berkas

#### Perbedaan Registry dan Repository

##### Registry
* Registri Docker adalah sumber terbuka layanan sisi server yang digunakan untuk menghosting dan mendistribusikan image Docker
* Docker juga memiliki registri defaultnya sendiri yang disebut Docker Hub

##### Repository
* Repositori adalah kumpulan dari beberapa versi image Docker
* Ini disimpan dalam registri Docker
* Ini memiliki dua jenis: publik dan privat repositori

