# Pratikum 11,12,13,14: PHP Framework (Codeigniter)
# Praktikum Lainnya Ada Pada Link Tugas Github
# PERSIAPAN
1. Gunakan text editor, saya menggunakan sublime.

2. Menggunakan Xampp
Diperlukan konfigurasi pada webserver, mengaktifkan ekstensi PHP intl. buka xampp di apache klik konfigurasi dan buka php.ini

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/xampp.jpg)

3. Membuat folder baru lab11_php_ci
Untuk mengaktifkan extension nya hapus tanda titik kome (;)

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/ext.jpg)

langkah selanjutnya unduh codeigniter, extrack filenya dan masukan ke dalam xampp/htdock

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/codel.jpg)

Bukalah localhost:8080 di browser.

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/8080.jpg)

Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt dan gunakan "php spark"

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/spark.jpg)

Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/whoops.JPG)

Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment variable CI_ENVIRINMENT menjadi development.

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/.env.jpg)

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/notepad.jpg)

Dan ini hasil errornya

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss11/eror.jpg)

# PENJELASAN TENTANG DIREKTORI CODEIGNETER
. github folder ini kita butuhkan untuk konfigurasi repo github, seperti konfigurasi untuk build dengan github action;
. app folder ini akan berisi kode dari aplikasi yang kita kembangkan;
. public folder ini berisi file yang bisa diakses oleh publik, seperti file index.php, robots.txt, favicon.ico, ads.txt, dll;
. tests folder ini berisi kode untuk melakukan testing dengna PHPunit;
. vendor folder ini berisi library yang dibutuhkan oleh aplikasi, isinya juga termasuk kode core dari system CI.
. writable folder ini berisi file yang ditulis oleh aplikasi. Nantinya, kita bisa pakai untuk menyimpan file yang di-upload, logs, session, dll.

Sedangkan file-file yang berada pada root direktori CI sebagai berikut.
. env adalah file yang berisi variabel environment yang dibutuhkan oleh aplikasi.
. gitignore adalah file yang berisi daftar nama file dan folder yang akan diabaikan oleh Git.
. build adalah script untuk mengubah versi codeigniter yang digunakan. Ada versi release (stabil) dan development (labil).
. composer.json adalah file JSON yang berisi informasi tentang proyek dan daftar library yang dibutuhkannya. File ini digunakan oleh Composer sebagai acuan.
. composer.lock adalah file yang berisi informasi versi dari libraray yang digunakan aplikasi.
. license.txt adalah file yang berisi penjelasan tentang lisensi Codeigniter;
. phpunit.xml.dist adalah file XML yang berisi konfigurasi untuk PHPunit.
. README.md adalah file keterangan tentang codebase CI. Ini biasanya akan dibutuhkan pada repo github atau gitlab.
. spark adalah program atau script yang berfungsi untuk menjalankan server, generate kode, dll.

Folder app, dimana folder tersebut adalah area kerja kita untuk membuat aplikasi. Dan folder public untuk menyimpan aset web seperti css, gambar, javascript, dll.
Pada folder app, dimana folder tersebut adalah area kerja kita untuk membuat aplikasi. Dan folder public untuk menyimpan aset web seperti css, gambar, javascript, dll.

# Memahami Konsep MVC
Codeigniter menggunakan konsep MVC. MVC meripakan singkatan dari Model-View-Controller. MVC merupakan konsep arsitektur yang umum digunakan dalam pengembangan aplikasi. Konsep MVC adalah memisahkan kode program berdasarkan logic proses, data, dan tampilan. Untuk logic proses diletakkan pada direktori Contoller, Objek data diletakkan pada direktori Model, dan desain tampilan diletakkan pada direktori View.

Codeigniter menggunakan konsep pemrograman berorientasi objek dalam mengimplementasikan konsep MVC.

Model
merupakan kode program yang berisi pemodelan data. Data dapat berupa database ataupun sumber lainnya.

View
merupakan kode program yang berisi bagian yang menangani terkait tampilan user interface sebuah aplikasi. didalam aplikasi web biasanya pasti akan berhubungan dengan html dan css.

Controller
merupakaan kode program yang berkaitan dengan logic proses yang menghubungkan antara view dan model. Controller berfungsi untuk menerima request dan data dari user kemudian diproses dengan menghubungkan bagian model dan view.

Routing dan Controller
Routing merupakan proses yang mengatur arah atau rute dari request untuk menentukan fungsi/bagian mana yang akan memproses request tersebut. Pada framework CI4, routing bertujuan untuk menentukan Controller mana yang harus merespon sebuah request. Controller adalah class atau script yang bertanggung jawab merespon sebuah request.

Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk meudian oleh router tesebut diarahkan ke Controller.
Router terletak pada file app/config/Routes.php
Membuat Route

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/ss11/route.jpg)

