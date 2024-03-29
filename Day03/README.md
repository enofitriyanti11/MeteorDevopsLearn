# LINUX

## 1. Install WSL

WSL (Windows Subsystem Linux) adalah  fitur sistem operasi Windows yang memungkinkan untuk menjalankan OS GNU/Linux, aplikasi terminal bahkan aplikasi GUI langsung dari desktop Windows user.

Berikut hasil install WSL di Windows

![install wsl](https://user-images.githubusercontent.com/82355684/221509865-500eba5d-a340-4e40-9843-0d1bed8e81b1.png)


## 2. Text Editor di Linux

1. Pico

Pico merupakan teks editor berbasis teks yang mudah digunakan. Teks editor ini menjadi favorit para pengguna baru. Pico awalnya hadir bersama Pine email client. Pico ditulis dalam bahasa pemrograman C.

![pico](https://user-images.githubusercontent.com/82355684/221513391-14273a86-2900-405c-b7a3-c8d7df64054f.png)

2. Nano

Nano merupakan teks editor kloning dari Pico dengan beberapa peningkatan. Nano tersedia untuk Linux dan DOS.

![nano](https://user-images.githubusercontent.com/82355684/221520758-c32f4bc4-7ee0-414a-bf2f-1aa5ccc1921d.png)

**Command**

```Ctrl + x``` => menyimpan file kemudian ubah nama file sesuai kebutuhan.

3. Emacs

![Emacs](https://user-images.githubusercontent.com/82355684/221521070-127d4abc-ff22-4dd3-8d5c-a3afbb8e0763.png)



4. Vim

Vim (Vi Impropment) merupakan kloning dari Vi dengan peningkatan dan tambahan. Fitur Vim lebih lengkap dan ter-update dibandingkan Vi.

Vim adalah salah salah satu teks editor favorit para programmer, karena ringan dan efisien.

![Vim](https://user-images.githubusercontent.com/82355684/221521339-3b608809-37e4-427c-b6a3-2998590f9dbe.png)


5. Vi

Vi sebenarnya teks editor untuk Unix. Vi dibuat oleh Bill Joy dengan bahasa pemrograman C. Vi dirilis pertama kali pada tahun 1976 (sekitar 40 tahun yang lalu).

![Vi](https://user-images.githubusercontent.com/82355684/221521967-f3e417d5-5c33-41db-ba42-08b0db3460bc.png)

6. Jed

JED merupakan teks editor berbasis teks lintas platform. Website resmi: http://www.jedsoft.org/jed/. JED memiliki beberapa fitur andalan, diantaranya:

* Syntax highlighting
* Code Folding
* Menu Drop-down
* Emulator editor Emacs, EDT, WordStar, Borland, Brief
* Bisa membaca Texinfo (GNU info)
* Edit Tex

![Jed](https://user-images.githubusercontent.com/82355684/221521655-bcf8297e-d863-44e3-9b6c-40e0ec53dce1.png)


## 3. Text Manipulation di Linux

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

digunakan untuk menampilkan konten dalam format yang terurut. perintah ```sort``` untuk secara ascending, dan perintah ```sort -r``` secara descending.

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



## 4. Perintah di Linux

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

# Command Linux

![image](https://user-images.githubusercontent.com/82355684/230802941-e10c6ab6-3b44-47b5-aa3f-a656152502d8.png)

![image](https://user-images.githubusercontent.com/82355684/230802976-89debc1a-f9b8-4417-8c1a-c0f18bc71d9d.png)

![image](https://user-images.githubusercontent.com/82355684/230802993-5cfa262e-b010-4b79-8838-0a7ec82e2874.png)

![image](https://user-images.githubusercontent.com/82355684/230803009-def7d5d1-c0b7-4aeb-920d-7fca6f85c0c3.png)

![image](https://user-images.githubusercontent.com/82355684/230803026-c9e8296c-8564-478c-9b6e-f26cc026d47f.png)

![image](https://user-images.githubusercontent.com/82355684/230803060-7fba76da-1d36-4f4d-a68c-4534da4484b7.png)

![image](https://user-images.githubusercontent.com/82355684/230803070-b352f012-d4a7-4fb7-8c54-3688f3316f6c.png)

![image](https://user-images.githubusercontent.com/82355684/230803104-75d5acb7-0139-48c0-9f41-627c9553eaa6.png)

![image](https://user-images.githubusercontent.com/82355684/230803118-00cf4e00-0c7a-4354-9c4f-da704bfed666.png)

![image](https://user-images.githubusercontent.com/82355684/230803122-57521694-a22b-47fa-98e3-2ccb7d670d13.png)
