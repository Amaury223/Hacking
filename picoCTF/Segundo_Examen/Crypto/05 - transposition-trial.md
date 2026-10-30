## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://challenge-files.cylabacademy.net/library/c432352dd1b936c7ab4ceb162b63dafa1292c57462d832c59614d4db0de130be/message.txt).

Hints

1

Split the message up into blocks of 3 and see how the first block is scrambled
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/c432352dd1b936c7ab4ceb162b63dafa1292c57462d832c59614d4db0de130be/message.txt -o message.txt
Dark23-academy@webshell:~$ cat message.txt
heTfl g as icaaemd{7y4NRP051N5_16_35P3X51N3_V575D318}F

academy{7R4N5P051N6_15_3XP3N51V3_5571D3F8}
```
## Notas Adicionales
El bloque `"heT"` corresponde a la palabra `"The"`, así que la regla de reordenamiento es:

- Bloque scrambled: `(c0, c1, c2)` → Original: `(c2, c0, c1)`
## Referencias
https://challenge-files.cylabacademy.net/library/c432352dd1b936c7ab4ceb162b63dafa1292c57462d832c59614d4db0de130be/message.txt