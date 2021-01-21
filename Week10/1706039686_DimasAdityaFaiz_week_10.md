## Apa yang saya pelajari selama minggu ke-10 Sysprog?
Pembelajaran saya minggu ini difokuskan pada topik mengenai Signals. Signals adalah cara komunikasi antar process, dan signals pada umumnya bisa di-trap atau di-handle, block, maupun di ignore oleh proses yang menerimanya. Cara mengirimkan signal adalah dengan command kill, yang memiliki beberapa options yang bisa dipakai, misalnya kill -9 -1 untuk mematikan semua process yang bisa dimatikan dan kill -s TERM (PID) untuk mengirimkan SIGTERM ke process yang memiliki PID tersebut, dimana SIGTERM sendiri adalah sinyal untuk clean shutdown.

## Signal
Signal SIGTERM, SIGKILL dan SIGINT tergolong shutdown signals. SIGTERM, semerupakan signal yang dikirimkan ke suatu process ketika process tersebut mau di-terminate secara aman atau biasa. Di lain sisi, SIGINT merupakan signal yang dikirimkan ketika ada interrupt di tengah-tengah process, biasanya oleh user (misalnya saat ada process berjalan lalu kita interrupt dengan Ctrl+C atau keyboard interrupt), dan dapat dianggap sebagai ungraceful shutdown. Terakhir, SIGKILL merupakan semacam last resort dari shutdown signals. SIGKILL tidak dapat di-trap sama sekali oleh process manapun, karena digunakan sebagai last resort shutdown signal. 

## Signal List:

```
Signal      Standard   Action   Comment
────────────────────────────────────────────────────────────────────────
SIGABRT      P1990      Core    Abort signal from abort(3)
SIGALRM      P1990      Term    Timer signal from alarm(2)
SIGBUS       P2001      Core    Bus error (bad memory access)
SIGCHLD      P1990      Ign     Child stopped or terminated
SIGCLD         -        Ign     A synonym for SIGCHLD
SIGCONT      P1990      Cont    Continue if stopped
SIGEMT         -        Term    Emulator trap
SIGFPE       P1990      Core    Floating-point exception
SIGHUP       P1990      Term    Hangup detected on controlling terminal
or death of controlling process
SIGILL       P1990      Core    Illegal Instruction
SIGINFO        -                A synonym for SIGPWR
SIGINT       P1990      Term    Interrupt from keyboard
SIGIO          -        Term    I/O now possible (4.2BSD)
SIGIOT         -        Core    IOT trap. A synonym for SIGABRT
SIGKILL      P1990      Term    Kill signal
SIGLOST        -        Term    File lock lost (unused)
SIGPIPE      P1990      Term    Broken pipe: write to pipe with no
readers; see pipe(7)
SIGPOLL      P2001      Term    Pollable event (Sys V);
synonym for SIGIO
SIGPROF      P2001      Term    Profiling timer expired
SIGPWR         -        Term    Power failure (System V)
SIGQUIT      P1990      Core    Quit from keyboard
SIGSEGV      P1990      Core    Invalid memory reference
SIGSTKFLT      -        Term    Stack fault on coprocessor (unused)
SIGSTOP      P1990      Stop    Stop process
SIGTSTP      P1990      Stop    Stop typed at terminal
SIGSYS       P2001      Core    Bad system call (SVr4);
see also seccomp(2)
SIGTERM      P1990      Term    Termination signal
SIGTRAP      P2001      Core    Trace/breakpoint trap
SIGTTIN      P1990      Stop    Terminal input for background process
SIGTTOU      P1990      Stop    Terminal output for background process
SIGUNUSED      -        Core    Synonymous with SIGSYS
SIGURG       P2001      Ign     Urgent condition on socket (4.2BSD)
SIGUSR1      P1990      Term    User-defined signal 1
SIGUSR2      P1990      Term    User-defined signal 2
SIGVTALRM    P2001      Term    Virtual alarm clock (4.2BSD)
SIGXCPU      P2001      Core    CPU time limit exceeded (4.2BSD);
see setrlimit(2)
SIGXFSZ      P2001      Core    File size limit exceeded (4.2BSD);
see setrlimit(2)

SIGWINCH       -        Ign     Window resize signal (4.3BSD, Sun)

