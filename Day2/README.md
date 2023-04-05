# Apa itu Nodejs, NPM, NVM, Composer

### 1. Nodejs

Nodejs adalah adalah runtime environment untuk JavaScript yang bersifat open-source dan cross-platform. Dengan Node.js kita dapat menjalankan kode JavaScript di mana pun, tidak hanya terbatas pada lingkungan browser.
Node.js juga menyediakan banyak library/module JavaScript yang membantu menyederhanakan pengembangan aplikasi web.

### 2. NPM

NPM adalah mengelola package Javascript untuk menginstal modul, berbagi dependensi, dan berbagi tool. Dengan jumlah package yang banyak tersebut, seorang developer dapat terbantu terutama dalam soal waktu pembuatan aplikasi. 

### 3. YARN (Yet Another Resource Negosiator)

Kegunaannya sama dengan npm yaitu sebagia alternatif package manager selain npm untuk Nodejs. Tujuan awal dikembangkannya Yarn adalah untuk mengatasi masalah yang ada pada npm. Seiring perkembangannya, fitur yang dimiliki kedua package manager ini semakin serupa, namun Yarn tetap menjadi pilihan beberapa pengguna JavaScript

### 3. NVM (Node Version Manager)

NVM adalah sebuah program yang akan membantu kita menggunakan lebih dari satu versi Nodejs di dalam satu komputer. NVM lebih mudah digunakan karena selain untuk menentukan versi Nodejs yang akan digunakan, NVM juga akan membantu kita menginstalnya dan tentunya terupdate dengan versi resmi yang dari website Nodejs.
Kita butuh NVM saat kita membutuhkan Nodejs versi tertentu.

### 4. Composer

composer adalah tools dependency manager untuk project php yang berfungsi sebagai penghubung antara project PHP dengan library dari luar yaitu dengan mengunduh libarary dari packagist.org

