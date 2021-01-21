## Apa yang saya pelajari selama minggu ke-11 Sysprog?
Minggu ini pembelajaran saya difokuskan pada background processes. Simobol "&" di belakang sebuah command (<command> &) menandakan subuah background process. Background process terhubung dengan suatu terminal, bila terminalnya dimatikan atau dikirim signal seperti SIGTERM atau SIGKILL, process tersebut juga akan dimatikan atau mendapatkan signal yang sama dengan controlling terminalnya.

## Nohup, SIGHUP, dan Simbol &
Nohup adalah command yang digunakan untuk menjalankan suatu script yang immune dengan signal

SIGHUP (Hangup). Nohup menutup standard input (STDIN) dari program tersebut, me-redirect output ke
file nohup.out, dan mem-blok process dari signal sighup.
Disown adalah command dalam bash yang digunakan untuk menghapus suatu process dari job list dari
terminal yang memanggilnya.

Simbol & adalah instruksi untuk mengeksekusi sebuah perintah (<command> &) agar dijalankan dalam
background process dan segera kembali ke commad line untuk perintah tambahan. Background process akan mati setelah sesi shell ditutup

## Sessions
Sessions adalah kumpulan dari beberapa process groups. Pada Session ID (SID) yang sama pada suatu
kumpulan process, kumpulan process tersebut memiliki 1 controlling terminal yang sama. Baik process
groups maupun sessions memiliki leader, dimana process yang pertama kali memulai adalah process
group leader atau session leader.

## Daemon process vs normal Process
Perbedaan antara daemon process dan normal Process adalah, Daemon process umunya
memiliki PID init atau PID sytemd. Daemon Juga biasnya tidak memiliki controlling terminal,
sedangkan normal process memiliki controlling terminal.


