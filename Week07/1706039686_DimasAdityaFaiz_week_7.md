## Apa yang saya pelajari selama minggu ke-7 Sysprog?
Minggu ini pembelajaran saya difokuskan pada topik scripting, terutama dengan BASH (Bourne Again SHell). Saat kita
menjalankan sebuah bash script, kita bisa mem-pass beberapa parameter atau command-line arguments, yang mirip
seperti bagaimana kita menjalankan sebuah compiled C file.

## Shell Scripting
Shell script adalah sebuah program yang dituliskan untuk dijalankan oleh Unix/Linux shell. Penulisan program sama logikanya dengan bahasa pemrograman biasa, akan tetapi shell scripting dapat menyertakan command-command dan fitur-fitur yang terdapat di dalam Unix/Linux shell.

## Shell variables
Variabel shell adalah variabel khusus yang ditetapkan oleh shell dan dibutuhkan oleh shell agar dapat berfungsi dengan benar. Beberapa variabel ini adalah environtment variabel sedangkan yang lainnya adalah local variabel.

## Perbedaan $* and $@?
$* menyimpan secara lengkap “string” dari seluruh positional argumen pada suatu program mencakup dari argumen pertama atau $1 sampai argumen ke N, sementara $@ melakukan hal yang sama namun pada “array of string”.

## Perbedaan  & / &&?
& bersifat bitwise, sementara && adalah operator logika untuk “and”.

## lifespan of a variable inside a shell script
Artinya suatu variable pada shell memiliki waktu terbatas sebelum variable tersebut hilang. Batas waktunya adalah saat variable pada shell dibuat hingga shell ditutup.

## five types of shellas well as the advantages and disadvantages!
1. Bourne Shell (sh)
adalah shell penafsir baris perintah, untuk sistem operasi Unix.
keuntungan :
- shell dasar yang sederhana, prompt hanya mencangkup $ .
- berbagai unix system mudah untuk diadaptasikan ke server lain.
Kerugian :
- Kurang compatible dengan command lain
- Tidak dilengkapi dengan fasilitas auto-compilation sehingga penulisan script harus
dilakukan secara manual

2. Bourne-Again Shell (bash)
adalah shell yang menjadi standar shell di sebagian besar sistem Linux, Bash (Bourne
again shell) merupakan pengganti shell untuk Bourne shell, dimana bash adalah superset
dari sh.
Keuntungan :
- Menulis skrip shell dengan lebih cepat dari pada scripting language lain
- Dokumentasi cukup lengkap
- Dapat melakukan Interactive debugging
Kerugian :
- Biasanya kecepatan eksekusinya lambat.
- Ada banyak kekurangan dalam hal desain dan implementasi
- Sangat sedikit memberikan fasilitas struktur data

3. C Shell (csh)
Keuntungan :
- Memiliki sejarah perintah yang pernah diberikan
- File extension and formatting lebih mudah dimengerti
- Memiliki lingkungan interaktif
Kekurangan :
- Syntax sulit dimengerti
- Tidak memiliki command editor

4. Korn Shell (KSH)
Keuntungan :
- KSH memudahkan correction dari typing error
- Terdapat fitur reuse command dari history
Kerugian :
- Syntax cukup kompleks
- Format ekstensi file sulit dipelajari dan dimengerti

5. Z Shell (ZSH)
Keuntungan :
- Merupakan shell yang powerfull, karena dapat melakukan lebih banyak hal dibanding
shell lainnya.
- Mendukung command line histories
- Definisi perintah yang disediakan jauh lebih mudah dimengerti.
- Perintah yang digunakan sangat dinamis / multine.
Kerugian :
- Tidak semua linux system mensupport ZSH
- Sulit melakukan migrasi dibandingkan BASH atau SH.
- Membutuhkan banyak konfiguras