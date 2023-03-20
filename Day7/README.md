# DOCKER

## 1. INSTALL DOCKER

#### 1. update sistem dengan perintah berikut:

```sudo apt update```
```sudo apt upgrade```

![installdocker1](https://user-images.githubusercontent.com/82355684/225030924-af818535-bbbf-4c4b-b37e-f66165a5bd21.png)

![installdocker2](https://user-images.githubusercontent.com/82355684/225030934-9ec36b30-fb9d-41fe-9987-39e3716c4569.png)

#### 2. install paket dependensi yag diperlukan

```sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release```

![installdocker3](https://user-images.githubusercontent.com/82355684/225030944-b914cb56-1e68-4547-a3a1-3740aa588925.png)

#### 3. tambahkan kunci GPG resmi Docker ke sistem

```curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg```

#### 4. Tambahkan repository Docker ke sumber software Ubuntu

```echo
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

#### 5. kemudian jalankan perintah berikut unutk memperbaharui paket

```sudo apt update```

![installdocker4](https://user-images.githubusercontent.com/82355684/225030954-8af3aa99-6f44-4bc6-8267-ddba9f97ce4a.png)

#### 6. Install Docker

```sudo 
sudo apt install docker-ce docker-ce-cli containerd.io
```

![installdocker5](https://user-images.githubusercontent.com/82355684/225030963-e596c8ed-89e2-4870-b3bd-7c9d544aecea.png)

#### 7. setelah instalasi selesai, periksa apakah docker berhasil diinstall

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

```gpg --generate-key``` kemudian akan diminta username, email dan password.

```pass init <generated gpg-id public key>``` digunakan untuk menginisialisasi repositori Password Store (pass) dengan GPG key ID yang telah di-generate sebelumnya. Repositori ini adalah tempat untuk menyimpan password yang dienkripsi dengan menggunakan kunci publik GPG tersebut.




## 2. MEMBUAT DOCKER FILE

1. buat direktori baru: example
```mkdir docker-project```
2. tambahkan file ```Dockerfile``` dan file ```nginx.conf```.
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
* **RUN apt-get update && \ apt-get install -y nginx** = instruksi untuk melakukan update pada Ubuntu dan menginstall Nginx sebagai web server.
* **COPY nginx.conf /etc/nginx/nginx.conf** = digunakan untuk menyalin file konfigurasi Nginx dari direktori lokal yang sama dengan Dockerfile ke dalam direktori /etc/nginx/nginx.conf pada container.
* **EXPOSE 8080:80** = instruksi untuk mengekspos port 80 pada container agar dapat diakses dari luar melalui port 8080.
* **CMD ["nginx", "-g", "daemon off;"]** = instruksi untuk menjalankan Nginx pada container ketika container tersebut dijalankan. perintah ini memulai server web Nginx dengan opsi "daemon off" agar berjalan di foreground dan bukan sebagai proses latar belakang.

* file **nginx.conf** digunakan untuk mengkonfigurasi server web Nginx.

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
* ```worker_processes 1;``` >> Menentukan berapa banyak proses yang akan dijalankan untuk server Nginx. Dalam kasus ini, hanya satu proses yang akan dijalankan.
* ```events``` { worker_connections 1024; } >> Mengatur konfigurasi untuk koneksi yang diterima oleh server. Dalam kasus ini, setiap proses server akan dapat menangani hingga 1024 koneksi secara bersamaan.
* ```http {}``` >> Merupakan blok konfigurasi untuk modul HTTP di server Nginx
* ```server {}``` >> mendefenisikan server block untuk Nginx
* ```listen 8080;``` >> Mendefinisikan port yang akan digunakan oleh server Nginx. Dalam kasus ini, server akan mendengarkan koneksi pada port 8080.
* ```server_name localhost;``` >> Menentukan nama domain yang akan digunakan untuk server. Dalam kasus ini, nama domain adalah localhost.
* ```location / {}``` >> mendefenisikan bagian konfigurasi untuk lokasi root
* ```root /var/www/html;``` >> Menentukan direktori root di mana file index.html dan file lainnya dapat ditemukan.
* ```index index.html;``` >> Menentukan file index yang akan diakses ketika pengguna membuka alamat root server. Dalam kasus ini, file yang akan diakses adalah index.html.

3. buka terminal di teks editor. jalankan perintah 

```docker build -t ubuntu-nginx:latest .``` untuk membuat docker image.

```docker run -d -p 8080:80 ubuntu-nginx:latest``` untuk menjalankan docker container di port 8080

Hasil:

![dockerfilecreate](https://user-images.githubusercontent.com/82355684/225241437-45c5d9b3-73df-4c77-ae50-340f412ca219.png)

![dockerfilerunning](https://user-images.githubusercontent.com/82355684/225241447-ef63fed8-667d-4d28-bd52-4ad3d4c1195f.png)


## 3. Perintah Docker

Berikut adalah beberapa perintah dasar pada Docker:

1. ```docker run```: menjalankan sebuah kontainer baru dari image yang ditentukan.

2. ```docker stop```: menghentikan sebuah kontainer yang sedang berjalan.

3. ```docker ps```: menampilkan daftar kontainer yang sedang berjalan.

4. ```docker images```: menampilkan daftar image yang tersimpan di sistem.

5. ```docker rm```: menghapus sebuah kontainer yang sudah tidak digunakan.

6. ```docker rmi```: menghapus sebuah image yang sudah tidak digunakan.

7. ```docker build```: membuat image baru dari Dockerfile.

8. ```docker push```: mengunggah sebuah image ke Docker Registry.

9. ```docker pull```: mengunduh sebuah image dari Docker Registry.

10. ```docker exec```: menjalankan sebuah perintah di dalam kontainer yang sedang berjalan.

11. ```docker logs```: menampilkan log dari sebuah kontainer.

12. ```docker network```: mengelola jaringan Docker.

13. ```docker volume```: mengelola volume Docker.

14. ```docker-compose```: mengelola aplikasi multi-kontainer dengan file YAML.


## 4. Reverse Proxy Nginx

Untuk melakukan reverse proxy, pastikan sudah menyiapkan docker image aplikasi yang ingin dijalankan di Nginx. Nginx tidak bisa jalan jika docker containernya tidak running. 
Langkahnya sbb:
* buat Dockerfile di file project React.js, dan running docker image dari project React.js. kemudian running di browser
![image](https://user-images.githubusercontent.com/82355684/226278138-bb0f3624-fe8c-411e-b394-58bdbc29022e.png)

![Screenshot from 2023-03-20 14-24-40](https://user-images.githubusercontent.com/82355684/226277238-1b1a3869-617f-4275-8175-e8a298c45e3b.png)

![Screenshot from 2023-03-20 14-23-52](https://user-images.githubusercontent.com/82355684/226277240-eb96f58e-b9c6-48d9-9c40-4a04972267c6.png)

* buat file konfigurasi untuk reactjs di nginx : ```sudo nano /etc/nginx/sites-available/reactjs.conf``` seperti berikut:
![Screenshot from 2023-03-20 14-34-08](https://user-images.githubusercontent.com/82355684/226277230-6ce5a23a-bacb-41cf-a089-b8542a8e531e.png)

* defenisikan IP di ```sudo nano /etc/hosts``` seperti gambar berikut:
![Screenshot from 2023-03-20 14-31-07](https://user-images.githubusercontent.com/82355684/226277235-a2a911a4-0f6b-456e-9f63-11fc0dca0258.png)

* di terminal, jalankan perintah 
+ ```sudo nginx -t```
+ ```sudo systemctl reload nginx```

![Screenshot from 2023-03-20 14-34-38](https://user-images.githubusercontent.com/82355684/226277215-8ebbe51d-7f08-442a-bf64-0babb6de05ec.png)