## Descripción
Why use p and q when I can use more? Connect with `nc chatelaine.cylabacademy.net 30730`.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ mkdir cd b00tl3gRSA3   
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ cd ~/b00tl3gRSA3                 
                                                                                                                
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ sudo apt install -y pari-gp
[sudo] password for kali: 
Installing:                     
  pari-gp

Installing dependencies:
  pari-doc  pari-elldata  pari-galdata  pari-seadata

Suggested packages:
  pari-gp2c  pari-galpol  pari-nflistdata

Summary:
  Upgrading: 0, Installing: 5, Removing: 0, Not Upgrading: 0
  Download size: 89.2 MB
  Space needed: 103 MB / 61.3 GB available

┌──(kali㉿kali)-[~]
└─$ cd ~/b00tl3gRSA3 
                                                                                                                
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ nc -w 5 chatelaine.cylabacademy.net 30730 | tee datos.txt
c: 1740768294477180787749124296896058145412363760843675083028902839715406390678953109328682813705338927495822611482517284755406060065566238468076352732639815571537393729398939951160646066361108161062533280950913925838609311385005956473840938334561682868727247795965837276412781922886593191586925301671015780564659363438072074628221893097426201708
n: 7822439580607581884991256558033090087152098563150374501150302712389389302403533662045806935959941045276140508672788758065089299468775483552526069375638584915953208595834775291531794815085320495976366825263095913749665759239405257320399874017200612904135174234150320585868099247344593896752172681946314929411422945704586081024690567470939272373
e: 65537
                                                                                                                
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ nano resolver_b00tl3gRSA3.py
                                                                                                                
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ python3 resolver_b00tl3gRSA3.py datos.txt
[+] Factorizando n...
zsh: killed     python3 resolver_b00tl3gRSA3.py datos.txt
                                                                                                                
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ n=$(awk -F': ' '$1=="n"{print $2}' datos.txt)
curl -sG --data-urlencode "query=$n" https://factordb.com/api
echo
{"id":1100000011908496650,"status":"C","factors":[["7822439580607581884991256558033090087152098563150374501150302712389389302403533662045806935959941045276140508672788758065089299468775483552526069375638584915953208595834775291531794815085320495976366825263095913749665759239405257320399874017200612904135174234150320585868099247344593896752172681946314929411422945704586081024690567470939272373",1]]}
                                                                                                                
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ nano resolver_b00tl3gRSA3.py 
                                                                                                                
┌──(kali㉿kali)-[~/b00tl3gRSA3]
└─$ python3 resolver_b00tl3gRSA3.py datos.txt 


academy{too_many_fact0rs_9487747}
```
## Notas Adicionales
## Referencias
