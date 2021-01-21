## Apa yang saya pelajari selama minggu ke-3 Sysprog?
Kegiatan saya selama minggu ke-3 ini relaif sama dengan minngu sebelumnya, saya memulai dengan Menonton video materi yang tersedia di scele, dilanjutkan dengan mengerjakan pretest dan WS. Materi yang saya pelajari berfokus kepada "System Call" tentang bagaimana cara kerjanya hingga berbagai jenis dan kegunaanya.

## System call fork()
Sistem operasi UNIX mempunyai system call fork yang berfungsi untuk membuat proses baru. Proses yang memanggil system call fork ini akan dibagi jadi dua, proses induk dan proses turunan yang identik. 
Saat system call fork() dieksekusi, maka akan dibuat proses baru. Proses asal disebut sebagai proses
parent dan proses baru disebut sebagai proses child.
Proses child merupakan duplikat dari proses parent. Proses parent dan child melanjutkan eksekusi dari
titik dimana system call fork() menghasilkan eksekusi pada program utama. Proses dijalankan secara
konkuren, dan niilai yang dihasilkan oleh fork() akan disimpan dalam variable bertipe pid_t.


## Teknik Copy-on-write pada fork()
Copy-on-write adalah teknik yang diterapkan system call fork() dalam mengelola resource pada sebuah
proses. Ketika melakukan fork() pada suatu proses, child process akan diberikan copy dari resource yang
sama dari parent. Maka, ponter resource pada child dan parent merujuk pada resource yang sama
sampai salah satu dari process tersebut melakukan modifikasi isi pada resource, 

## Perbedaan Orphan process, Daemon processg, dan Zombie process|
Orphan : adalah proses yang kehilangan intended parent process yang dimilikinya. Pada proses ini,
parent process sudah menyelesaikan eksekusi dan terminate, sedangkan proses tersebut belum
melakukan terminate. Process akan tidak memiliki parent yang kemudian akan diadopsi oleh init process
Daemon : adalah proses yang berjalan di belakang layar dan memiliki init process sebagai parent
Zombie : adalah proses yang sudah mati/selesai, namun masih terdaftar pada tabel proses.
| Orphan process | Daemon processg | Zombie process|
| -------------------| --------------------- | --------------------- |
| proses yang sedang berjalan | proses yang sedang berjalan | proses yang sudah selesai |
| proses yang terputus hubungannya dengan parentnya | proses yang berjalan pada background dan memiliki init sebagai parent process | proses yang sudah selesai berjalan namun entry proses pada tabel proses masih tersisa |
 
## Zombie process : pencegahan dan cara mengatasinya
Zombie process adalah sebuah keadaan dimana suatu process sudah selesai dijalankan, namun masih
terdaftar pada table entry process karena belum dibersihkan secara baik dan benar. Umumnya zombie
disebabkan oleh child process yang sudah selesai dieksekusi namun parent process nya tidak melakukan
system call wait() sehingga menyebabkan tidak diakhirinya child process. 
Pencegahan dilakukan dengan mengeksekusi system call wait() pada setiap parent proses yang dibuat
ketika mendapat signal SIGCHLD dari child. Setelah wait() dieksekusi dan parent membaca status “mati”
dari child process, maka zombie status dari child process akan dihapus secara otomatis dari memory.
Jika pencegahan tidak berhasil, berikut adalah cara menangani zombie process :

1. Kita dapat melakukan kill() pada parent process, sehingga children dari parent process yang dibunuh
akan diadopsi oleh init dan init akan memanggil wait() kepada children
2. Kita dapat mengirim SIGCHLD kepada parent process agar melakukan syscall wait() pada children
3. Kita dapat melakukan system reboot| 