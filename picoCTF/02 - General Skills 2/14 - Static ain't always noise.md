## Descripción
Can you look at the data in this binary? The bash script might help!
## Solución
```
wget https://challenge-files.picoctf.net/c_wily_courier/b94bae11002f8fd650a028c91c0e5427b3122a0049c43a3ed483299b8d61665b/static

wget https://challenge-files.picoctf.net/c_wily_courier/b94bae11002f8fd650a028c91c0e5427b3122a0049c43a3ed483299b8d61665b/ltdis.sh

Dark23-academy@webshell:~$ cat ltdis.sh | more

Dark23-academy@webshell:~$ chmod +x ltdis.sh

Dark23-academy@webshell:~$ ./ltdis.sh

Dark23-academy@webshell:~$ ./ltdis.sh static

Dark23-academy@webshell:~$ strings static.ltdis.strings.txt | grep pico
picoCTF{d15a5m_t34s3r_20335e41}
```
## Notas Adicionales
bajar 2 archivos, lugo de darle permisos de ejecucion a el primer archivo ltdis.sh y ejecutarlo con el parametro del segundo archivo este crea un archivo txt donde esta la bandera... otra opccion es hacer un strings y grep a el archivo static

```
strings static | grep pico
```
## Referencias
[Webshell](https://webshell.cylabacademy.org/)