## Apa yang saya pelajari selama minggu ke-3 Sysprog?
Kegiatan saya selama minggu ke-3 ini relaif sama dengan minngu sebelumnya, saya memulai dengan Menonton video materi yang tersedia di scele, dilanjutkan dengan mengerjakan pretest dan WS. Materi yang saya pelajari berfokus kepada "System Call" tentang bagaimana cara kerjanya hingga berbagai jenis dan kegunaanya.

## File decriptor
File decrptor adalah abstraksi yang digunakan dalam interface antara user mode dan kernel
mode untuk mengidentifikasi sumber file / socket (mengakses file). File descriptor dilambangkan
dalam sebuah integer. Untuk setiap proses, terdapat 3 file descriptor yang tersedia dalam unix.
Standard input (stdin). Bernilai 0.
Standard output (stdout). Bernilai 1.
Standar error (stderr). Bernilai 2

Suatu file descriptor dibuat ketika suatu process memanggil system call open untuk membuka suatu file (file description), file descriptor tersebut
berfungsi sebagai pointer terhadap file yang dibuka.

## Inode table
Inode table adalah struktur data pada traditional Unix-style file system seperti ext3 dan ext4
yang bertugas untuk menyimpan properti dan alokasi block dari sebuah file atau director, Tabel
ini berisi daftar semua file di sistem filei. Lalu, dalam tabel inode, terdapat inode yang berisi
informasi (metadata) tentang file dan direktori.. Masing-masing inode dalam tabel inode
memiliki nomor unik (unik untuk sistem file itu), disebut sebagai inode number.

## stat() and lstat() command
stat () menerima argumen berupa path name ke sebuah file dan mengembalikan atribut atau
informasi tentang file target yang terkait dengan path tersebut. Sementaral, lstat () identik
dengan stat (), namun jika nama path adalah symbolic link, maka ia mengembalikan informasi
terkait symbolic link itu sendiri, bukan file yang dirujuknya.

## Systemcall close()
Close() berfungsi untuk menutup deskriptor file, sehingga tidak lagi merujuk ke file apa pun dan dapat
digunakan kembali. Jika melakukan open() tanpa close() maka descriptor akan tetap merujuk pada file 
sebelumnya yang di open(). Hasilnya adalah kita mungkin akan kehabisan deskriptor file yang tersedia
untuk melayani sebuah proses, dan upaya untuk membuka lebih banyak file pada akhirnya akan gagal.
Selain itu, tidak melakukan close() juga dapat mencegah proses lain membuka atau menghapus file yang
telah di open(), karena secara default, file di open() dalam mode berbagi eksklusif yang mencegah
proses lain untuk membukanya.

## File hole
File hole adalah ruang di antara akhir file sebelumnya dan byte yang baru ditulis. Terdapat alokasi byte
dalam hole, dan membaca dari hole mengembalikan buffer byte yang berisi 0.
