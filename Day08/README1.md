# DOCKER

### 1. Pengertian
Docker adalah software open-source yang digunakan untuk meluncurkan (deploy) aplikasi di dalam container virtual. Dengan container virtual ini (containerization), aplikasi bisa dijalankan secara terisolasi di environment yang kompleks sehingga tidak menimbulkan masalah pada environment lainnya.

Cara kerja Docker adalah dengan menciptakan sebuah ruang isolasi untuk meluncurkan aplikasi atau layanan. Ruang isolasi ini disebut Container, seperti ‘wadah’ yang akan menampung suatu benda agar tidak tumpah ke area lain.

Docker container adalah sebuah paket software yang berisi semua dependensi yang diperlukan untuk menjalankan aplikasi tertentu. Semua konfigurasi dan instruksi untuk memulai atau menghentikan container diperintahkan oleh sebuah komponen yang disebut ‘image Docker’.

ketika menjalankan aplikasi di beberapa sistem yang berbeda, dengan container ini, software akan berjalan dengan cara yang sama di environment mana pun. Kapan pun image dijalankan user, container baru akan dibuat.

### 2. Arsitektur Docker 

arsitektur Docker terdiri dari empat komponen utama, yaitu:

* **Client Docker**
komponen utama untuk membuat, mengelola, dan menjalankan aplikasi dalam container. Client Docker adalah metode utama untuk mengontrol server Docker melalui CLI seperti Command Prompt (Windows) atau Terminal (macOS, Linux).

* **Server Docker** 
juga disebut daemon Docker. Server Docker menunggu permintaan REST API yang dibuat oleh client Docker serta mengelola image dan container.

* **Image Docker**
komponen yang memerintahkan server Docker terkait persyaratan tentang cara container Docker dibuat. Image bisa didownload dari website seperti Docker Hub. atau juga bisa membuat custom image, yaitu dengan membuat Dockerfile dan meneruskannya ke server. Perlu diketahui bahwa Docker tidak menghapus image yang tidak digunakan, jadi user harus menghapus data image sendiri agar tidak menumpuk.

* **Registry Docker**
aplikasi sisi server open-source yang digunakan untuk menghosting dan mendistribusikan image Docker. Registry sangat berguna untuk menyimpan image secara lokal dan mengelolanya sepenuhnya. Atau, user bisa mengakses Docker Hub yang tadi disebutkan, yang merupakan repositori image Docker terbesar di dunia.

### 3. Kelebihan dan Kekurangan

a. Kelebihan

* Portabilitas
Docker memungkinkan user membuat atau menginstal aplikasi kompleks di perangkat, dan aplikasi tersebut dijamin bisa berjalan. Docker container memiliki semua yang dibutuhkan aplikasi, hanya dengan sedikit atau bahkan tanpa input dari user.

* Automasi
Automasi membantu developer menghindari tugas yang membosankan dan repetitif, serta menghemat waktu.

* Komunitas
ada lebih dari 9 juta image container yang dihosting di Docker Hub.

b. Kekurangan

* Kecepatan – meskipun akan lebih cepat untuk menjalankan aplikasi melalui Docker container daripada di VM, Docker masih lebih lambat dibandingkan dengan menjalankan aplikasi secara native pada server fisik.

* Kemudahan penggunaan – Docker tidak dimaksudkan untuk menjalankan aplikasi yang memerlukan Graphical User Interface (GUI). yang artinya user harus familiar dengan perintah yang digunakan pada CLI

* Keamanan
Docker berjalan pada sistem operasi host, yang berarti software berbahaya apa pun yang bersembunyi di balik containernya bisa sampai ke mesin host.


### 5. Perbedaan Docker dan VM

Perbedaan Docker dan Virtual Machine adalah, 
* container Docker menggunakan OS yang sama dengan host, 
* VM memiliki OS tamu yang berjalan dari sistem host. Metode operasi ini memengaruhi performa, kebutuhan hardware, dan dukungan OS.
* Meskipun teknologi container Docker lebih unggul pada hampir semua aspek, VM lebih aman karena sistem operasinya tetap terpisah (independen) dari hardware.

![Perbedaan Docker VM](https://user-images.githubusercontent.com/82355684/229448945-70b371f3-cd13-4a41-abcd-892f840bccc1.png)

### 6. Perbandingan Docker dengan Kubernetes

* Docker adalah platform untuk membangun dan menjalankan container, sedangkan Kubernetes adalah sistem orkestrasi (orchestration) container open-source.
* Keduanya tidak bisa dibandingkan secara langsung, karena Docker digunakan dalam pembuatan container, sementara Kubernetes mengelolanya pada skala besar. Namun, Docker menawarkan sistem orkestrasinya sendiri yang disebut Docker Swarm.

![Docker Kubernetes](https://user-images.githubusercontent.com/82355684/229450283-74da8164-7271-4cc3-bf77-21ec9ec23aac.png)


### 7. Perbandingan Docker dengan Jenkins

Docker dan Jenkins itu memiliki perbedaan tujuan.
* Jenkins adalah sistem automasi inti untuk model development CI/CD (Continuous Integration and Continuous Delivery), yang digunakan para developer untuk merilis potongan-potongan kecil kode secara terus-menerus untuk mencegah error penggabungan.
* Docker adalah sistem containerization. Dengan Docker, bisa mencoba software baru tanpa harus menginstalnya secara manual. Docker juga berguna kalau memerlukan software yang harus disiapkan cepat.


# Getting Started With Docker 

6 hal berikut adalah point ynag digunakan dalam perintah docker:

1. Pull image from registry
2. Show list of docker image
3. Running docker image
4. Accessing container
5. View logs
6. Cleanup

Berikut adalah contoh bagaimana cara pull image postgres from registry (docker hub)

1. ```docker pull postgres``` (mengambil docker images terbaru dari docker registry)
```docker images``` (melihat list images yang terbentuk)

--> pull image postgres from registry dan docker images akan terbentuk.

![Screenshot from 2023-04-03 15-56-25](https://user-images.githubusercontent.com/82355684/229469157-9bad535f-9a79-41ba-85a4-a16b853604cd.png)

2. ```docker container run -it --name my_postgres -e POSTGRES_PASSWORD=postgres -d namaImage```

--> menjalankan docker images yang telah dibuat disebut docker container.

![Screenshot from 2023-04-03 15-57-14](https://user-images.githubusercontent.com/82355684/229469149-7da420db-6772-4df3-a354-d8bb4430372b.png)

3. ```docker exec -it ContainerID psql -U namaImage```

--> mengakses postgres yang ada di dalam container

![Screenshot from 2023-04-03 16-04-52](https://user-images.githubusercontent.com/82355684/229469135-dab62572-eb6c-4aea-919c-f085e2f99174.png)

4. 