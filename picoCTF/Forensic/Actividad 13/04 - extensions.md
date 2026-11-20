## Descripción
This is a really weird text file. Can you find the flag? Get the flag from [TXT](https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt).

Hints

1

How do operating systems know what kind of file it is? (It's not just the ending!)

2

Make sure to submit the flag as academy{XXXXX}
## Solución
```
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt
--2026-11-20 00:47:48--  https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.26, 18.238.132.49, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15696 (15K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt                    100%[===========================================>]  15.33K  --.-KB/s    in 0s      

2026-11-20 00:47:49 (465 MB/s) - ‘flag.txt’ saved [15696/15696]

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ file flag.txt
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ cp flag.txt flag.png
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ python3 -c "from PIL import Image; Image.open('flag.png').show()"

```
![[Pasted image 20261119234917.png]]
academy{now_you_know_about_extensions}
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt
