## Mengadopsi DevOps di PT Meteor Inovasi Digital
Sebuah perusahaan PT Meteor Inovasi Digital mengadopsi sebuah DevOps yang dipimpin oleh seorang leader yang bernama David. DevOps singkatan dari Development and Operations yang merupakan sebuah budaya atau culture baru untuk mengkoordinasikan antar tim yaitu tim development dengan tim operations dengan efektif dan efisien. 

Eno adalah seorang DevOps Engineer yang akan bergabung dalam tim DevOps dan ditugaskan untuk memberikan penjelasan mengenai adopsi DevOps di perusahaan PT Meteor Inovasi Digital.

#### 1.	Pengertian DevOps
 
DevOps adalah kombinasi dari culture, penerapan, dan peralatan yang meningkatkan kemampuan perusahaan atau organisasi untuk memberikan aplikasi dan layanan dalam kecepatan yang tinggi, mengembangkan dan meningkatkan produk dalam waktu yang lebih cepat dari organisasi yang menggunakan pengembangan software dan proses pengelolaan infrastruktur tradisional. Kecepatan ini membuat organisasi dapat melayani customer dengan lebih baik dan dapat berkomptensi dengan lebih efektif di pasaran.

Koordinasi yang diterapkan pada sebuah DevOps membutuhkan sebuah tools. Ada banyak tools yang bisa digunakan salah satunya adalah Source Code Management (SCM) yang biasa digunakan secara umum oleh tim development. Produk SCM yang paling terkenal adalah Git, ditemani oleh Source Code Repository (SCR) seperti GitHub, GitLab, Bitbucket, atau yang lainnya. Namun SCM saja tak cukup untuk mengomunikasikan antara tim development dengan tim operational. 
Untuk mengetahui permasalahan yang terjadi, biasanya tim operational akan dihubungkan ke Product Management Software seperti Jira. Melalui Produk Management Software, tim operation dapat mengetahui berbagai permasalahan yang terjadi pada sistem/aplikasi. Sehingga antara pihak development dengan operational akan saling terhubung satu sama lain.

#### 2.	Tujuan DevOps
DevOps bertujuan untuk mempercepat pengiriman produk software yang lebih baik dan berkualitas tinggi serta meningkatkan kolaborasi antara tim development dan tim operation, mulai dari perencanaan hingga aplikasi/fitur ter-deliver ke user. Semua itu harus dilakukan secara otomatis agar:
1.	Meningkatkan deployment frequency.
2.	Meningkatkan waktu pemasaran.
3.	Menurunkan tingkat kegagalan pada rilisan terbaru.
4.	Mempersingkat waktu perbaikan.
5.	Meningkatkan waktu pemulihan.

#### 3.	Manfaat DevOps
Manfaat DevOps yang dapat dirasakan oleh sebuah organisasi adalah sebagai berikut:

a.	Kecepatan

Bergerak dalam kecepatan tinggi sehingga perusahaan dapat melakukan inovasi untuk pelanggan dengan lebih cepat, beradaptasi dengan lebih baik di pasar yang berubah, dan menjadi lebih efisien dalam mendorong hasil bisnis yang berkualitas tinggi. Model DevOps memungkinkan tim pengembang dan pengoperasian perusahaan untuk mencapai hasil tersebut. Misalnya, layanan mikcro dan pengiriman berkelanjutan memungkinkan tim mendapatkan kepemilikan layanan dan kemudian meluncurkan pembaruannya dengan lebih cepat.

b.	Pengiriman yang cepat

Dapat meningkatkan frekuensi dan kecepatan peluncuran sehingga perusahaan dapat berinovasi dan meningkatkan produk dengan lebih cepat. Semakin cepat dapat meluncurkan fitur baru dan memperbaiki bug, semakin cepat pula dapat merespons kebutuhan pelanggan dan mendapatkan keuntungan yang kompetitif. Integrasi berkelanjutan dan pengiriman berkelanjutan merupakan praktik yang mengautomasi proses peluncuran software, dari pembuatan hingga penerapan.

c.	Keandalan

Keandalan yang terjadi seperti integrasi berkelanjutan dan pengiriman berkelanjutan untuk menguji bahwa tiap perubahan berfungsi aman. Praktik pemantauan dan pembuatan log dapat membantu mendapatkan informasi performa secara waktu-nyata.

d.	Skala

Automasi dan konsistensi membantu Anda mengelola sistem yang kompleks atau berubah secara efisien dan dengan risiko yang berkurang. Misalnya, infrastruktur sebagai kode membantu Anda mengelola pengembangan, pengujian, dan lingkungan produksi dengan cara yang dapat diulang dan lebih efisien.

e.	Kolaborasi yang dapat ditingkatkan

Tingginya tingkat kolaborasi antara tim development dan tim operation dapat mengurangi kesalahan dan meningkatkan kualitas produk.

f.	Keamanan

Keamanan yang ada pada DevOps dapat menentukan dan melacak kegiatan pada skala yang telah ditetapkan. Sehingga model DevOps dapat digunakan tanpa mengorbankan keamanan dengan menggunakan kebijakan kepatuhan yang terautomasi, control yang menyeluruh dan teknik manajemen konfigurasi.
 
#### 4.	Tahapan-Tahapan Siklus DevOps

![DevOps Siklus](https://th.bing.com/th/id/R.5b353a639c066e831116b59aecad17c7?rik=edB84M61H9UURw&riu=http%3a%2f%2fblogs.vmware.com%2fmanagement%2ffiles%2f2020%2f08%2fScreen-Shot-2020-08-27-at-1.31.56-PM.png&ehk=bWVZxwy8MP4%2bvbbymh3TKnDZaHvMgFXQ5pFaNl4DYnA%3d&risl=&pid=ImgRaw&r=0)

Siklus DevOps mencakup serangkaian kombinasi yang secarra umum dikenal sebagai “DevOps Lifecycle”. Tahapan-tahapannya yaitu sebagai berikut:

1)	Plan

Tahap ini melibatkan perencanaan proses pengembangan dan pengiriman software. Tim DevOps merencanakan apa yag harus dilakukan selama siklus ini dan membuat rencana untuk memenuhi tujuan bisnis. Tujuan utamanya adalah untuk memastikan bahwa semua anggota tim memahami tujuan, ruang lingkup, dan Batasan proyek atau produk.
Tools yang digunakan Trello, JIRA, Asana atau GitLab (untuk manajemen tugas dan proyek) dan Google Doc atau Microsoft Office (untuk kolaborasi dokumen).

2)	Code

Tahap ini melibatkan pengembangan dan penulisan code yang akan digunakan untuk membangun aplikasi. Tim DevOps biasanya menggunakan alat seperti Git atau SVN untuk mengelola kode sumber dan berkolaborasi pada kode yang sama. Kode harus dipelihara dengan baik agar mudah dikelola di kemudian hari.
Tools yang digunakan yaitu Git, GitHub, atau GitLab (untuk manajemen kode sumber) dan Visual Studio Code, IntelliJ IDEA atau Sublime Text (untuk text editor pengembangan code).

3)	Build

Tahap ini melibatkan membangun dan menguji kode yang telah ditulis dan dikembangkan. Tujuannya adalah untuk memastikan bahwa kode dapat dijalankan dan berfungsi sesuai dengan kebutuhan. Hal ini dapat dilakukan secara otomatis dengan menggunakan tools seperti Jenkins atau Travis CI, GitLab CI/CD, CircleCI

4)	Test

Tahap ini melibatkan pengujian kode atau aplikasi yang telah dibangun untuk memastikan bahwa ia berfungsi dengan baik dan sesuai dengan kebutuhan. Hal ini juga untuk memastikan kualitas produk yang dihasilkan serta pengujian keamanan dan kinerja. Tim DevOps biasanya melakukan pengujian otomatis dan manual untuk memastikan aplikasi berfungsi dengan baik.
Tool yang digunakan Selenium, Appium atau TestComplete (untuk pengujian fungsional), JMeter atau LoadRunner (untuk pengujian beban), dan SonarQube (untuk pengujian keamanan).

5)	Release

Tahap ini melibatkan persiapan untuk merilis aplikasi ke lingkungan produksi. Tim DevOps akan memeriksa bahwa aplikasi telah diuji dengan baik dan sudah siap untuk di release. Ini termasuk dokumentasi, pelaporan, dan persiapan infrastruktur.
Tools yang digunakan yaitu Jenkins, CircleCI, atau Gitlab CI/CD (untuk integrasi berkelanjutan) dan Docker atau Kubernetes (untuk manajemen kontainer).

6)	Deploy

