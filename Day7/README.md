# DOCKER

## 1. INSTALL DOCKER

1. update sistem dengan perintah berikut:

```sudo apt update```
```sudo apt upgrade```

![installdocker1](https://user-images.githubusercontent.com/82355684/225030924-af818535-bbbf-4c4b-b37e-f66165a5bd21.png)

![installdocker2](https://user-images.githubusercontent.com/82355684/225030934-9ec36b30-fb9d-41fe-9987-39e3716c4569.png)

2. install paket dependensi yag diperlukan

```sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release```

![installdocker3](https://user-images.githubusercontent.com/82355684/225030944-b914cb56-1e68-4547-a3a1-3740aa588925.png)

3. tambahkan kunci GPG resmi Docker ke sistem

```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg```

4. Tambahkan repository Docker ke sumber software Ubuntu

```echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null```

5. kemudian jalankan perintah berikut unutk memperbaharui paket

```sudo apt update```

![installdocker4](https://user-images.githubusercontent.com/82355684/225030954-8af3aa99-6f44-4bc6-8267-ddba9f97ce4a.png)

6. Install Docker

```sudo apt install docker-ce docker-ce-cli containerd.io```

![installdocker5](https://user-images.githubusercontent.com/82355684/225030963-e596c8ed-89e2-4870-b3bd-7c9d544aecea.png)

7. setelah instalasi selesai, periksa apakah docker berhasil diinstall

```sudo docker run hello-world```

![installdocker6](https://user-images.githubusercontent.com/82355684/225030971-a86b25d0-e90d-4157-8c74-2333acedb371.png)

**Command untuk melihat versi Docker**
* ```docker version```
* ```sudo docker --version```
* ```docker compose version```

**Docker Desktop**
* pastikan docker sudah running dengan baik.
* download docker di link berikut https://docs.docker.com/desktop/install/ubuntu/
* masuk ke direktori tempat hasil download docker
* jalankan perintah : sudo apt install <namafiledocker>.deb
* docker desktop sudah tersedia.

untuk menggunakan docker desktop lakukan login/register terlebih dahulu. 
dengan menjalankan perintah di terminal:
```gpg --generate-key``` kemudian akan diminta username, email dan password
```pass init <generated gpg-id public key>``` digunakan untuk menginisialisasi repositori Password Store (pass) dengan GPG key ID yang telah di-generate sebelumnya. Repositori ini adalah tempat untuk menyimpan password yang dienkripsi dengan menggunakan kunci publik GPG tersebut.




## 2. MEMBUAT DOCKER FILE

1. buat direktori baru: example
```mkdir docker-project```
2. tambahkan file ```Dockerfile``` dan file ```nginx.conf```
* file ```Dockerfile``` digunakan untuk membangun Docker Image dan mengandung instruksi yang diperlukan untuk membangun sebuah image.

```Dockerfile
# Menggunakan base image Ubuntu 22.04
FROM ubuntu:22.04

# Update Ubuntu dan install Nginx
RUN apt-get update && \
    apt-get install -y nginx

# Copy file konfigurasi Nginx ke dalam container
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80 untuk akses ke Nginx
EXPOSE 8080:80

# Jalankan Nginx ketika container dijalankan
CMD ["nginx", "-g", "daemon off;"]
```

* **FROM ubuntu:22.04** = perintah untuk menentukan base image Docker yang digunakan untuk membangun image baru pada OS Ubuntu 22.04
* **RUN apt-get update && \ apt-get install -y nginx** = intsruksi untuk melakukan update pada Ubuntu dan menginstall Nginx sebagai web server.
* **COPY nginx.conf /etc/nginx/nginx.conf** = digunakan untuk menyalin file konfigurasi Nginx dari direktori lokal yang sama dengan Dockerfile ke dalam direktori /etc/nginx/nginx.conf pada container.
* **EXPOSE 8080:80** = instruksi untuk mengekspos port 80 pada container agar dapat diakses dari luar melalui port 8080.
* **CMD ["nginx", "-g", "daemon off;"]** = instruksi untuk menjalankan Nginx pada container ketika container tersebut dijalankan. perintah ini memulai server web Nginx dengan opsi "daemon off" agar berjalan di foreground dan bukan sebagai proses latar belakang.

* file ```nginx.conf``` digunakan untuk mengkonfigurasi server web Nginx.

```nginx.conf
worker_processes 1;

events {
    worker_connections 1024;
}

http {
    server {
        listen 8080;
        server_name localhost;

        location / {
            root /var/www/html;
            index index.html;
        }
    }
}
```
* worker_processes 1; >> Menentukan berapa banyak proses yang akan dijalankan untuk server Nginx. Dalam kasus ini, hanya satu proses yang akan dijalankan.
* events { worker_connections 1024; } >> Mengatur konfigurasi untuk koneksi yang diterima oleh server. Dalam kasus ini, setiap proses server akan dapat menangani hingga 1024 koneksi secara bersamaan.
* http {} >> Merupakan blok konfigurasi untuk modul HTTP di server Nginx
* server {} >> mendefenisikan server block untuk Nginx
* listen 8080; >> Mendefinisikan port yang akan digunakan oleh server Nginx. Dalam kasus ini, server akan mendengarkan koneksi pada port 8080.
* server_name localhost; >> Menentukan nama domain yang akan digunakan untuk server. Dalam kasus ini, nama domain adalah localhost.
* location / {} >> mendefenisikan bagian konfigurasi untuk lokasi root
* root /var/www/html; >> Menentukan direktori root di mana file index.html dan file lainnya dapat ditemukan.
* index index.html; >> Menentukan file index yang akan diakses ketika pengguna membuka alamat root server. Dalam kasus ini, file yang akan diakses adalah index.html.

3. buka terminal di teks editor. jalankan perintah 

```docker build -t ubuntu-nginx:latest .``` untuk membuat docker image
```docker run -d -p 8080:80 ubuntu-nginx:latest``` untuk menjalankan docker container di port 8080

Hasil:

![dockerfilecreate](https://user-images.githubusercontent.com/82355684/225241437-45c5d9b3-73df-4c77-ae50-340f412ca219.png)

![dockerfilerunning](https://user-images.githubusercontent.com/82355684/225241447-ef63fed8-667d-4d28-bd52-4ad3d4c1195f.png)
