# HOW TO USE WEB SERVER NGINX FOR LARAVEL AND REACT.JS PEMROGRAMAN LANGUAGE

## 1. REACTJS

* Pastikan nginx sudah running dengan baik
* buka terminal dan masuk ke direktori berikut
```cd /etc/nginx/sites-enabled/```
* buat file configurasi baru untuk reactjs 
```sudo nano reactjs.conf```
kemudian isi file seperti berikut:

server {
	listen 80;
	listen [::]:80;

	server_name eno_nih.com;

	location / {
	  proxy_pass  http://localhost:3000;
	}
}

* ```sudo ln -s /etc/nginx/sites-available/reactjs.conf /etc/nginx/sites-enabled/```
* buat hosts untuk akses project react.js di browser:

![hosts](https://user-images.githubusercontent.com/82355684/224642154-9e4adc47-03b0-4539-acbd-561693b53bce.png)

* ```sudo nginx -t```
* ```sudo systemctl reload nginx```
* masuk ke direktori dari file project berada:
```cd MID/Project/reactjs/```
jalankan ```npm run start```

