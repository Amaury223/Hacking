## Descripción
Can you find the flag in this disk image? Wrap what you find in the academy{} flag format. Download the disk image [here](https://challenge-files.cylabacademy.net/library/0b369ed5974a5e777ca3bc323bd39d75a6f27762a449d16cd2a0ffc08b2a6aa8/timeline-1-partition4.img.gz).

Hints

1

Create a Sleuthkit MAC timeline!

2

Look at recent timestamps

3

Pay close attention to timestamps near an anti-forensic action

4

Filter only new files by grepping for `macb`
## Solución
```
──(kali㉿kali)-[~]
└─$ wget "https://challenge-files.cylabacademy.net/library/0b369ed5974a5e777ca3bc323bd39d75a6f27762a449d16cd2a0ffc08b2a6aa8/timeline-1-partition4.img.gz"


┌──(kali㉿kali)-[~]
└─$ gunzip timeline-1-partition4.img.gz
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ fls -r -m / timeline-1-partition4.img > body.txt
mactime -b body.txt > timeline.txt
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ grep 'macb' timeline.txt | tail -n 30
                               23 macb l/lrwxrwxrwx 0        0        33003    /etc/ssl/certs/a3418fda.0 -> ca-cert-GTS_Root_R4.pem
                               34 macb l/lrwxrwxrwx 0        0        33004    /etc/ssl/certs/93bc0acc.0 -> ca-cert-AffirmTrust_Networking.pem
                               23 macb l/lrwxrwxrwx 0        0        33005    /etc/ssl/certs/626dceaf.0 -> ca-cert-GTS_Root_R2.pem
                               34 macb l/lrwxrwxrwx 0        0        33006    /etc/ssl/certs/e35234b1.0 -> ca-cert-Certum_Trusted_Root_CA.pem
                               49 macb l/lrwxrwxrwx 0        0        33007    /etc/ssl/certs/f30dd6ad.0 -> ca-cert-USERTrust_ECC_Certification_Authority.pem
                               53 macb l/lrwxrwxrwx 0        0        33008    /etc/ssl/certs/02265526.0 -> ca-cert-Entrust_Root_Certification_Authority_-_G2.pem
                               30 macb l/lrwxrwxrwx 0        0        33009    /etc/ssl/certs/c01eb047.0 -> ca-cert-UCA_Global_G2_Root.pem
                               32 macb l/lrwxrwxrwx 0        0        33010    /etc/ssl/certs/6a9bdba3.0 -> ca-cert-SecureSign_Root_CA15.pem
                               31 macb l/lrwxrwxrwx 0        0        33011    /etc/ssl/certs/5f15c80c.0 -> ca-cert-TWCA_Global_Root_CA.pem
                               45 macb l/lrwxrwxrwx 0        0        33012    /etc/ssl/certs/1e08bfd1.0 -> ca-cert-IdenTrust_Public_Sector_Root_CA_1.pem
                               28 macb l/lrwxrwxrwx 0        0        33013    /etc/ssl/certs/8d86cdd1.0 -> ca-cert-certSIGN_ROOT_CA.pem
                               52 macb l/lrwxrwxrwx 0        0        33014    /etc/ssl/certs/f249de83.0 -> ca-cert-Trustwave_Global_Certification_Authority.pem
                               24 macb l/lrwxrwxrwx 0        0        33015    /etc/ssl/certs/0b9bc432.0 -> ca-cert-ISRG_Root_X2.pem
                              111 macb r/rrw-r--r-- 0        0        33016    /etc/apk/world
                            28160 macb r/rrw-r--r-- 0        0        4934     /lib/apk/db/scripts.tar
                           411949 macb r/rrw-r--r-- 0        0        4945     /lib/apk/db/installed
                               11 macb l/lrwxrwxrwx 0        0        64809    /usr/bin/crontab -> /bin/bbsuid
                               11 macb l/lrwxrwxrwx 0        0        64872    /usr/bin/passwd -> /bin/bbsuid
                               11 macb l/lrwxrwxrwx 0        0        64916    /usr/bin/traceroute -> /bin/bbsuid
                               11 macb l/lrwxrwxrwx 0        0        64917    /usr/bin/traceroute6 -> /bin/bbsuid
                               11 macb l/lrwxrwxrwx 0        0        64936    /usr/bin/vlock -> /bin/bbsuid
                                3 macb l/lrwxrwxrwx 0        0        64945    /usr/bin/ex -> vim
                                3 macb l/lrwxrwxrwx 0        0        67318    /usr/bin/rview -> vim
                                3 macb l/lrwxrwxrwx 0        0        67319    /usr/bin/rvim -> vim
                                3 macb l/lrwxrwxrwx 0        0        67320    /usr/bin/view -> vim
                               49 macb r/rrw-r--r-- 0        0        32716    /etc/chat
                             1024 macb d/drwxr-xr-x 0        0        33017    /lib/rc/cache
                                8 macb r/rrw-r--r-- 0        0        33020    /lib/rc/cache/softlevel
                                9 macb r/rrw------- 0        0        4943     /root/.ash_history
                               32 macb r/rr-------- 0        0        65278    /var/lib/seedrng/seed.credit
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ icat timeline-1-partition4.img 32716
NTczNDE3aDEzcl83aDRuXzdoM18xNDU3XzU4NTI3YmIyMjIK
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ icat timeline-1-partition4.img 32716 | base64 -d
573417h13r_7h4n_7h3_1457_58527bb222

academy{573417h13r_7h4n_7h3_1457_58527bb222}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/0b369ed5974a5e777ca3bc323bd39d75a6f27762a449d16cd2a0ffc08b2a6aa8/timeline-1-partition4.img.gz