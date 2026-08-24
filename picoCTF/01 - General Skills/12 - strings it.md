## Descripción
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/6577d3f1500aebcd300787bd5d96216b30aed379c811f5e83e888f897da4a3d5/strings) without running it?
## Solución
```
wget https://challenge-files.picoctf.net/c_fickle_tempest/6577d3f1500aebcd300787bd5d96216b30aed379c811f5e83e888f897da4a3d5/strings

Dark23-academy@webshell:~$ ls
README.txt  file  flag  hola  noc  strings

Dark23-academy@webshell:~$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=ac2be8917250478c4e3cdd8b41a945cfdd4a755f, for GNU/Linux 3.2.0, not stripped

Dark23-academy@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_d6306c19}

```
## Notas Adicionales
Cat no funciona con Archivos binarios
Strings - Muestra las cadenas (Caracteres imprimibles) en un archivo binario (no texto)
## Referencias
