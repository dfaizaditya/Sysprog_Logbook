## Pemrograman Sistem
Pemrograman sistem adalah pemrograman yang dapat berinteraksi langsung dengan hardware. Pemrograman sistem ini meliputi kernel module, device, syscall, sistem operasi, I/O, firmware dan hal-hal yang tidak terhubung langsung dengan user. pemrograman sistem dibuat dengan tujuan untuk menghubungkan antara sistem operasi dengan software atau dari sistem operasi ke hardware.

## Apa perbedaan dari System programing dan Application programming?
| System programming | Application programming |
| -------------------| --------------------- |
| Digunakan untuk menulis low level instructionyang dapat dimengerti oleh perangkat keras komputer | Digunakan untuk membangun perangkat lunak aplikasi yang mencakup perangkat lunak |
| System software yang dihasilkan adalah software yang digunakan untuk mengelola dan mengendalikan hardware komputer dan application software | Aplication software yang dihasilkan adalah software yang digunakan oleh pengguna akhir (end user) |
| Pemrograman dilakukan dengan menggunakan bahasa assembly yang berinteraksi dengan hardware | Pemrograman dilakukan dengan menggunakan high level language |

## Scripting dan Programming Language
Sebuah script pada Scripting language dapat langsung dijalankan dengan interpreter, berbeda dengan bahasa pemrograman yang sebelum dijalankan perlu terlebih dahulu di-compile menjadi bentuk executable. Mekanisme yang terjadi adalah suatu program (interpreter) melakukan parsing script dan mengeksekusinya baris per baris. Selain itu, Scripting language tidak mengenal adanya tipe terstruktur seperti pada bahasa pemrograman, sebagai gantinya pada scripting language dapat digunakan class dengan beberapa atribut.

## Kernel
Kernel adalah sistem berupa perangkat lunak yang mempunyai bertugas untuk menjadi penghubung antara berbagai macam program aplikasi yang diinstal (software) agar dapat terhubung dengan perangkat keras (hardware) komputer. Kernel berfungsi untuk menerjemahkan berbagai bahasa software agar dapat dimengerti oleh hardware. Setelahnya, hardware akan segera memprosesnya sesuai dengan perintah yang diberikan.

- Perbedaan kernel dan sistem operasi
  Pada dasarnya Kernel adalah suatu perangkat lunak yang menjadi bagian utama dari sebuah sistem operasi (OS) computer. Sementara, sistem operasi adalah sekumpulan program yang terhubung langsung ke perangkat keras komputer dan semua programnya berjalan di atasnya. Dapat disimpulkan bahwa Kernel merupakan level terendah dari sistem operasi.

- Perbedaan kernel mode dan user mode
  | Kernel mode | User mode |
  | :------------- | :------------------------------------------------------------------------- |
  |Mode dimana ketika kode dieksekusi, kode tersebut memiliki akses tak terbatas ke hardware| kode tidak langsung memiliki akses ke hardware atau memori |
  Dapat mengeksekusi instruksi CPU apa saja dan melakukan referensi ke alamat memori mana saja|Kode yang dijalankan mesti berhubungan dengan API sistem untuk berhubungan dengan hardware|

  Sebuah komputer memerlukan kedua mode tersebut untuk dapat berjalan dengan baik, Karena jika semua program dijalankan hanya dalam kernel mode, proses yang berjalan dalam sistem akan dapat saling menimpa memori satu sama lain. Maka diperlukan user mode untuk mengakses fitur yang ada dengan membuat panggilan ke API yang mendasarinya. Jika sebuah system tidak memiliki dual mode (user mode dan kernel mode) dapat timbul permasalahan diantaranya:
    - User program yang sedang berjalan dapat secara tidak sengaja menghapus sistem operasi dengan
    menimpanya dengan data pengguna.
    - Berbagai proses dapat menulis dalam sistem yang sama pada waktu yang sama, dengan hasil yang
    mengacaukan sistem.

## Program dan process

Sebuah program adalah sekumpulan instruksi yang dimaksudkan untuk mencapai suatu tujuan. Sementara proses (OS process) adalah program yang dimuat ke dalam memori dan dimulai. Memuat program ke dalam proses biasanya berarti mengalokasikan ruang alamat, dan sebaliknya membuat konteks untuk proses tersebut, memuat kode (instruksi yang dikodekan) dan data lain ke dalam ruang alamat itu, dan memberikan waktu cpu program dimulai dengan utama. Maka secara keseluruhan dapat dikatakan bahwa Ketika kita memulai sebuah program, maka kita juga memulai proses pada sistem operasi.

Jenis-jenis segment:pengeksekusian

1.  Text Segment:
    adalah salah satu bagian dari program dalam file objek atau memori, yang berisi instruksi yang dapat dieksekusi. Sebagai wilayah memori, Text Segment dapat ditempatkan di bawah heap atau stack untuk mencegah overflow heaps dan stack menimpanya.
2.  Initialized Data Segment:
adalah bagian dari virtual address space dalam sebuah program, yang berisi variabel global dan variabel statis yang diinisialisasi oleh programmer.
3.  Uninitialized Data Segment:
    Sebelum program mulai dijalankan data dalam segmen ini diinisialisasi menjadi aritmatika 0 oleh kernel. Uninitialized data dimulai pada akhir segmen data dan berisi semua variabel global dan variabel statis yang diinisialisasi ke nol atau tidak memiliki inisialisasi eksplisit dalam source code.
4.  Stack:
    Segmen ini digunakan untuk menyimpan semua variabel local, serta digunakan untuk meneruskan argumen ke sebuah fungsi bersamaan dengan return address dari instruksi yang akan dieksekusi setelah pemanggilan fungsi selesai.
5.  Heap:
    Pada segmen ini, umumnya dilakukan dynamic memory allocation. Saat beberapa memori lagi perlu dialokasikan menggunakan malloc dan fungsi calloc, heap akan naik. Area Heap dibagikan oleh semua pustaka bersama dan modul yang dimuat secara dinamis dalam suatu proses

## Tipe File pada Linux

Pada sistem Unix seperti GNU/Linux, tipe file dapat terdeteksi tanpa perlu melihat ekstensi file. Salah satu cara untuk mendeteksi tipe file adalah dengan menggunakan command `ls -ld <nama-file>`

Dengan menggunakan ls -ld, kita dapat melihat tipe file dari simbol pada karakter pertama dari bagian file permission. Terdapat tujuh tipe file pada Linux:

1. `-`: regular file
2. `d`: directory
3. `c`: character device file
4. `b`: block device file
5. `s`: local socket file
6. `p`: named pipe
7. `l`: symbolic link

## Absolute dan Relative Path

Absolute path dimulai dari root directory suatu sistem ( / ), sehingga jika diakses dari working directory
manapun akan mendapat hasil yang sama.
Relative path dimulai dari suatu working directory, atau direktori tempat user berada.

## FHS (Filesystem Hierarchy Standard)

Standarnya FHS (File Hierarchy Standard) digunakan untuk menyusun hierarchy tree pada GNU/Linux.
FHS adalah sebuah aturan standar penempatan lokasi berkas dan direktori pada suatu sistem operasi,
pengguna dan perangkat lunak mengetahui dimana letak suatu berkas atau direktori yang tersimpan di
suatu computer melalui aturan tersebut.

Lebih lengkapnya bisa lihat https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html

| 