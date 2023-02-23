## Apa itu Nodejs, NPM, NVM, Composer

### 1. Nodejs

Nodejs adalah adalah runtime environment untuk JavaScript yang bersifat open-source dan cross-platform. Dengan Node.js kita dapat menjalankan kode JavaScript di mana pun, tidak hanya terbatas pada lingkungan browser.
Node.js juga menyediakan banyak library/module JavaScript yang membantu menyederhanakan pengembangan aplikasi web.

### 2. NPM

NPM adalah mengelola package Javascript untuk menginstal modul, berbagi dependensi, dan berbagi tool. Dengan jumlah package yang banyak tersebut, seorang developer dapat terbantu terutama dalam soal waktu pembuatan aplikasi. 






## Cara menjalankan project berbagai bahasa pemrograman

### 1. Reactjs

sebelum menjalankan project react pastikan di lokal sudah terinstal nodejs dan npm/yarn. nodejs digunakan untuk menjalankan kode JavaScript di manapun dan juga menyediakan banyak library/module JavaScrpt yang membantu menyederhanakan aplikasi web. NPM dan Yarn itu sama penggunaannya yaitu untuk mengelola package manager JavaScript untuk menginstall modul, berbagi dependensi dan berbagi tool. Sedangkan NVM juga bisa digunakan untuk mengatur versi dari nodejs yang digunakan pada sebuah project, sehingga NVM dapat memudahkan kita dalam mengganti versi nodejs yang digunakan dalam sebuah project.

**cara running project reactjs**
  1. buka project reactjs dan masuk ke terminal
  2. jalankan perintah *npm install* untuk menginstal package managernya
  3. jalankan perintah *npm start* untuk running project


### 2. Laravel

sebelum menjalankan project, pastikan laptop sudah menginstal composer dan php. kemudian dibutuhkan database, bisa menggunakan phpmyadmin.

**cara running project laravel**
  1. jalankan perintah *cp .en.example .env* untuk mengcopy file .env sementara untuk membuat databassse baru di lokal.
  2. jalankan perintah *composer install* untuk menginstal package manager composer.
  3. jalankan perintah *php artisan key:generate*
  4. kemudian buat database baru di phpmyadmin dengan mneyesuaikan yang ada di file .env pada project. Untuk **DB_HOST=127.0.0.1 , DB_USERNAME=root , DB_PASSWORD={kosongkan} *untuk DB_USERNAME dan DB_PASWWOR itu sesuai dnegan yg ada di lokal* .**
  5. jalankan perintah *php artisan config:cache*
  6. jalankan perintah *php artisan migrate*
  7. jalankan perintah *php artisan serve* maka project akan diarahkan ke server



### 3. Nodejs


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
    
    
### 5. Java
