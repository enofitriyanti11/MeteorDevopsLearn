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

Contoh VCS:
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

1. innitial repo : untuk mneginisialisasi sebuah repo di direktori lokal. Perintahnya: ```git init```

2. menambahkan file ke repository dengan perintah: ```git add```. perintah ini akan menambahkan file ke repo dan git mencatat setiap perubahannya.

3. commit: langkah dan tidakan untuk menyimpan perubahan yang telah dilakukan ke dalam rep dengan perintahnya: ```git commit```

4. brancing: developer bisa membuat cabang yang digunakan untuk membuat perubahan di fitur yang berbeda. ```git branch branchbaru``` untuk membuat branch baru dan ```git checkout namabranch``` untuk pindah ke branch baru.

5. merging: digunakan untuk menggabungkan perubahan di branch yang berbeda. Perintahnya: ```git merge```

6. sikronisasi jarak jauh dimana developers dapat berkolaborasi dengan developer lain pada proyek yang sama dan lokasi yang berjauhan. ```git push``` untuk mengupload perubahan lokal ke repo dan ```git pull``` untuk mendownload perubahan dari repo ke lokal.

**Perbedaan GitHub, GitLab, dan Bitbucket**
GitHub, GitLab, dan Bitbucket semuanya adalah platform hosting git repository, tetapi ada beberapa perbedaan penting antara ketiganya:

1. GitHub:
GitHub adalah salah satu platform hosting git repository paling populer. Didirikan pada tahun 2008, GitHub menyediakan platform untuk pengembang untuk menyimpan, mengelola, dan berbagi kode secara terbuka atau privat. GitHub banyak digunakan untuk menyimpan proyek open-source, tetapi juga dapat digunakan untuk menyimpan kode yang bersifat privasi. Selain itu, GitHub menyediakan fitur-fitur kolaborasi, seperti pull requests, code review, dan issue tracking.

2. GitLab:
GitLab adalah platform hosting git repository yang memungkinkan pengembang untuk memasang GitLab di server mereka sendiri atau menggunakan versi cloud yang disediakan oleh GitLab.com. GitLab memiliki fitur-fitur yang serupa dengan GitHub, seperti kolaborasi dan manajemen proyek, tetapi GitLab juga menawarkan fitur-fitur yang lebih luas, seperti Continuous Integration dan Continuous Deployment (CI/CD), dan fitur-fitur DevOps yang lain. Selain itu, GitLab juga menyediakan fitur-fitur untuk melacak metrik performa aplikasi dan infrastruktur.

3. Bitbucket:
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


untuk mengetahui apa saja yang bisa dimasukkan ke file **```.gitignore```** bisa akses website ```github/github/gitignore``` atau bisa mengakses website **```gitignore.io```** untuk megenerate file apa saja yang dimasukkan ke file .gitignore



## 4. GitLab

GitLab adalah platform hosting git repository yang memungkinkan pengembang untuk memasang GitLab di server mereka sendiri atau menggunakan versi cloud yang disediakan oleh GitLab.com. GitLab memiliki fitur-fitur yang serupa dengan GitHub, seperti kolaborasi dan manajemen proyek, tetapi GitLab juga menawarkan fitur-fitur yang lebih luas, seperti Continuous Integration dan Continuous Deployment (CI/CD), dan fitur-fitur DevOps yang lain. Selain itu, GitLab juga menyediakan fitur-fitur untuk melacak metrik performa aplikasi dan infrastruktur.

![gitlab](https://user-images.githubusercontent.com/82355684/223319984-7ceec957-85c5-44d9-99fc-34757c0f131a.png)

Berikut adalah beberapa fitur utama GitLab dan fungsinya:

1. Repositori Git: GitLab menyediakan repositori Git untuk mengelola kode sumber proyek Anda. Anda dapat membuat cabang, melakukan commit, dan menggabungkan perubahan dengan mudah.

2. Issue tracking: GitLab menyediakan sistem pelacakan masalah untuk memungkinkan tim mengorganisir dan melacak masalah, bug, dan permintaan fitur. Fitur ini memungkinkan tim untuk menyelesaikan masalah lebih cepat dan dengan lebih efisien.

3. Continuous Integration (CI): GitLab menyediakan CI yang terintegrasi dengan repositori Anda. Fitur ini memungkinkan Anda untuk secara otomatis melakukan pengujian, pengujian lint, dan pelaksanaan tugas lainnya setiap kali ada perubahan pada kode sumber.

4. Continuous Delivery (CD): GitLab menyediakan CD yang terintegrasi dengan CI. Fitur ini memungkinkan Anda untuk secara otomatis membangun, menguji, dan merilis kode sumber Anda ke lingkungan produksi.

5. Version Control: GitLab menyediakan kontrol versi kode sumber Anda. Fitur ini memungkinkan Anda untuk memantau perubahan pada kode sumber Anda, dan memudahkan Anda untuk kembali ke versi sebelumnya jika ada masalah.

6. Wiki: GitLab menyediakan fitur Wiki untuk dokumentasi proyek Anda. Fitur ini memungkinkan tim untuk berkolaborasi dalam menulis dan mengedit dokumen proyek

7. Snippets: GitLab menyediakan fitur Snippets untuk berbagi kode sumber atau potongan kode dengan orang lain. Fitur ini memungkinkan Anda untuk berbagi kode sumber dengan mudah, tanpa harus memberikan akses ke repositori Anda.

8. Security: GitLab menyediakan fitur keamanan untuk membantu melindungi kode sumber Anda dari ancaman keamanan. Fitur ini mencakup pemeriksaan keamanan otomatis, deteksi kerentanan, dan laporan keamanan.

9. API: GitLab menyediakan API yang lengkap untuk mengakses data proyek Anda. Fitur ini memungkinkan Anda untuk mengintegrasikan GitLab dengan aplikasi atau layanan pihak ketiga.

10. Integrations: GitLab menyediakan integrasi dengan banyak layanan pihak ketiga seperti Jira, Slack, dan Trello. Fitur ini memungkinkan Anda untuk mengintegrasikan GitLab dengan alat yang sudah digunakan tim Anda.

#### How To use GitLab

1. Setup Git Global

* git config --global user.name "username"
* git config --global user.email "example@gmail.com"

2. Push direktrory lokal ke GitLab

* ```cd folder```
* ```git init --initial-branch=main```
* ```git remote add origin https://gitlab.com/enofitriyanti11/test2.git```
* ```git add .```
* ```git commit -m "Initial commit"```
* ```git push -u origin main```

3. membuat repository baru dan add file di lokal (clone)

* masuk ke folder atau desktop tempat ingin menyimpan code yang akan di clone
* ```git clone https://gitlab.com/enofitriyanti11/test2.git```
* ```cd test2```
* ```git switch -c main```
* ```touch README.md```
* ```git add README.md```
* ```git commit -m "add README"```
* ```git push -u origin main```

4. Push repositori yang usdah ada

* ```cd existing_repo```
* ```git remote rename origin old-origin```
* ```git remote add origin https://gitlab.com/enofitriyanti11/test2.git```
* ```git push -u origin --all```
* ```git push -u origin --tags```
