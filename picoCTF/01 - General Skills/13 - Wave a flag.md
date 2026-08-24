## Descripción
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

1

This program will only work in the webshell or another Linux computer.


## Solución
```
Dark23-academy@webshell:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=9e46ec8729d2f2aa8ffc4b1cdc058081bddcfe67, for GNU/Linux 3.2.0, with debug_info, not stripped
Dark23-academy@webshell:~$ chmod +X warm
Dark23-academy@webshell:~$ ./warm -h
-bash: ./warm: Permission denied
Dark23-academy@webshell:~$ ./warm   
-bash: ./warm: Permission denied
Dark23-academy@webshell:~$ chmod +x warm
Dark23-academy@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here:
picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}



```
## Notas Adicionales

chmod +x warm

./warm

## Referencias