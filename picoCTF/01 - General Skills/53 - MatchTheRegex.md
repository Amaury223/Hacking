## Descripción
How about trying to match a regular expression

The website is running [here](http://saturn.picoctf.net:61873/).
http://saturn.picoctf.net:61873/
## Solución
```
Dark23-academy@webshell:~$ curl -s "http://saturn.picoctf.net:61873/flag?input=picoCTF"
{"flag":"picoCTF{succ3ssfully_matchtheregex_9080e406}"}Dark23-academy@webshell:~$ 
```
## Notas Adicionales
- La validación estaba expuesta en el JavaScript de la página.
## Referencias
http://saturn.picoctf.net:61873/