**Install di windows**
![install](https://user-images.githubusercontent.com/82355684/221145062-e543424f-66ca-4f72-8632-82fb5c8abe70.png)

**Install di Linux**
![instalpackagemanagerlinux](https://user-images.githubusercontent.com/82355684/223921245-3250ab0a-7faf-4fde-9fba-86a5bf2ebcf0.png)


## Command NPM
* mengecek versi NPM
```npm -v```
* memulai project
```npm init``` diarahkan untuk membuat file package.json
* menginstall modul
```npm install -g``` or ```npm install <package-name>```
* menginstall package sebagai development dependency:
```npm install <package-name> --save-dev```
* menginstall modul secara global pada sistem
```npm install <package-name> --global```
* mengupdate semua package dalam project
```npm update```
* mengupdate npm ke versi terbaru
```npm install npm@latest -g```

## Command YARN
* ```yarn init project_name``` untuk membuat inisialisasi dan membuat dua file konfigurasi yaitu package.json dan yarn.lock
* ```yarn add [package]@[version]``` untuk menentukan versi tertentu untuk setiap package atau library sebagai dependensi bagi proyek
* ```yarn upgrade [package]@[version]``` untuk menentukan versi mana yang akan digunakan untuk mengupdate package
* ```yarn remove [package]``` Untuk menghapus package dari sebuah proyek
* ```yarn install``` untuk menginstal semua dependensi yang ditentukan

**Mengupgrade Yarn**

* Kalau Yarn diinstal dengan npm:
```npm install --global yarn```
* Untuk mengupgrade Yarn ke versi terbaru:
```yarn set version latest```
* Untuk mengupgrade Yarn ke versi tertentu:
```yarn set version [version.number]```
* Pada komputer Unix menggunakan cURL:
```curl --compressed -o- -L https://yarnpkg.com/install.sh | bash```

**Command Yarn**

* yarn add: menambahkan paket untuk digunakan dalam paket  saat ini.
* yarn init: menginisialisasi pengembangan sebuah paket.
* yarn install: menginstal semua dependensi yang didefinisikan dalam berkas package.json.
* yarn publish: mempublikasikan sebuah paket ke packet manager.
* yarn remove: menghapus paket yang tidak terpakai dari paket saat ini.


# Cara menjalankan project berbagai bahasa pemrograman di Windows

### 1. Reactjs

sebelum menjalankan project react pastikan di lokal sudah terinstal nodejs dan npm/yarn. nodejs digunakan untuk menjalankan kode JavaScript di manapun dan juga menyediakan banyak library/module JavaScrpt yang membantu menyederhanakan aplikasi web. NPM dan Yarn itu sama penggunaannya yaitu untuk mengelola package manager JavaScript untuk menginstall modul, berbagi dependensi dan berbagi tool. Sedangkan NVM juga bisa digunakan untuk mengatur versi dari nodejs yang digunakan pada sebuah project, sehingga NVM dapat memudahkan kita dalam mengganti versi nodejs yang digunakan dalam sebuah project.

**cara running project reactjs**
  1. buka project reactjs dan masuk ke terminal
  2. jalankan perintah *npm install* untuk menginstal package managernya
  3. jalankan perintah *npm start* untuk running project
  ![run reactjs](https://user-images.githubusercontent.com/82355684/221145809-17fec268-bbc1-4414-a225-9f8a93a4e4a9.png)

### 2. Laravel

sebelum menjalankan project, pastikan laptop sudah menginstal composer dan php. kemudian dibutuhkan database, bisa menggunakan phpmyadmin.

**cara running project laravel**
  1. jalankan perintah *cp .env.example .env* untuk mengcopy file .env sementara untuk membuat database baru di lokal.
  2. jalankan perintah *composer install* untuk menginstal package manager composer pada project.
  3. jalankan perintah *php artisan key:generate*
  
  ![run laravel1](https://user-images.githubusercontent.com/82355684/221145514-ef43b415-1c71-42ea-a84d-9e374333c51b.png)

  4. kemudian buat database baru di phpmyadmin dengan mneyesuaikan yang ada di file .env pada project. Untuk **DB_HOST=127.0.0.1 , DB_USERNAME=root , DB_PASSWORD={kosongkan} *untuk DB_USERNAME dan DB_PASWWOR itu sesuai dnegan yg ada di lokal* .**

  **.env sebelum dirubah**
  
  ![run laravel2](https://user-images.githubusercontent.com/82355684/221145540-4e0085f8-86c8-4402-8daf-2c1d7efb6d27.png)
 

  **.env sesudah dirubah**
  
  ![run laravel3](https://user-images.githubusercontent.com/82355684/221145568-07296297-1557-4d17-87c8-796dbc61bd53.png)

  5. jalankan perintah *php artisan config:cache*
  6. jalankan perintah *php artisan migrate*
  7. jalankan perintah *php artisan serve* maka project akan diarahkan ke server
  
  ![run laravel4](https://user-images.githubusercontent.com/82355684/221145615-d972ef6b-9a2c-426e-b157-0343131ee618.png)

### 3. Nodejs

yang diperlukan sebelum running project nodejs adalah environment nodejs, npm/yarn, dan nvm untuk mengganti versi dari nodejs yang ada pada aplikasi yang akan di running.

**cara menjalankan project nodejs**
1. npm install
2. npm start
3. node [nama_apps].js

![run nodejs2](https://user-images.githubusercontent.com/82355684/221148539-60767561-f082-4362-8c20-a4875c891230.png)

### 4. Golang

**cara menjalankan project golang:**
  1. masuk ke direktori project golang
  2. masuk ke direktori terkait
  3. jalankan perintah *go run nama_file.go*
  4. end

**perintah dasar golang**

1. go run ==> untuk menjalankan program go yang sudah ditulis
ex: go run nama_file.go
2. go build ==> untuk memformat code go agar sesuai dengan konvensi yang ditetapkan oleh Go
ex: go build nama_file.go
3. go fmt ==> untuk memformat code Go agar sesuai dengan konvensi yang ditetapkan oleh Go
ex: go fmt nama_file.go
4. go get ==> untuk mengunduh dan menginstall paket Go dari repository
ex: go get nama_paket
5. go test ==> untuk menjalankan unit test pada program Go
ex: go test nama_file_test.go
6. go mod ==> untuk mengelola dependensi pada program Go
ex: go mod init nama_modul

# Cara menjalankan project berbagai bahasa pemrograman di Linux

1. React js

* buka project
* ```npm install```
* ```npm start```
![reactjslinux](https://user-images.githubusercontent.com/82355684/223924965-660adbe4-ca66-4961-aa56-ef47df02b0d0.png)

* ```npm run build``` digunakan untuk  membuat production build


2. Laravel


* jalankan perintah *cp .env.example .env* untuk mengcopy file .env sementara untuk membuat database baru di lokal
* jalankan perintah *composer install* untuk menginstal package manager composer pada project.
* jalankan perintah *php artisan key:generate* 
* kemudian buat database baru di phpmyadmin dengan mneyesuaikan yang ada di file .env pada project. Untuk **DB_HOST=127.0.0.1 , DB_USERNAME=root , DB_PASSWORD={kosongkan} *untuk DB_USERNAME dan DB_PASWWOR itu sesuai dnegan yg ada di lokal* .**
* jalankan perintah *php artisan config:cache*
* jalankan perintah *php artisan migrate*
* jalankan perintah *php artisan serve* maka project akan diarahkan ke server




# Apa itu GIT, dan GITHUB

Git adalah sebuah software yang digunakan untuk mencatat perubahan seluruh file atau repository yang ada pada sebuah project
Istilah commit pada git berfungsi untuk menyimpan riwayat perubahan data pada file. Melalui commit developer dapat kembali ke source code sebelumnya.

GitHub merupakan layanan cloud yang berguna untuk menyimpan dan mengelola sebuah project yang dinamakan repository (repo git). Cara kerja pada GitHub harus terkoneksi pada internet sehingga tidak perlu meng-install sebuah software ke dalam perangkat keras. Hal ini memberikan keringanan penyimpanan komputer yang kita gunakan karena file project tersimpan oleh cloud GitHub.

conclusion:
Git merupakan alat version control.
GitHub merupakan alat version control sekaligus penyimpanan cloud.
Kedua platform ini pada konsep kerjanya hampir sama dengan Dropbox dan Google Drive, hanya saja Git dan GitHub bekerja untuk mengolah kode script. Sedangkan DropBox dan Google Drive bertugas untuk mengolah kata.

Prosedur yang diterapkan pada git ini dapat membantu antar divisi project untuk memantau dan menghubungkan (merge) antar ekstensi yang berbeda dengan mudah. Sehingga aplikasi yang dibuat oleh sebuah tim project dapat berfungsi tanpa menghubungkan secara manual.

## perintah pada git

sebelum mengenal git lebih jauh ada perintah yang fungsinya berbeda yaitu git remote dan git clone. perbedaannya adalah Git Remote digunakan untuk mengelola koneksi antara repositori lokal dan jarak jauh, sedangkan Git Clone digunakan untuk menyalin seluruh riwayat perubahan dari repositori jarak jauh ke repositori lokal.

#### menambahkan folder lokal ke repository github
1. buat folder baru dan isi dengan file. folder kosong tidak bisa di push jika tidak ada file.
2. jalankan perintah
  * ```git init```
  * ```git add .```
  * ```git commit -m "add komentar"```
  * ```git branch -M main```
  * buat repository baru di github dan salin link url repo tsb
  * ```git remote add [namabranch] [url https repo]```
  * ```git push -u origin main```

#### mengambil repository github ke lokal
1. buat folder di lokal
2. masuk ke folder tsb
3. lakukan ```git init```
4. lakukan git remote ex: git remote add [nama branch] [url repo] ==> ```git remote add master https://github.com/akun/repo.git```
5. lakukan git pull ex: git pull [URL repo] ==> ```git pull https://github.com/akun/repo.git```

**git clone digunakan untuk mengupdate apa yang telah di update d repository akan terupdate juga di lokal**
```git clone https://github.com/nama-akun/repo.git```

#### cara menghubungkan git lokal dengan github
1. masuk ke direktori yang diinginkan di CMD
2. ```git clone [urlrepo]```
3. ```git pull [nama remote] [namabranch]``` untuk mengambil file dari github ke lokal
4. ```git push [nama remote] [namabranch]``` untuk mengupload kode yang ada di lokal ke github
sebelum di push, ```git add .``` dan ```git commit -m "add komentar"```

#### cara mengganti branch baru
1. buat branch baru ```git branch [namabranchbaru]```
2. masuk ke branch baru ```git checkout [namabranchbaru]```

#### untuk membatalkan perintah di git
1. ```git log --oneline``` untuk melihat list commit yang sudah di rubah
2. ```git revert [kodeperubahan]``` 

#### git ssh
SSH memudahkan user untuk mengelola server tanpa harus datang ke lokasi fisik server. Tidak hanya server saja, user dapat memanfaatkan SSH untuk mengatur dan mengelola komputer maupun perangkat desktop yang ada di jaringan yang sama tanpa harus menyentuh perangkat tersebut.
SSH memungkinkan user lain dapat mengakses repo yang ada di github jika bersifat private dan telah mendapat izin dari pemilik repo tsb.

**cara mengoneksikan ssh di lokal**
1. masuk ke folder baru
2. ```git init```
3. ```git pull git@github.com:enofitriyanti11/MeteorDevopsLearn.git```

