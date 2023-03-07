# Version Control System

## 1. Version Control System (VCS)

Sistem Kontrol Versi (VCS) adalah alat yang digunakan untuk mengelola perubahan yang dibuat pada kode perangkat lunak atau jenis konten digital lainnya. Alat ini melacak semua modifikasi, membuat pengembang untuk berkolaborasi dalam kode, kembali ke versi sebelumnya dan memelihara riwayat perubahan.

VCS terbagi dua:
    a. Centralized Version Control System (CVCS) : menyimpan semua kode di server pusat. Developer bekerja pada salinan kode lokal dan mendorong perubahan ke server pusat. Contohnya SVN (Git) dan CVS (sudah tidak digunakan karena memiliki kelemahan dalam konflik file)

    b. Distributed Version Control System (DVCS) : memungkinkan developers bekerja pada salinan kode lokal dan menyinkronkan perubahan mereka dengan yang lain. Setiap pengembang memiliki salinan basis code sendiri, sehingga lebih mudah untuk bekerja secara offline dan menggabungkan perubahan nantinya. Contoh: Git dan Mercurial. 

Manfaatnya yaitu:
    a. Collaboration: membuat developers bekerja pada codebase yang sama secara bersamaan dan menghindari konflik.
    b. History Tracking (pelacakan riwayat): dapat melacak semua perubahan yang dibuat pada code, dan bisa membuat developers kembali ke versi sebelumnya atau membandingkan perubahan antara versi yang berbeda.
    c. Backup dan disaster recovery (pemulihan bencana): dapat menyimpan semua versi code, yang berfungsi sebagai cadangan jika terjadi kehilangan data atau bencana.
    d. Eksperimen : developers dapat membuat beberapa cabang dan menguji fitur-fitur baru tanpa memengaruhi basis code utama.
    e. Traceability (Ketertelusuran/riwayat): menyediakan catatan yang jelas tentang siapa yang membuat perubahan, kapan perubahan itu dibuat, dan why.

contoh VCS:
    1. GitHub
    2. GitLab
    3. Perforce
    4. Beanstalk
    5. AWS Codecommit
    6. Apache Subversion
    7. Team Foundation Server
    8. Mercurial
    9. Bitbucket
    10. CVS (Concurrent Version Control)


## 2. Git

Git adalah sistem control versi yang paling populer, dan banyak diguankan dalam industri pengembangan software. Git memberikan fitur-fitur canggih termasuk, branching, merging, dan code review. Git juga menawarkan layanan hosting seperti GitHub, GitLab, dan Bitbucket yang menyidiakan alat tambahan untuk kolaborasi dan manajemen kode.

**Langkah-langkah kerja Git**
a. innitial repo : untuk mneginisialisasi sebuah repo di direktori lokal. Perintahnya: ```git init```
b. menambahkan file ke repository dengan perintah: ```git add```. perintah ini akan menambahkan file ke repo dan git mencatat setiap perubahannya.
c. commit: langkah dan tidakan untuk menyimpan perubahan yang telah dilakukan ke dalam rep dengan perintahnya: ```git commit```
d. brancing: developer bisa membuat cabang yang digunakan untuk membuat perubahan di fitur yang berbeda. ```git branch branchbaru``` untuk membuat branch baru dan ```git checkout namabranch``` untuk pindah ke branch baru.
e. merging: digunakan untuk menggabungkan perubahan di branch yang berbeda. Perintahnya: ```git merge```
f. sikronisasi jarak jauh dimana developers dapat berkolaborasi dengan developer lain pada proyek yang sama dan lokasi yang berjauhan. ```git push``` untuk mengupload perubahan lokal ke repo dan ```git pull``` untuk mendownload perubahan dari repo ke lokal.

**Perbedaan GitHub, GitLab, dan Bitbucket**
GitHub, GitLab, dan Bitbucket semuanya adalah platform hosting git repository, tetapi ada beberapa perbedaan penting antara ketiganya:

    GitHub:
    GitHub adalah salah satu platform hosting git repository paling populer. Didirikan pada tahun 2008, GitHub menyediakan platform untuk pengembang untuk menyimpan, mengelola, dan berbagi kode secara terbuka atau privat. GitHub banyak digunakan untuk menyimpan proyek open-source, tetapi juga dapat digunakan untuk menyimpan kode yang bersifat privasi. Selain itu, GitHub menyediakan fitur-fitur kolaborasi, seperti pull requests, code review, dan issue tracking.

    GitLab:
    GitLab adalah platform hosting git repository yang memungkinkan pengembang untuk memasang GitLab di server mereka sendiri atau menggunakan versi cloud yang disediakan oleh GitLab.com. GitLab memiliki fitur-fitur yang serupa dengan GitHub, seperti kolaborasi dan manajemen proyek, tetapi GitLab juga menawarkan fitur-fitur yang lebih luas, seperti Continuous Integration dan Continuous Deployment (CI/CD), dan fitur-fitur DevOps yang lain. Selain itu, GitLab juga menyediakan fitur-fitur untuk melacak metrik performa aplikasi dan infrastruktur.

    Bitbucket:
    Bitbucket adalah platform hosting git repository yang dimiliki oleh Atlassian, yang juga merupakan pemilik dari Jira dan Confluence. Bitbucket menyediakan fitur-fitur seperti kolaborasi dan manajemen proyek, tetapi juga menawarkan fitur-fitur unik, seperti integrasi yang erat dengan produk Atlassian lainnya, seperti Jira dan Confluence. Bitbucket juga memungkinkan pengembang untuk menyimpan kode secara gratis dalam repository privat untuk tim dengan hingga lima anggota.

Jadi, perbedaan utama antara ketiga platform hosting git repository adalah fitur dan fungsionalitas yang mereka tawarkan, serta siapa yang memilikinya. Selain itu, GitHub dan GitLab lebih populer di kalangan pengembang open-source dan perusahaan, sedangkan Bitbucket lebih terkait dengan ekosistem produk Atlassian.



## 3. Git Ignore

Git ignore adalah sebuah file yang digunakan untuk memberi tahu Git tentang file atau direktori mana yang tidak perlu dipantau atau ditambahkan ke dalam repositori Git. File-file ini seringkali adalah file sementara atau file konfigurasi lokal yang tidak perlu dicatat dalam repositori Git, seperti file log, file konfigurasi, atau file yang dihasilkan secara otomatis.
Git Ignore digunakan untuk mengabaikan file yang dipush ke repository github. 

cara menggunakan git ignore:
1. buat file ```.gitignore``` di direktori dari repositori
2. tambahkan daftar fike atau folder yang ingin diabaikan, satu perbaris.
3. Simpan file .gitignore dan tambahkan ke repositori dengan menggunakan command ```git add .gitignore```.
4. Lakukan commit untuk menambahkan file .gitignore ke repositori: ```git commit -m "Tambah file .gitignore"```.
5. Git akan mengabaikan semua file dan folder yang telah Anda tentukan dalam file .gitignore saat melakukan operasi git add, git commit, dan lainnya.

contoh penggunaan:
![gitignore](https://user-images.githubusercontent.com/82355684/223082266-b5bc2e58-6b93-4d36-ba2f-f248e665fa3e.png)


untuk mengetahui apa saja yang bisa dimasukkan ke file ```.gitignore``` bisa akses website ```github/github/gitignore``` atau bisa mengakses website ```gitignore.io``` untuk megenerate file apa saja yang dimasukkan ke file .gitignore



## 4. GitLab





