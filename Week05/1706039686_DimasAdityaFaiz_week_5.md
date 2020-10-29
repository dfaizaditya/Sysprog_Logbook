## Apa yang saya pelajari selama minggu ke-5 Sysprog?
Kegiatan saya selama minggu ke-3 ini relaif sama dengan minngu sebelumnya, saya memulai dengan Menonton video materi yang tersedia di scele, dilanjutkan dengan mengerjakan pretest dan WS. Materi yang saya pelajari berfokus kepada "Memory" dan "process" tentang jenis dan cara kerjanya hingga berbagai jenis dan kegunaanya.

## The memory structure of a process 
Stack segment : adalah area memori yang digunakan proses untuk menyimpan variabel lokal dari fungsi
dan informasi lain yang disimpan setiap kali suatu fungsi dipanggil.
Heap segment : adalah area memoi yang digunakan untuk alokasi memori dinamis. Segmen ini
digunakan secara bersama pleh semua proses yang berjalan di system.
BBS segment : adalah area memori yang menyimpan semua variabel global yang tidak diinisialisasi dalam
program.
Data segment : adalah area memori yang menyimpan semua variabel global yang diinisialisasi
Text segment : adalah area memori yang berisi instruksi mesin yang dijalankan CPU.

## Reference Locality
Reference locality adalah suatu kecenderungan prosesor mengakses set dari lokasi memory yang sama untuk beberapa saat.
1. Temporal locality
Sebuah address yang diakses oleh sebuah eksekusi program, maka ada kemungkinan address tersebut
akan diakses kembali.
2. Spatial locality
Sebuah address yang diakses oleh sebuah eksekusi program, maka ada kemungkinan address terdekat
dari address tersebut juga akan diakses. 

## Memory Allocation
1. brk () 
brk() adalah system call yang menetapkan akhir segmen data ke nilai yang ditentukan oleh addr, jika nilai tersebut wajar dan
sistem memiliki cukup memori, serta proses tidak melebihi ukuran data maksimumnya.
2. sbrk () 
Sbrk() adalah system call yang menambah ruang data program dengan menambah byte. Memanggil sbrk () dengan increment =
0 dapat digunakan untuk menemukan lokasi saat ini dari jeda program.

Baik Sbrk dan brk berfungsi untuk mengatur address dari program break yang adalah akihir dari suatu
program. Perbedaanya ada pada cara pengaturan address, brk mengatur address berdasarkan
parameter input, sementara sbrk mengatur address dengan menambah space segment berdasarkan
input parameter.

## Memory Leak
Memory Leak adalah suatu keadaan dimana memori telah teralokasi untuk sebuah program, namun
tidak dapat dibebaskan kembali untuk dikembalikan ke sistem operasi.
Beberapa tindakan yang dapat menghasilkan memory leak antara lain:
1. Dealokasi memory tidak dilakukan pada akhir program.
2. Memory yang dialokasikan melebihi batas heap.
3. Ada thread yang mati tanpa melakukan cleanup.

## System call malloc()
Saat melakukan system call malloc(), malloc() akan membaca parameter berapa byte memori
yang harus dialokasikan untuk eksekusi program. Lalu, dilakukan pemanggilan sbrk() untuk
mencari sebuah pointer ke heap yang kosong pada memori. Setelah itu, pada free list yang berisi
blok memori bebas akan dipilih sebuah block memory yang bebas. Terakhir, jika ditemukan ada
block yang tersedia, maka pointer dari block tersebut akan di-return kepada program. Sedangkan
jika tidak tidak ada block yang tersedia, maka malloc() akan mengembalikan null value.

Malloc () tidak menggunakan sbrk () untuk menyesuaikan jeda program pada setiap panggilan.
Karena malloc hanya akan melakukan pemanggilan saat heap tidak cukup, malloc akan
mengimplementasikan system call sbrk() untuk menambah address program break. Lalu, malloc
akan mengembalikan pointer ke allocate memory apabila berhasil dan NULL apabila gagal.

## System call setjmp() dan longjmp()
1. setjmp(), adalah sebuah fungsi yang akan menyimpan address saat ini ke sebuah buffer. Fungsi
tersebut me-return value sebuah integer, dimana saat pertama kali dipanggil fungsi akan mereturn nilai 0 dan untuk return value selanjutnya adalah set value dari fungsi longjmp().
2. longjmp(), adalah sebuah fungsi yang akan melakukan 'jump' ke address env sesuai pemanggilan
setjmp(env). Fungsi ini memiliki parameter integer val, dimana nilai parameter tersebut akan
menggantikan nilai return value dari setjmp(env) saat fungsi longjmp dipanggil

