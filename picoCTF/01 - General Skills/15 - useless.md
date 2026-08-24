## Descripción
There's an interesting script in the user's home directory
The work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.

`Hostname: saturn.picoctf.net Port: 58716 Username: picoplayer Password: password`
## Solución
```
ssh picoplayer@saturn.picoctf.net -p 58716

Password: password

picoplayer@challenge:~$ ls
useless

picoplayer@challenge:~$ cat useless

picoplayer@challenge:~$ man useless
picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_5657}


```
## Notas Adicionales
Leer el manual
man - te proporciona un manual de ayuda completo de un comando o ejecutable  

## Referencias