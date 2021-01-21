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
##Perbedaan  & / &&?
& bersifat bitwise, sementara && adalah operator logika untuk “and”.

##lifespan of a variable inside a shell script
Artinya suatu variable pada shell memiliki waktu terbatas sebelum variable tersebut hilang. Batas waktunya adalah saat variable pada shell dibuat hingga shell ditutup.