# Kesimpulan Task Sebelumnya

## 1. Apa itu Devops
Devops adalah sebuah culture yang posisinya berada diantara tim Development dan tim Operations
Devops merupakan teknologi baru yang dapat mempermudah dan mempercepat proses pembuatan sebuah product IT atau software.

#### Siklus Devops Ada 8

a. Plan
Devops berperan dalam merencanakan apa yag harus dilakukan selama siklus ini dan membuat rencana untuk memenuhi tujuan bisnis. Tujuan utamanya adalah untuk memastikan bahwa semua anggota tim memahami tujuan, ruang lingkup, dan Batasan proyek atau produk.
Tools yang umum digunakan adalah JIRA, Trello

b. Code
Devops berperan dalam berkolaborasi dengan tim Development dalam mengelola code project yang sedang digunakan.
Tools yang digunakan yaitu untuk menyimpan code (Git, GitHub, Gitlab), Text Editor (Visual Studio Code, Visual Studio).

c. Build
Devops berperan dalam build dan menguji code dapat berjalan dengan baik (running well) dan mendeteksi adanya bugs. Bagian ini biasanya dilakukan secara otomatis menggunakan tools Jenkins atau GitLab CI/CD

d. Test
Tahap ini melibatkan pengujian kode atau aplikasi yang telah dibangun untuk memastikan bahwa ia berfungsi dengan baik dan sesuai dengan kebutuhan. Hal ini juga untuk memastikan kualitas produk yang dihasilkan serta pengujian keamanan dan kinerja. Tim DevOps biasanya melakukan pengujian otomatis dan manual untuk memastikan aplikasi berfungsi dengan baik.
Tool yang digunakan Selenium, Appium atau TestComplete (untuk pengujian fungsional), JMeter atau LoadRunner (untuk pengujian beban), dan SonarQube (untuk pengujian keamanan).

e. Release
Tahap ini melibatkan persiapan untuk merilis aplikasi ke lingkungan produksi. Tim DevOps akan memeriksa bahwa aplikasi telah diuji dengan baik dan sudah siap untuk di release. Ini termasuk dokumentasi, pelaporan, dan persiapan infrastruktur.
Tools yang digunakan yaitu Jenkins, CircleCI, atau Gitlab CI/CD (untuk integrasi berkelanjutan) dan Docker atau Kubernetes (untuk manajemen kontainer).

f. Deploy
Tahap ini melibatkan pengiriman aplikasi ke lingkungan produksi. Tim DevOps akan menggunakan alat seperti Ansible atau puppet untuk mengotomasi proses pengiriman produk.
Tools yang digunakan Ansible atau Chef (untuk manajemen konfigurasi), Terraform atau CloudFormation (untuk manajemen infrastruktur) dan AWS CodeDeploy atau Google Cloud Deployment Manager (untuk pengiriman code).

g. Operate
Tahap ini melibatkan operasi aplikasi dalam lingkungan produksi. Tim DevOps memastikan bahwa aplikasi berjalan dengan baik dan dapat diakses oleh pengguna. Tools yang digunakan yaitu Nagios, Zabbix atau Promotheus (untuk monitoring kinerja).

h. Monitor
Tahap ini melibatkan pemantauan aplikasi dalam lingkungan produksi. Tim DevOps akan memantau performa aplikasi dengan melibatkan pengumpulan dan analisis data untuk memantau kinerja produk yang telah dirilis. 
Tools yang digunakan ELK Stck atau Splunk (untuk analisis log). Setiap alat yang dipilih tergantung pada kebutuhan tim development dan tim operation serta lingkungan teknis yang digunakan.

   

## 2. Apa itu Nodejs, NPM, YARN, NVM, Composer, PHP

a. Nodejs
adalah sebuah platform yang digunakan untuk menjalankan semua yang berhubungan dengan bahasa pemrograman Javascript

b. NPM
adalah sebuah package manager yang digunakan untuk menginstall semua libraries untuk menjalankan semua yang dibutuhkan oleh project.

c. YARN
adalah sebuah package manager yang fungsinya sama dengan NPM karena dikembangkan sebagai pengganti dari NPM. Tapi yang lebih sering digunakan adalah YARN oleh programmer karena lebih fleksibel

d. NVM
adalah membantu user untuk mengganti versi nodejs yang diperlukan sesuai dengan kebutuhan programmers.

e. Composer
adalah sebuah package manager untuk menjalankan project PHP seperti Framework Laravel