Memeriksa penambahan route di CLI dengan perintah "php spark routes"

![imag](https://github.com/fdlhrauf/Lab11Web/blob/main/ss11/routes.jpg)

Mengakses file about.php akan terlihat seperti berikut , karena tidak ada isinya.



Membuat controller dengan nama file page.php



Hasil yang di tampilkan sebagai berikut



Membuat method baru controoller page



Ini hasilnya.



Membuat view about.php app/view/about.php



Mengubah method about pada class Controller Page menjadi seperti ini



Ini hasilnya.



Membuat CSS pada pratikum ke 4



Membuat file Header dengan Folder template/view/header.php



Membuat file footernya juga



Dan kemudian mengubah file about.php pada app/view/about.php



Ini hasilnya



Pertanyaan dan Tugas
Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

Membuat file contact.php, faqs.php, tos.php seperti berikut.



membuat sourch code seperti berikut pada file app/Controllers



Ini hasilnya







Pratikum ke 12
Membuat table dan database.



Konfigurasi dengan database server dengan mensetting file app/config/database.php



Membuat model untuk mengakses artikel.



Membuat controller artikel.php



Membuat folder baru di dalam app/views dan membuat file baru dengan nama index.php.



Hasil Outputnya



Menambahkan data ke dalam tabel artikel.



Hasil outputnya.



Membuat tampilan detail artikel dengan menambahkan fungsi baru pada controller/Artikel.php



Membuat view detail.php di direktori app/views/artikel/detail.php



Membuat routing untuk artikel detail di app/config/Routes.php



Membuat menu untuk proses CRUD dan membuat method baru pada controllers/Artikel.php



Membuat views/artikel/admin_index.php untuk tampilan admin.



Menambahkan routing pada menu admin. berada di file app/Config/Routes.



Hasil outputnya.



CRUD Menambah data pada artikel, di direktori app/Controllers/Artikel.php



Membuat form tambah di direktori app/views/artikel/form_add.php



Hasil Outputnya.



Menambahkan fungsi method untuk ubah data artikel di direktori app/Controller/Artikel.php



Membuat form ubah yang sudah terisi data sebelumnya.



Hasil outputnya.



Membuat penghapusan data, dengan menambahkan fungsi/method pada direktori app/Controllers/Artikel.php




# Pratikum 13
Membuat table user

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/001.jpg)

Membuat model user app/Models/UserModel.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/002.jpg)

Membuat controller user app/Controllers User.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/003.jpg)

Membuat view login app/views/login.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/004.jpg)

Membuat database seeder app/Database/Seeds/UserSeeder.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/005.jpg)

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/006.jpg)

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/007.jpg)

Output Loginnya

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/008.jpg)

Menambahkan Auth Filter app/Filters/Auth.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/009.jpg)

Tambahkan config auth app/Config/Filters.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/010.jpg)

Ubah routes app/Config/Routes.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/011.jpg)

Percobaan output login h.ttp://localhost:8080/admin/artikel dan akan muncul halaman login

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/012.jpg)

Fungsi logout

![imag](https://github.com/fdlhrauf/Labss11/blob/main/ss13/013.jpg)

# PRAKTIKUM 14

Membuat pagination Controller/Artikel. admin_index

![imag](https://github.com/fdlhrauf/Labss11/blob/main/01.jpg)

Menambahkan kode views/artikel/admin_index

![imag](https://github.com/fdlhrauf/Labss11/blob/main/02.jpg)

output page

![imag](https://github.com/fdlhrauf/Labss11/blob/main/03.jpg)

Membuat pencaharian Controller/Artikel. admin_index

![imag](https://github.com/fdlhrauf/Labss11/blob/main/04.jpg)

Menambahkan form pencaharian views/artikel/admin_index.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/05.jpg)

Mengubah link pagenya

![imag](https://github.com/fdlhrauf/Labss11/blob/main/06.jpg)

Hasil output

![imag](https://github.com/fdlhrauf/Labss11/blob/main/07.jpg)

Menambahkan fungsi unggah gambar Controller/Artikel. method add

![imag](https://github.com/fdlhrauf/Labss11/blob/main/08.jpg)

Menambahkan field input views/artikel/form_add.php

![imag](https://github.com/fdlhrauf/Labss11/blob/main/09.jpg)

Menambahkan encrypt type

![imag](https://github.com/fdlhrauf/Labss11/blob/main/10.jpg)

Hasil output

![imag](https://github.com/fdlhrauf/Labss11/blob/main/11.jpg)
