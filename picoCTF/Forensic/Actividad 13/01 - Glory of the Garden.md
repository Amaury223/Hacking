
## Descripción
This file contains more than it seems. Get the flag from [garden.jpg](https://challenge-files.cylabacademy.net/library/d0194d28b6a765e7fd2fd2e62d44900e83912d4c98d622e40c02f7b58755051d/garden.jpg).

Hints

1

What is a hex editor?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/d0194d28b6a765e7fd2fd2e62d44900e83912d4c98d622e40c02f7b58755051d/garden.jpg
--2026-11-20 00:40:17--  https://challenge-files.cylabacademy.net/library/d0194d28b6a765e7fd2fd2e62d44900e83912d4c98d622e40c02f7b58755051d/garden.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.88, 18.238.132.26, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295191 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg                  100%[===========================================>]   2.19M  7.00MB/s    in 0.3s    

2026-11-20 00:40:18 (7.00 MB/s) - ‘garden.jpg’ saved [2295191/2295191]

                                                                                                                
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ strings garden.jpg | grep -i academy
Here is a flag: academy{more_than_m33ts_the_3y3caff56ca}
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 



```
## Notas Adicionales
## Referencias
 https://challenge-files.cylabacademy.net/library/d0194d28b6a765e7fd2fd2e62d44900e83912d4c98d622e40c02f7b58755051d/garden.jpg