f. PHP
adalah platform yang digunakan untuk menjalankan project yang menggunakan bahasa pemrograman PHP
    

## 3. How to RUn Project Any Programming Language

1. Reactjs
2. Laravel
3. Golang
4. Python


## 4. Git & GitHub

Git merupakan alat version control.
GitHub merupakan alat version control sekaligus penyimpanan cloud.
Kedua platform ini pada konsep kerjanya hampir sama dengan Dropbox dan Google Drive, hanya saja Git dan GitHub bekerja untuk mengolah kode script. Sedangkan DropBox dan Google Drive bertugas untuk mengolah kata.

Prosedur yang diterapkan pada git ini dapat membantu antar divisi project untuk memantau dan menghubungkan (merge) antar ekstensi yang berbeda dengan mudah. Sehingga aplikasi yang dibuat oleh sebuah tim project dapat berfungsi tanpa menghubungkan secara manual.
Sebelum mengenal git lebih jauh ada perintah yang fungsinya berbeda yaitu git remote dan git clone. perbedaannya adalah Git Remote digunakan untuk mengelola koneksi antara repositori lokal dan jarak jauh, sedangkan Git Clone digunakan untuk menyalin seluruh riwayat perubahan dari repositori jarak jauh ke repositori lokal.

**Perintah Pada Git**

**menambahkan folder lokal ke repository github*

1. buat folder baru dan isi dengan file. folder kosong tidak bisa di push jika tidak ada file.
2. jalankan perintah
* ```git init```
* ```git add .```
* ```git commit -m "add komentar"```
* ```git branch -M main```
* buat repository baru di github dan salin link url repo tsb
* ```git remote add [namabranch] [url https repo]```
* ```git push -u origin main```
    
 **mengambil repository github ke lokal**
 1. buat folder di lokal
 2. masuk ke folder tsb
 3. lakukan ```git init```
 4. lakukan git remote ex: git remote add [nama branch] [url repo] ==> ```git remote add master git@github.com:enofitriyanti11/MeteorDevopsLearn.git```
 5. lakukan git pull ex: git pull [URL repo] ==> ```git pull git@github.com:enofitriyanti11/MeteorDevopsLearn.git```
 
 **git clone digunakan untuk mengupdate apa yang telah di update d repository akan terupdate juga di lokal**
 ```git clone git@github.com:enofitriyanti11/MeteorDevopsLearn.git```
 
 **cara menghubungkan git lokal dengan github**
 1. masuk ke direktori yang diinginkan di CMD
 2. ```git clone [urlrepo]```
 3. ```git pull [nama remote] [namabranch]``` untuk mengambil file dari github ke lokal
 4. ```git push [nama remote] [namabranch]``` untuk mengupload kode yang ada di lokal ke github
 sebelum di push, ```git add .``` dan ```git commit -m "add komentar"```
 
 **cara mengganti branch baru**
 1. buat branch baru ```git branch [namabranchbaru]```
 2. masuk ke branch baru ```git checkout [namabranchbaru]```
 
 **untuk membatalkan perintah di git**
 1. ```git log --oneline``` untuk melihat list commit yang sudah di rubah
 2. ```git revert [kodeperubahan]``` 
 
 **git ssh**
 
 SSH memudahkan user untuk mengelola server tanpa harus datang ke lokasi fisik server. Tidak hanya server saja, user dapat memanfaatkan SSH untuk mengatur
 dan mengelola komputer maupun perangkat desktop yang ada di jaringan yang sama tanpa harus menyentuh perangkat tersebut.
 SSH memungkinkan user lain dapat mengakses repo yang ada di github jika bersifat private dan telah mendapat izin dari pemilik repo tsb.
 
 **cara mengoneksikan ssh di lokal**
 1. masuk ke folder baru
 2. ```git init```
 3. ```git pull git@github.com:enofitriyanti11/MeteorDevopsLearn.git```



## 5. Text Editor di Linux

1. Nano

