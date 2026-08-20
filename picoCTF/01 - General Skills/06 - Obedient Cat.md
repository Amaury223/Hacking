
## Descripción
This file has a flag in plain sight (aka "in-the-clear").

Pistas
Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.

2
To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget and a link to the flag. The link can be copied from the details section.

3
$ man cat
## Solución
```
`Dark23-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/4acf636990e4540d6fc36684b1256e625c0617d7cb01727e12e3f9606d89fe45/flag`
`--2026-08-19 16:55:29--  https://challenge-files.picoctf.net/c_wily_courier/4acf636990e4540d6fc36684b1256e625c0617d7cb01727e12e3f9606d89fe45/flag`
`Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.40, 3.160.5.64, 3.160.5.95, ...`
`Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.40|:443... connected.`
`HTTP request sent, awaiting response... 200 OK`
`Length: 34 [application/octet-stream]`
`Saving to: 'flag'`

`flag                                                       100%[========================================================================================================================================>]      34  --.-KB/s    in 0s`      

`2026-08-19 16:55:29 (21.7 MB/s) - 'flag' saved [34/34]`

`Dark23-academy@webshell:~$ cat flag`
`picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}`
```
## Notas Adicionales
## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)