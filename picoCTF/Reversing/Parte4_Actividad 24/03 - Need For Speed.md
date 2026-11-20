
## Descripción
1. The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://challenge-files.cylabacademy.net/library/1f19c0ef7346746915a41e424dc8399c20e09955cc88570026df8750f77905bf/need-for-speed)

Hints

1

What is the final key?
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/1f19c0ef7346746915a41e424dc8399c20e09955cc88570026df8750f77905bf/need-for-speed
--2026-11-20 05:14:35--  https://challenge-files.cylabacademy.net/library/1f19c0ef7346746915a41e424dc8399c20e09955cc88570026df8750f77905bf/need-for-speed
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.95, 3.160.5.64, 3.160.5.18, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16544 (16K) [application/octet-stream]
Saving to: 'need-for-speed'

need-for-speed                                             100%[========================================================================================================================================>]  16.16K  --.-KB/s    in 0s      

2026-11-20 05:14:36 (89.0 MB/s) - 'need-for-speed' saved [16544/16544]

Dark23-academy@webshell:~$ chmod +x need-for-speed
Dark23-academy@webshell:~$ ./need-for-speed
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
Dark23-academy@webshell:~$ gdb ./need-for-speed
GNU gdb (Ubuntu 12.1-0ubuntu1~22.04.2) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from ./need-for-speed...
(No debugging symbols found in ./need-for-speed)
(gdb) handle SIGALRM ignore
Signal        Stop      Print   Pass to program Description
SIGALRM       No        No      No              Alarm clock
(gdb) run
Starting program: /home/Dark23-academy/need-for-speed 
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================

Creating key...
Finished
Printing flag:

academy{Good job keeping bus #251feedf speeding along!}

[Inferior 1 (process 347) exited normally]
(gdb) 
```
## Notas Adicionales
## Referencias
https://www.youtube.com/watch?v=8piqd2BWeGI

https://challenge-files.cylabacademy.net/library/1f19c0ef7346746915a41e424dc8399c20e09955cc88570026df8750f77905bf/need-for-speed