Tahap ini melibatkan pengiriman aplikasi ke lingkungan produksi. Tim DevOps akan menggunakan alat seperti Ansible atau puppet untuk mengotomasi proses pengiriman produk.
Tools yang digunakan Ansible atau Chef (untuk manajemen konfigurasi), Terraform atau CloudFormation (untuk manajemen infrastruktur) dan AWS CodeDeploy atau Google Cloud Deployment Manager (untuk pengiriman code).

7)	Operate

Tahap ini melibatkan operasi aplikasi dalam lingkungan produksi. Tim DevOps memastikan bahwa aplikasi berjalan dengan baik dan dapat diakses oleh pengguna.
Tools yang digunakan yaitu Nagios, Zabbix atau Promotheus (untuk monitoring kinerja).

8)	Monitor

Tahap ini melibatkan pemantauan aplikasi dalam lingkungan produksi. Tim DevOps akan memantau performa aplikasi dengan melibatkan pengumpulan dan analisis data untuk memantau kinerja produk yang telah dirilis.
Tools yang digunakan ELK Stck atau Splunk (untuk analisis log).
Setiap alat yang dipilih tergantung pada kebutuhan tim development dan tim operation serta lingkungan teknis yang digunakan.

#### 5.	Cara kerja DevOps di Industri IT
Berikut ini adalah beberapa Langkah umum dalam cara kerja DevOps di industry IT:
1)	Integrasi berkelanjutan : tim development dan operation bekerja sama untuk melakukan integrasi berkelanjutan yaitu membangun, menguji, dan merilis software secara otomatis dan terus menerus.
2)	Pengujian otomatis : DevOps juga memanfaatkan pengujian otomatis untuk memastikan bahwa software yang dihasilkan sesuai dengan kebutuhan user.
3)	Provisioning otomatis : DevOps juga memanfaatkan provisioning otomatis untuk mempercepat pemasangan dan konfigurasi infrastruktur IT
4)	Monitoring dan analisis : DevOps melibatkan monitoring dan analisis infrastruktur IT dan aplikasi untuk memastikan bahwa mereka berjalan dengan baik dan memberikan pengalaman yang baik bagi pengguna.
5)	Kode yang dikelola dengan baik : DevOps juga mendorong tim pengembangan untuk mengelola kode dengan baik sehingga mudah untuk dikerjakan, dikembangkan dan dipelihara.
6)	Kolaborasi yang lebih baik : DevOps meningkatkan kolaborasi antara tim development dan operation, sehingga memungkinkan mereka untuk lebih cepat merespon perubahan pasar dan kebutuhan user. 
 
Dengan mengadopsi DevOps, perusahaan dapat meningkatkan efisiensi, mempercepat waktu rilis produk, meningkatkan kualitas produk dan meminimalkan risiko kesalahan ynag terjadi selama proses pengembangan dan operasi.



## Hal lain tentang DevOps

DevOps Lifecycle

1. CONTINUOUS DEVELOPMENT
Tools: Git, SVN, Mercurial, CV
Fase yang melibatkan plan dan code dari software. Menentukan visi proyek selama fase perencanaan dan pengembangan mulai dari mengembangkan kode untuk aplikasi.

2. CONTINUOUS INTEGRATION
Tools: Jenkins, TeamCity, Travis
tahap ini inti dari siklus hidup DevOps, karena ini adalah praktik yang dilakukan  oleh para pengembang yang melakukan perubahan pada kode sumber dengan lebih sering. Hal ini dilakukan setiap hari ataupun mingguan.

3. CONTINUOUS TESTING
Tools: Jenkins, Selenium TestNG, JUnit
fase ini dilakukan pengujian terhadap software yang dikembangkan secara terus menerus untuk mencari bug menggunakan alat pengujian otomatisasi.

4. CONTINUOUS DEPLOYMENT
Conﬁguration Management Tools – Chef, Puppet, Ansible
Containerization Tools – Docker, Vagrant
tahap ini mendeploy code pada server produksi. pastikan untuk mendeploy code dengan benar di semua server. Tools2 tersebut untuk membantu dalam mencapai Penerapan Berkelanjutan (Continuous Deployment/CD)


5. CONTINUOUS MONITORING
Tools: Splunk, ELK Stack, Nagios, New Relic
Tahap ini penting dalam lifecycle DevOps dalam memantau kinerja aplikasi. semua informasi penting tentang penggunaan software akan dicatat. Kemudian informasi tersebut digunakan untuk memerikasa fungsionalitas aplikasi yang tepat. DevOps dapat menyelesaikan kesalahan seperti low memory, server not reachable, dll.