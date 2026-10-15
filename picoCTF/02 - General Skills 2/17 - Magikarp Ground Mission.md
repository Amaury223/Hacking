## Descripción
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Finding a cheatsheet for bash would be really helpful!
## Solución
```
Dark23-academy@webshell:~$ ssh ctf-player@xebec.cylabacademy.net -p 46222

ctf-player@academy-chall$ cat 1of3.flag.txt
academy{xxsh_

parte 2
ctf-player@academy-chall$ ls
2of3.flag.txt  challenge  home                      lib.usr-is-merged  mnt   root  srv  usr
bin            dev        instructions-to-3of3.txt  lib64              opt   run   sys  var
boot           etc        lib                       media              proc  sbin  tmp
ctf-player@academy-chall$ cat 2of3.flag.txt
0ut_0f_//4t3r_

parte 3
ctf-player@academy-chall$ cd ~
ctf-player@academy-chall$ ls
3of3.flag.txt  drop-in
ctf-player@academy-chall$ cat 3of3.flag.txt 
47c47679}
academy{xxsh_0ut_0f_//4t3r_47c47679}
```
## Notas Adicionales
accedemos al servidor con los datos que nos indican y dentro de este tendremos directorios y instrucciones siguiendo dichas instrucciones navegaremos por los directorios hasta encontrar todas las partes de la bandera.
## Referencias
[Webshell](https://webshell.cylabacademy.org/)