![nano_](https://user-images.githubusercontent.com/82355684/222968294-fed4c909-38a7-4ef8-b6e9-72d4cdce051f.png)

2. Vi

![vi_](https://user-images.githubusercontent.com/82355684/222968321-68ab67f7-01b4-4d88-8971-47cacd4a059a.png)

3. Vim

![vim_](https://user-images.githubusercontent.com/82355684/222968328-1d5cd1fd-7160-4f82-9b0e-ade8973fc7e0.png)

4. Pico

![pico_](https://user-images.githubusercontent.com/82355684/222968338-1929ee9e-6e25-478a-94af-a799f4508aca.png)

5. Jed

![jed_](https://user-images.githubusercontent.com/82355684/222968364-8784a0d9-735a-4212-a8f0-5c30f696d23a.png)



## 6. Manipulation Text Command Line Linux

1. awk

digunakan untuk pemindaian baris dami baris dan membandingkan baris dengan pola.
ex:
awk '{print $1}' namafile.txt

![awk](https://user-images.githubusercontent.com/82355684/221814421-cc2ddc2e-64bc-4df4-8216-5c115a5afa21.png)

2. grep

digunakan untuk mencari kata dalam file.
ex:
```grep -i kataygdicari namafile.txt``` untuk mencari kata tanpa memerhatikan besar kecilnya huruf. 
```grep -l kataygdicari ./*``` untuk mencari sebuah kata di kumpulan file.

![grep](https://user-images.githubusercontent.com/82355684/221815299-37291bd2-7e4f-467c-af31-e3ec23881a9e.png)

3. sort

digunakan untuk menampilkan konten dalam format yang terurut.
perintah ```sort``` untuk secara ascending, dan perintah ```sort -r``` secara descending.

ex:

![sort1](https://user-images.githubusercontent.com/82355684/221816531-a77ea4ea-4ce9-44c2-a28b-88249400204b.png)

![sort2](https://user-images.githubusercontent.com/82355684/221817942-134c3c4b-46fc-4470-b999-5fcfcb85888a.png)

4. sed

digunakan untuk mengganti teks menjadi tampilan kata yang ditentukan. misalnya kata **two** pada baris ke empat pada file diganti menjadi **2** maka digunakan ```sed -n '4 s/two/2/p' namafile.txt```

ex:

![sed](https://user-images.githubusercontent.com/82355684/221827043-b3a2867e-31ca-4403-afe9-48767865b48b.png)

ex: penggantian kata secara global gunakan fleg **-g**
![sed2](https://user-images.githubusercontent.com/82355684/221828301-6ade42d1-351c-49ad-8cc6-99b4d1da19d2.png)

5. cut

digunakan untuk memotong ata mengekstrak bagian teks dari baris atau file.
```cut -b 1 filebaru.txt``` untuk menampilkan huruf pertama dari kata awal dari setiap baris
```cut -d " " -f 1 filebaru.txt``` untuk menampilkan kata awal dari setiap baris.

![cut](https://user-images.githubusercontent.com/82355684/221829827-37c5b0db-d07b-4176-8e12-02ea831fefd2.png)


## 7. Perintah-perintah Linux

1. ```pwd``` untuk mengetahui directory mana yang sedang dibuka.
2. ```ls``` untuk mengetahui file apa saja yang ada di dalam directory.
```ls -a``` untuk melihat isi direktori beserta file tersembunyi.
```ls -l``` untuk melihat isi direktori dan detailnya.
3. ```cd namafolder``` untuk masuk ke sebuah directory. ```cd ..``` untuk keluar dari directory.
4. ```cat namafile.txt``` untuk membaca isi file. ```cat > namafile.txt``` untuk menambahkan isi file. ```cat >> namafile.txt``` untuk menambahkan isi file ke file yang sudah ada.
5. ```mkdir namafolder``` untuk membuat folder baru.
6. ```touch namafile.txt``` untuk membuat file baru.
7. ```mv namafilelama.txt namafilebaru.txt``` untuk mengganti nama file lama ke baru. 
8. ```nano``` untuk menampilakn text editor nano.
9. ```vi``` untuk menampilkan text editor vi.
10. ```find``` untuk mencari file yang berlokasi di dalam direktori.
11. ```head -n 3 namafile.txt``` untuk menampilkan baris isi text dalam file.
12. ```tail -n 2 namafile.txt``` untuk menampilkan beberapa baris terakhir saja.
13. ```diff namafile1.txt namafile2.txt``` untuk membandingkan isi dua file berdasarkan baris demi baris.  
14. ```uname -a``` untuk melihat informasi linux yang sedang running.
15. ```grep kataygdicari namafile.txt``` untuk mencari kata dalam file yang diinginkan.
```grep -r katayag dicari``` untuk mencari kata dalam file yang ada di dalam direktori.
16. ```rm file.txt``` untuk menghapus file.
```rm -i file.txt file.txt``` untuk menghapus file yang ada dalam direktori dengan memunculkan konfirmasi Y/N.
```rm -r namadirektori``` untuk menghapus direktori yang ada isi filenya.
17. ```echo "teks yang ingin dimasukkan" > namafile.txt``` untuk menambahkan teks ke dalam file yang baru dibuat.
```echo "teks yang ditambahkan" >> namafile.txt``` untuk menambahkan isi teks ke dalalm file yang sudah ada.
18. ```rmdir namadirektori``` untuk menghapus direktori.


![commandline](https://user-images.githubusercontent.com/82355684/221823256-74c93a5a-bb30-4d87-8ede-db89a6a4b795.png)

        


## 8. What happens behind the scenes when you access to a website

![WebServerInformation](https://user-images.githubusercontent.com/82355684/222687517-a058ca10-2318-4044-96b2-e847297cbc7c.png)

Berdasarkan gambar kita dapat melihat bahwa untuk mengakses sebuah informasi di browser itu memerlukan internet. Bagaimana cara kerjanya?

1. Semua client memiliki IP Address yang digunakan untuk dapat terhubung ke server yang menyimpan berbagai data yang dibutuhkan. 
2. IP Adress yang dimiliki client itu masih Local Network, sehingga belum bisa mengakses informasi yang ada di server.
3. Agar bisa terhubung, IP Adress akan terkoneksi ke Provider yang merupakan jalan untuk bisa terhubung ke internet (Public Network), sehingga IP Adress yang dimiliki oleh client akan terhubung terlebih dahulu ke router, dan dari router terhubung ke provider yang digunakan. Contoh provider: Telkomsel, Indihome, Indosaat, dll.
4. Ketika mencari sebuah informasi di web browser (request), kita akan mengetikkan nama domain. Karena server hanya mengenali IP Adress, maka domain tadi akan ditranslate oleh DNS menjadi sebuah IP Adress yang dikenali oleh Server. Sehingga ketika domain diketikkan, DNS akan memberikan IP Adress dari nama domain tersebut.
5. Server akan memberikan response berupa data dengan format HTML (tampilan teks&paragraf), CSS(style), dan JavaScript (interaksi dan aksi), JSON (format yang digunakan dalam proses pengiriman dan penyimpanan data file), API (untuk mengintegrasikan dua bagian dari aplikasi atau dengan aplikasi yang berbeda secara bersamaan contohnya integrasi dengan payment gateway). 
6. Response tersebut akan dikirim lagi ke client berupa format html yang dikirim melalui IP Adress lagi.
    

## 9. Docker

Platform yang digunakan untuk building, running dan shipping applications. Docker dapat membuat semua aplkasi lain dapat berjalan, berfungsi dengan cara yang sama pada mesin lain.

**Container**
=> sebuah wadah yang dapat menjalankan banyak aplikasi secara terpisah tetapi lebih ringan karena tidak memerlukan sistem operasi. Semua container ini dijalankan pada satu mesin sebagai sistem operasi, dan host.

**Virtual Machine** 
=> sebuah software yang digunakan untuk menjalankan berbagai mesin sistem operasi. Virtual Machine memerlukan ruang image yang berbagi dengan lokal.


**Fitur-fitur docker**

a. Docker engine
Yang pertama ada docker engine. Ia digunakan untuk membuat image dan container.

b. Docker Hub
Selanjutnya adalah docker hub. Ia adalah registry yang berisikan kumpulan dari image-image. Dengan menggunakan docker hub ini kamu dapat mengumpulkan image. Hub ini berbeda dengan docker engine yang hanya membuat image.

c. Docker Compose
Docker compose ini adalah salah satu fitur unggulan yang berfungsi untuk menjalankan beberapa container atau biasa disebut multi-container sehingga dapat menghemat banyak waktu.

d. Docker for Mac
Untuk fitur yang satu ini, kamu pasti sudah tau dari namanya. Fitur ini memungkinkan pengguna docker untuk menjalankan container pada sistem operasi Mac.

e. Docker for Linux
Sama seperti fitur sebelumnya, fitur ini juga memungkinkan penggunanya untuk menjalankan container pada sistem operasi Linux.

f. Docker for Windows
Fitur terakhir dan sudah pasti fitur yang paling banyak digunakan dibandingkan dengan fitur-fitur lainnya yaitu docker for windows. Fitur ini memungkinkan penggunanya untuk menjalankan container pada sistem operasi windows.

    




