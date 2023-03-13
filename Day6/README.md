# HOW TO USE WEB SERVER NGINX FOR LARAVEL AND REACT.JS PEMROGRAMAN LANGUAGE

## 1. REACTJS

* Pastikan nginx sudah running dengan baik
* buka terminal dan masuk ke direktori berikut
```cd /etc/nginx/sites-enabled/```
* buat file configurasi baru untuk reactjs 
```sudo nano reactjs.conf```
kemudian isi file seperti berikut:

server {
<<<<<<< HEAD
    listen 80;
    listen [::]:80;

    server_name eno_nih.com;

    location / {
        proxy_pass http://localhost:3000;
    }
=======
	listen 80;
	listen [::]:80;
	
	server_name eno_nih.com
	
	location / {
		proxy_pass http://localhost:3000;
	}
>>>>>>> refs/remotes/origin/main
}


* ```sudo ln -s /etc/nginx/sites-available/reactjs.conf /etc/nginx/sites-enabled/```
* buat hosts untuk akses project react.js di browser:

![hosts](https://user-images.githubusercontent.com/82355684/224642154-9e4adc47-03b0-4539-acbd-561693b53bce.png)

* ```sudo nginx -t```
* ```sudo systemctl reload nginx```
* masuk ke direktori dari file project berada:
```cd MID/Project/reactjs/```
jalankan ```npm run start```

Output:
![reactjs_nginx](https://user-images.githubusercontent.com/82355684/224646540-5d27cc22-31ea-41a3-b71f-7cc74fe4332e.png)


## 2. Laravel

1. install php, composer, mysql dan nginx
2. kemudian pastikan nginx dan mysql aktif
3. buat mysql di terminal dengan cara (**cara install MySQL Server**)
4. pada file ```.env``` yang ada di project laravel konfigurasikan dengan MySQL yang sudah dibuat sebelumnya.
5. selanjutnya buat file configurasi di ```/etc/nginx/sites-available/laravel1.conf``` dengan format sbb:

server {
     listen 80;
     listen [::]:80 ipv6only=on;

     # Log files for Debugging
     access_log /var/log/nginx/vhostlaravel-access.log;
     error_log /var/log/nginx/vhostlaravel-error.log;

     # Webroot Directory for Laravel project
     root /var/www/html/laravel1/public;
     index index.php index.html index.htm;

     # Your Domain Name
     server_name laravel_project.com;

     location / {
             try_files $uri $uri/ /index.php?$query_string;
     }

     # PHP-FPM Configuration Nginx
     location ~ \.php$ {
             try_files $uri =404;
             fastcgi_split_path_info ^(.+\.php)(/.+)$;
             fastcgi_pass unix:/run/php/php8.1-fpm.sock;
             fastcgi_index index.php;
             fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
             include fastcgi_params;
     }
}

6. kemudian lakukan symlink: ```sudo ln -s /etc/nginx/sites-available/laravel1.conf /etc/nginx/sites-enabled/``` 
7. daftarkan domain di direktori ```sudo nano /etc/hosts```

![hosts](https://user-images.githubusercontent.com/82355684/224642154-9e4adc47-03b0-4539-acbd-561693b53bce.png)

8. sudo nginx -t
9. sudo systemctl reload nginx
10. akses di browser dengan domain yang sudah didaftarkan.


**cara install MySQL Server**


1. sudo apt install mysql-client mysql-server -y
2. sudo systemctl status mysql.service
3. jika status mysql inactive, gunakan perintah: sudo systemctl start mysql.service
4. sudo systemctl enable mysql.service

lakukan configurasi MySQL Server untuk project laravel. Berfungsi untuk sebagai wadah database di web server nginx.
* sudo mysql -u root -p
* CREATE DATABASE sample_db;
* CREATE USER 'user_name'@'localhost' IDENTIFIED BY 'user_password';
* GRANT ALL PRIVILEGES ON naya_cake.* TO 'metoo'@'localhost';
* FLUSH PRIVILEGES;
* EXIT

Database yang telah dibuat digunakan untuk mengkonfigurasikan file .env yang ada pada project laravel yang dibuat.

**cara install Project Laravel**

1. masuk ke direktori berikut: cd /var/www/html
2. sudo composer global require laravel/installer
3. sudo composer create-project --prefer-dist laravel/laravel contoh.com
4. sudo chmod -R 755 /var/www/html/contoh.com
5. sudo chown -R www-data:www-data /var/www/html/contoh.com
6. cd contoh.com
7. composer install

Jika sudah ada project lain yang sudah di pull dari github, maka tinggal memindahkannyya ke direktori /var/www/html sebagai contoh: sudo mv /MID/Project/contoh.com /var/www/html
