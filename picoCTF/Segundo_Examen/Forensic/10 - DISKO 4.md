## Descripción
Can you find the flag in this disk image? This time I deleted the file! Let see you get it now! Download the disk image [here](https://challenge-files.cylabacademy.net/library/d11cb680ea12a21fc0d5fdb414a325b8c800bd2fbf4b546df09d428f0e84b4c4/disko-4.dd.gz).

Hints

1

How would you look for deleted files?
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget "https://challenge-files.cylabacademy.net/library/d11cb680ea12a21fc0d5fdb414a325b8c800bd2fbf4b546df09d428f0e84b4c4/disko-4.dd.gz"
gunzip disko-4.dd.gz


┌──(kali㉿kali)-[~]
└─$ fls -r -d disko-4.dd
r/r * 522629:   log/messages
r/r * 532021:   log/dont-delete.gz
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ icat disko-4.dd 532021 > dont-delete.gz
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ file dont-delete.gz
dont-delete.gz: gzip compressed data, was "dont-delete", last modified: Wed Sep 23 06:57:18 2026, from Unix, original size modulo 2^32 55
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ gunzip dont-delete.gz
cat dont-delete
Here is your flag
academy{d3l_d0n7_h1d3_w3ll_187a1210}

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/d11cb680ea12a21fc0d5fdb414a325b8c800bd2fbf4b546df09d428f0e84b4c4/disko-4.dd.gz