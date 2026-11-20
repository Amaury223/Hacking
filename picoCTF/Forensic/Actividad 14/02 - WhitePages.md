## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.cylabacademy.net/library/f500839660c0dddc9df4e5410dcd8e4d5a27f7ebae825caad4690a9d1646a451/whitepages.txt) is all blank!

Hints

1

There is data encoded somewhere... there might be an online decoder.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/f500839660c0dddc9df4e5410dcd8e4d5a27f7ebae825caad4690a9d1646a451/whitepages.txt
--2026-11-20 01:15:59--  https://challenge-files.cylabacademy.net/library/f500839660c0dddc9df4e5410dcd8e4d5a27f7ebae825caad4690a9d1646a451/whitepages.txt
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.88, 18.238.132.26, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2760 (2.7K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt              100%[===========================================>]   2.70K  --.-KB/s    in 0.002s  

2026-11-20 01:15:59 (1.60 MB/s) - ‘whitepages.txt’ saved [2760/2760]

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ file whitepages.txt
whitepages.txt: Unicode text, UTF-8 text, with very long lines (1296), with no line terminators
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wc -c whitepages.txt
2760 whitepages.txt
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ cat -A whitepages.txt | head -20
M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^C    M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C    M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C    M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C    M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C    M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^C    M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C    M-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C    M-bM-^@M-^C   M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C     M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C     M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^C     M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C     M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C     M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C   M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C     M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C   M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^CM-bM-^@M-^C  M-bM-^@M-^C     M-bM-^@M-^C M-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^CM-bM-^@M-^C M-bM-^@M-^C M-bM-^@M-^C                                                                                                                
┌──(kali㉿kali)-[~]
└─$ xxd whitepages.txt | head -20
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 8320 20e2 8083 e280 83e2   ......  .......
00000020: 8083 e280 8320 e280 8320 20e2 8083 e280  ..... ...  .....
00000030: 83e2 8083 2020 e280 8320 20e2 8083 e280  ....  ...  .....
00000040: 83e2 8083 e280 8320 e280 8320 20e2 8083  ....... ...  ...
00000050: e280 8320 e280 83e2 8083 e280 8320 20e2  ... .........  .
00000060: 8083 e280 8320 e280 8320 e280 8320 20e2  ..... ... ...  .
00000070: 8083 2020 e280 8320 e280 8320 2020 20e2  ..  ... ...    .
00000080: 8083 e280 8320 e280 83e2 8083 e280 83e2  ..... ..........
00000090: 8083 20e2 8083 20e2 8083 e280 83e2 8083  .. ... .........
000000a0: e280 83e2 8083 20e2 8083 20e2 8083 e280  ...... ... .....
000000b0: 8320 e280 8320 e280 83e2 8083 2020 e280  . ... ......  ..
000000c0: 8320 e280 83e2 8083 e280 8320 e280 8320  . ......... ... 
000000d0: e280 8320 e280 83e2 8083 e280 8320 e280  ... ......... ..
000000e0: 8320 e280 83e2 8083 20e2 8083 e280 83e2  . ...... .......
000000f0: 8083 e280 83e2 8083 e280 8320 e280 8320  ........... ... 
00000100: e280 83e2 8083 e280 83e2 8083 e280 8320  ............... 
00000110: e280 8320 e280 8320 e280 8320 e280 8320  ... ... ... ... 
00000120: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000130: e280 8320 e280 83e2 8083 2020 e280 83e2  ... ......  ....
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ nano resolver.py
with open("whitepages.txt", "r", encoding="utf-8") as f:
    contenido = f.read()

bits = ""

for caracter in contenido:
    if caracter == "\u2003":
        bits += "0"
    elif caracter == " ":
        bits += "1"

resultado = ""

for i in range(0, len(bits) - 7, 8):
    byte = bits[i:i+8]
    resultado += chr(int(byte, 2))

print("[+] Bits encontrados:", len(bits))
print("[+] Mensaje decodificado:")
print(resultado)
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ python3 resolver.py
[+] Bits encontrados: 1296
[+] Mensaje decodificado:

academy

SEE PUBLIC RECORDS & BACKGROUND REPORT
5000 Forbes Ave, Pittsburgh, PA 15213
academy{not_all_spaces_are_created_equal_5fe1602ea91f835386aa3eae672cf4e3}

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/f500839660c0dddc9df4e5410dcd8e4d5a27f7ebae825caad4690a9d1646a451/whitepages.txt