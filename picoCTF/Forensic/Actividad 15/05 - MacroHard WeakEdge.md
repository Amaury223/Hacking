## Descripción
've hidden a flag in this file. Can you find it? [Forensics_is_fun.pptm](https://challenge-files.cylabacademy.net/library/ef35dfe613527d28fe872d94179b53bc1a0497ddecf57e51d160c910be3a8e8a/Forensics_is_fun.pptm)
## Solución
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wget "https://challenge-files.cylabacademy.net/library/ef35dfe613527d28fe872d94179b53bc1a0497ddecf57e51d160c910be3a8e8a/Forensics_is_fun.pptm"
--2026-11-20 03:17:29--  https://challenge-files.cylabacademy.net/library/ef35dfe613527d28fe872d94179b53bc1a0497ddecf57e51d160c910be3a8e8a/Forensics_is_fun.pptm
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.49, 18.238.132.88, 18.238.132.26, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100145 (98K) [application/octet-stream]
Saving to: ‘Forensics_is_fun.pptm’

Forensics_is_fun.pptm       100%[===========================================>]  97.80K  --.-KB/s    in 0.1s    

2026-11-20 03:17:30 (752 KB/s) - ‘Forensics_is_fun.pptm’ saved [100145/100145]

                                                                                                                
 
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ find macrohard -type f -name "hidden"
macrohard/ppt/slideMasters/hidden
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ cat macrohard/ppt/slideMasters/hidden
Z m x h Z z o g Y W N h Z G V t e X t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                                                                
┌──(kali㉿kali)-[~]
└─$ cat macrohard/ppt/slideMasters/hidden | tr -d ' ' | base64 -d
flag: academy{D1d_u_kn0w_ppts_r_z1p5}     ```


```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/ef35dfe613527d28fe872d94179b53bc1a0497ddecf57e51d160c910be3a8e8a/Forensics_is_fun.pptm