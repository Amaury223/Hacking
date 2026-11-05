## Descripción
This service can provide you with a random number, but can it do anything else? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 12677`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/0981ed1dcae182f5d272ebe49164d0dc2c09f043e1843e26dbebaa80317d3245/picker-I.py).

Instance

Expires in 14:52
## Solución
```
Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 12677
Try entering "getRandomNumber" without the double quotes...
==> win
0x61 0x63 0x61 0x64 0x65 0x6d 0x79 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x63 0x35 0x35 0x66 0x62 0x65 0x66 0x35 0x7d

academy{4_d14m0nd_1n_7h3_r0ugh_c55fbef5}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/0981ed1dcae182f5d272ebe49164d0dc2c09f043e1843e26dbebaa80317d3245/picker-I.py