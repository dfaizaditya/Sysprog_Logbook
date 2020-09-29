## Apa yang saya pelajari selama minggu ke-2 Sysprog?
Kegiatan saya selama minggu ke-2 ini relaif sama dengan minngu sebelumnya, saya memulai dengan Menonton video materi yang tersedia di scele, dilanjutkan dengan mengerjakan pretest dan WS. Materi yang saya pelajari berfokus kepada "System Call" tentang bagaimana cara kerjanya hingga berbagai jenis dan kegunaanya.

## Apa itu system call?
System call adalah tata cara pemanggilan di program aplikasi untuk memperoleh layanan yang
disediakan oleh sistem operasi. System call berupa rutin sistem operasi untuk keperluan tertentu yang
spesifik.

## AKenapa kita membutuhkan system call?
System call dibutuhkan karena OS modern menerapkan isolasi antara proses user dan kernel. Isolasi
antar user dan kernel, menyebabkan user mode memerlukan cara untuk meminta izin terhadap
tindakan yang memiliki hak istimewa dari kernel. Contoh : membaca atau menulis disk fisik.
Oleh karena itu, disinilah peran systemcall sebagai penghubung user dan kernel yang berbentuk tata cara
pemanggilan di program aplikasi untuk memperoleh layanan yang disediakan oleh sistem operasi.

## Bagaimana system call bekerja ?
System call memiliki layanan terhadap aplikasi. Ketika kita melakukan system call pada user mode,
wrapper function akan berguna sebagai inisiator yang menginisiasi fungsi yang akan dipanggil,
mempersiapkan alokasi memori, serta register.

Setelahnya pada kernel mode, terdapat trap handler yang berfungsi untuk memerikan fungsi-fungsi
yang diminta oleh wrapper fungtion. Fungsi lainnya dari trap handler adalah mengubah user mode
menjadi kernel mode dan sebaliknya. Setelah pada trap handler diketahui fungsi yang akan
dipanggil,fungsi tersebut akan dieksekusi di register dan stack.

## System call error handling 
Kita dapat mengetahui apa error yang terjadi melalui liblary <errno.h> yang mendefinisikan variabel
integer errno dan memberikan feed back berupa symbolic name
| Serrno |  value Error |
| -------------------| --------------------- |
|1 | /* Operation not permitted */ |
|2 | /* No such file or directory */ |
|3 | /* No such process */ |
|4 | /* Interrupted system call */ |
|5 | /* I/O error */ |
|6 | /* No such device or address */ |
|7 | /* Argument list too long */ 
|8 | /* Exec format error */ |
|9 | /* Bad file number */ |
|10 | /* No child processes */ |
|11 | /* Try again */ |
|12 | /* Out of memory */ |
|13 | /* Permission denied */ |



