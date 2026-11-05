## Descripción
Can you figure out how this program works to get the flag? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 39303`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV.c). The binary can be downloaded [here](https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV).

Instance

Expires in 14:53

Hints

1

With Python, there are no binaries. With compiled languages like C, there is source code, and there are binaries. Binaries are created from source code, they are a conversion from the human-readable source code, to the highly efficient machine language, in this case: x86_64.

2

How can you find the address that `win` is at?
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV

Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV.c

Dark23-academy@webshell:~$ cat picker-IV.c

Dark23-academy@webshell:~$ file picker-IV
picker-IV: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=557545489438396d48510f7d86e8a9dcd71a1601, for GNU/Linux 3.2.0, not stripped
Dark23-academy@webshell:~$ checksec --file=picker-IV
[*] '/home/Dark23-academy/picker-IV'
    Arch:       amd64-64-little
    RELRO:      Partial RELRO
    Stack:      No canary found
    NX:         NX enabled
    PIE:        No PIE (0x400000)
    SHSTK:      Enabled
    IBT:        Enabled
    Stripped:   No
Dark23-academy@webshell:~$ objdump -D picker-IV | grep -A 15 "<win>"
00000000004012a1 <win>:
  4012a1:       f3 0f 1e fa             endbr64 
  4012a5:       55                      push   %rbp
  4012a6:       48 89 e5                mov    %rsp,%rbp
  4012a9:       48 83 ec 10             sub    $0x10,%rsp
  4012ad:       48 8d 05 71 0d 00 00    lea    0xd71(%rip),%rax        # 402025 <_IO_stdin_used+0x25>
  4012b4:       48 89 c7                mov    %rax,%rdi
  4012b7:       e8 34 fe ff ff          call   4010f0 <_init+0xf0>
  4012bc:       48 8d 05 6b 0d 00 00    lea    0xd6b(%rip),%rax        # 40202e <_IO_stdin_used+0x2e>
  4012c3:       48 89 c6                mov    %rax,%rsi
  4012c6:       48 8d 05 63 0d 00 00    lea    0xd63(%rip),%rax        # 402030 <_IO_stdin_used+0x30>
  4012cd:       48 89 c7                mov    %rax,%rdi
  4012d0:       e8 7b fe ff ff          call   401150 <_init+0x150>
  4012d5:       48 89 45 f0             mov    %rax,-0x10(%rbp)
  4012d9:       48 83 7d f0 00          cmpq   $0x0,-0x10(%rbp)
  4012de:       75 19                   jne    4012f9 <win+0x58>
Dark23-academy@webshell:~$ nm picker-IV | grep " win"
00000000004012a1 T win
Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 39303

Enter the address in hex to jump to, excluding '0x': 4012a1
You input 0x4012a1
You won!
academy{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_cccc13c1}

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV.c

https://challenge-files.cylabacademy.net/library/29304f03408a71abe2959b78d93cf0ad4b599550b0dfc4ee3211c8376731d344/picker-IV

