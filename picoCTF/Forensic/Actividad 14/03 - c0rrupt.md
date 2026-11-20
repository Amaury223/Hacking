## Descripción
We found this [file](https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery). Recover the flag.

Hints

1

Try fixing the file header
## Solución
```
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery
--2026-11-20 01:18:23--  https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.49, 18.238.132.115, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 201205 (196K) [application/octet-stream]
Saving to: ‘c0rrupt-mystery’

c0rrupt-mystery             100%[===========================================>] 196.49K  --.-KB/s    in 0.1s    

2026-11-20 01:18:24 (1.49 MB/s) - ‘c0rrupt-mystery’ saved [201205/201205]

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ file c0rrupt-mystery
c0rrupt-mystery: data
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ xxd -l 64 c0rrupt-mystery
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 89 50 4e 47 0d 0a 1a 0a
89: command not found
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ nano reparar.py
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ python3 reparar.py
[+] Archivo reparado: reparado.png
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ file reparado.png
reparado.png: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ sudo apt install pngcheck -y

┌──(kali㉿kali)-[~]
└─$ pngcheck -v reparado.png
zlib warning:  different version (expected 1.3.1, using 1.3.2)

File: reparado.png (201205 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  CRC error in chunk pHYs (computed 495224f0, expected 38d82c82)
ERRORS DETECTED in reparado.png
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ xdg-open reparado.png
academy{c0rrupt10n_1847995}
```
![[Pasted image 20261120002037.png]]
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/8388ecc430588d15064755583476bec46e23d42a6d8de6e8995c19e40f2e4c58/c0rrupt-mystery