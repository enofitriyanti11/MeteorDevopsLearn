# HOW TO USE WEB SERVER NGINX FOR LARAVEL AND REACT.JS PEMROGRAMAN LANGUAGE

## 1. REACTJS

* Pastikan nginx sudah running dengan baik
* lokasi project ada di ```/var/www/html```
* untuk mendapatkan file index.html, jalankan perintah **npm run build**
* buka terminal dan masuk ke direktori berikut
```cd /etc/nginx/sites-available/```
* buat file configurasi baru untuk reactjs 
```sudo nano reactjs.conf```
kemudian isi file konfigurasi seperti berikut:

```server
server {
    listen 80;
    listen [::]:80;

    server_name reactjsproject.com;

    location / {
        root /var/www/html/reactjs/build;
        index index.html;
        try_files $uri /index.html;
    }
}
```

* ```sudo ln -s /etc/nginx/sites-available/reactjs.conf /etc/nginx/sites-enabled/```
* buat hosts untuk akses project react.js di browser:

![hosts reactjs](https://user-images.githubusercontent.com/82355684/224885777-25630e4d-2bdf-4a8d-8de0-b409f841ea43.png)

* ```sudo nginx -t```
* ```sudo systemctl reload nginx```

Output:

![nginx reactjs](https://user-images.githubusercontent.com/82355684/224885861-981573c6-16e4-46fd-9823-582e2167125a.png)


## 2. Laravel

1. install php, composer, mysql dan nginx
2. kemudian pastikan nginx dan mysql aktif
3. buat mysql di terminal dengan cara (**cara install MySQL Server**)
4. pada file ```.env``` yang ada di project laravel konfigurasikan dengan MySQL yang sudah dibuat sebelumnya.
5. selanjutnya buat file configurasi di ```/etc/nginx/sites-available/laravel1.conf``` dengan format sbb:

```server
server {
    listen 80;
    listen [::]:80 ipv6only=on;

    # Log files for Debugging
    access_log /var/log/nginx/vhostlaravel-access.log;
    error_log /var/log/nginx/vhostlaravel-error.log;

    # Webroot Directory for Laravel Project
    root /var/www/html/laravel1/public;
    index index.php indexx.html index.htm;

    # Domain
    server_name laravelproject.com;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    # PHP-FPM Configuration Nginx
    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass unix:run/php//php8.1-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
```

6. kemudian lakukan symlink: ```sudo ln -s /etc/nginx/sites-available/laravel1.conf /etc/nginx/sites-enabled/``` 
7. daftarkan domain di direktori ```sudo nano /etc/hosts```

![hosts](https://user-images.githubusercontent.com/82355684/224642154-9e4adc47-03b0-4539-acbd-561693b53bce.png)

8. ```sudo nginx -t```
9. ```sudo systemctl reload nginx```
10. akses di browser dengan domain yang sudah didaftarkan.


**cara install MySQL Server**


1. ```sudo apt install mysql-client mysql-server -y```
2. ```sudo systemctl status mysql.service```
3. jika status mysql inactive, gunakan perintah: ```sudo systemctl start mysql.service```
4. ```sudo systemctl enable mysql.service```

lakukan configurasi MySQL Server untuk project laravel. Berfungsi untuk sebagai wadah database di web server nginx.
* ```sudo mysql -u root -p```
* ```CREATE DATABASE sample_db;```
* ```CREATE USER 'user_name'@'localhost' IDENTIFIED BY 'user_password';```
* ```GRANT ALL PRIVILEGES ON naya_cake.* TO 'metoo'@'localhost';```
* ```FLUSH PRIVILEGES;```
* ```EXIT```

Database yang telah dibuat digunakan untuk mengkonfigurasikan file .env yang ada pada project laravel yang dibuat.

**cara install Project Laravel**

1. masuk ke direktori berikut: ```cd /var/www/html```
2. ```sudo composer global require laravel/installer```
3. ```sudo composer create-project --prefer-dist laravel/laravel contoh.com```
4. ```sudo chmod -R 755 /var/www/html/contoh.com```
5. ```sudo chown -R www-data:www-data /var/www/html/contoh.com```
6. ```cd contoh.com```
7. ```composer install```

Jika sudah ada project lain yang sudah di pull dari github, maka tinggal memindahkannyya ke direktori ```/var/www/html``` sebagai contoh: ```sudo mv /MID/Project/contoh.com /var/www/html```


## Konfigurasi Nginx Untuk aplikasi Laravel

```server
server {
    listen 80;
    server_name laravel.com
    root /var/www/html/laravel/public;
    index index.php index.html;
    charset utf-8;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

}
```


bagian-bagian konfigurasi sebagai berikut:

1. Server Block
* berisi informasi tentang server yang akan digunakan seperti nama domain atau alamat IP dan port yang digunakan.
2. Listen
* digunakan untuk menentukan port yang akan digunakan oleh Nginx. Contohnya port yang digunakan adalah 80.
3. Server Name
* digunakan untuk menentukan nama domain atau alamat IP Server. 
4. Root
* bagian ini untuk menetukan direktori root aplikasi Laravel. 
5. Index
* bagian index menentukan file yang akan ditampilkan jika user mengakses direktori root. 
6. Charset
* digunakan untuk menentukan set karakter oleh server. set karakter yang digunakan utf-8
7. Location
Location menentukan cara server menangani permintaan yang masuk. Ada dua lokasi yang didefenisikan yaitu ```/``` dan ```~\.php$```.
* ```/``` untuk menangani permintaan yang tidak mengandung ekstensi file
* ```~\.php$``` untuk menangani permintaan yang mengandung ekstensi file ```.php```
8. Try Files
* digunakan untuk menentukan urutan file yang dicoba oleh server saat mencari file yang cocok dengan permintaan user. pada contoh diatas, server mencoba untuk menemukan file yang cocok dengan URI yang diminta, kemudian mencoba untuk menemukan direktori dengan nama yang sama dan akhirnya mencoba untuk menjalankan file ```index.php``` dengan parameter query string.
9. FastCGI
* digunakan unutk menentukan bagaimana server akan menjalankan script PHP. Pada conoth diatas, server akan menghubungkan ke socket Unix yang dijalankan oleh PHP-FPM dan akan mengirimkan informasi tentang script yang diminta serta konfigurasi lainnya. Konfigurasi ```SCRIPT_FILENAME``` menentukan nama file yang akan dijalankan oleh PHP-FPM. Bagian ```include fastcgi_params``` adalah direktif yang memuat file konfigurasi standar untuk FastCGI.