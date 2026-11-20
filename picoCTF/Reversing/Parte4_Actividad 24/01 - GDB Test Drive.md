
## Descripción
Can you get the flag? Download this [binary](https://challenge-files.cylabacademy.net/library/37a3037cc617e25371d3529e74304830bd22988c8c2f2b39e4355fc6781ac402/gdbme).

Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/37a3037cc617e25371d3529e74304830bd22988c8c2f2b39e4355fc6781ac402/gdbme
--2026-11-20 05:00:57--  https://challenge-files.cylabacademy.net/library/37a3037cc617e25371d3529e74304830bd22988c8c2f2b39e4355fc6781ac402/gdbme
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.18, 3.160.5.95, 3.160.5.64, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16304 (16K) [application/octet-stream]
Saving to: 'gdbme'

gdbme                                                      100%[========================================================================================================================================>]  15.92K  --.-KB/s    in 0.007s  

2026-11-20 05:00:57 (2.26 MB/s) - 'gdbme' saved [16304/16304]

Dark23-academy@webshell:~$ chmod +x gdbme
                                         
Dark23-academy@webshell:~$ gdb gdbme                                
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
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
```
![[Pasted image 20261119230330.png]]

academy{d3bugg3r_dr1v3_d28daa02}

## Notas Adicionales
## Referencias
https://learn.cylabacademy.org/assignments/13742/273#:~:text=Can%20you%20get,jump%20*(main%2B104)