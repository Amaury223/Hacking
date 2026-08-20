## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?
## Solución

```
Dark23-academy@webshell:~$  nc fickle-tempest.picoctf.net 59312 > noc     
Dark23-academy@webshell:~$ cat noc | grep pico
Dark23-academy@webshell:~$ cat noc
Dark23-academy@webshell:~$ nc fickle-tempest.picoctf.net 51460 > noc  
cat noc
Dark23-academy@webshell:~$ cat noc | grep pico
picoCTF{digital_plumb3r_d3246b6B}
```
## Notas Adicionales
## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)