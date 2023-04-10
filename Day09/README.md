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

#### Command Docker 

- List all Docker Images
```docker images -a```
- List All Running Docker Containers
```docker ps```
- List All Docker Containers
```docker ps -a```
- Start a Docker Container
```docker start <container name>```
- Stop a Docker Container
```docker stop <container name>```
- Remove a Docker Image
```docker rmi <image name>```
- SSH Into a Running Docker Container
this will give you a bash shell in the container.
```sudo docker exec -it <container name> bash```


# Getting Started With Dockerfile

Dockerfile Syntax

* From - The base image to use.
* Run - Runs commands ketika building docker image.
* Workdir - direktori kerja ketika container running.
* Copy - Copy Files.
* CMD - Runs commands when running the container.
* Expose - memberi alamat port yang dapat diakses.

Example:

1. create dockerfile for React.js Project

```Dockerfile React.js
# image docker berisi node.js versi 14 diatas alpine linux
FROM node:14-alpine

# direktori kerja yang dibentuk pada docker image ada di /app 
WORKDIR /app

# copy semua file package.json yang ada di direktori lokal ke direktori kerja yang ada di image docker.
COPY package*.json ./

# jalankan perintah npm install utk menginstal semua dependensi yang ada/didefenisikan di dlm file package.json
RUN npm install

# copy semua file dari lokal ke direktori kerja yg ada di image docker
COPY . .

# jalankan perintah npm run build 
RUN npm run build

# port yg akan digunakan aplikasi adalah port 3000 (port yg dgunakan utk menjalankan aplikasi node.js) 
EXPOSE 3000

# utk menjalankan perintah npm start ketika container dijalankan dari image docker.
CMD ["npm", "start"]
```

2. jalankan command docker

![image](https://user-images.githubusercontent.com/82355684/230816072-58cf441e-abc3-4696-a158-6423e74986cd.png)


3. hasil dockerfile yang diakses di browser

![image](https://user-images.githubusercontent.com/82355684/230816007-150a11b7-afa5-4132-b2a8-315039cf7759.png)

