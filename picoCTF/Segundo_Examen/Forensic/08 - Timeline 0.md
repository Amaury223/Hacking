## Descripción
Can you find the flag in this disk image? Wrap what you find in the academy{} flag format. Download the disk image [here](https://challenge-files.cylabacademy.net/library/bf9a20c350075c5863371e078daee1d570d4062902edc8a4a042e02a7cebf161/partition4.img.gz).

Hints

1

Create a Sleuthkit MAC timeline!

2

Sloppy timestomping can yield strange (very old) timestamps
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/bf9a20c350075c5863371e078daee1d570d4062902edc8a4a042e02a7cebf161/partition4.img.gz




┌──(kali㉿kali)-[~]
└─$ gunzip partition4.img.gz
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ fls -r -m / partition4.img > body.txt
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ mactime -b body.txt > timeline.txt
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ grep '1985' timeline.txt
Tue Jan 01 1985 12:00:00       41 macb r/rrw-r--r-- 0        0        4945     /bin/bcab
                            11017 m... r/rrw-r--r-- 0        0        1985     /lib/modules/6.6.116-0-lts/kernel/drivers/media/usb/gspca/gspca_sq930x.ko.gz
                            19859 m... r/rrw-r--r-- 0        0        3631     /lib/modules/6.6.116-0-lts/kernel/drivers/virt/nitro_enclaves/nitro_enclaves.ko.gz
                            11017 ...b r/rrw-r--r-- 0        0        1985     /lib/modules/6.6.116-0-lts/kernel/drivers/media/usb/gspca/gspca_sq930x.ko.gz
                            11017 ..c. r/rrw-r--r-- 0        0        1985     /lib/modules/6.6.116-0-lts/kernel/drivers/media/usb/gspca/gspca_sq930x.ko.gz
                            19859 ..cb r/rrw-r--r-- 0        0        3631     /lib/modules/6.6.116-0-lts/kernel/drivers/virt/nitro_enclaves/nitro_enclaves.ko.gz
                            11017 .a.. r/rrw-r--r-- 0        0        1985     /lib/modules/6.6.116-0-lts/kernel/drivers/media/usb/gspca/gspca_sq930x.ko.gz
                            19859 .a.. r/rrw-r--r-- 0        0        3631     /lib/modules/6.6.116-0-lts/kernel/drivers/virt/nitro_enclaves/nitro_enclaves.ko.gz
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ icat partition4.img 4945 > bcab.txt
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ cat bcab.txt
NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ base64 -d bcab.txt
71m311n3_0u7113r_h3r_43a2e7af


academy{71m311n3_0u7113r_h3r_43a2e7af}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/bf9a20c350075c5863371e078daee1d570d4062902edc8a4a042e02a7cebf161/partition4.img.gz