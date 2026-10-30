## Descripción
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log. Download the encoded data here: [Logs Data](https://challenge-files.cylabacademy.net/library/e6fc51b98dd61381c5cd54dc836c8344fb475f17728f2095969e3a0f401ea195/logs.txt). Be prepared—the file is large, and examining it thoroughly is crucial .

Hints

1

Use `base64` to decode the data and generate the image file.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget "https://challenge-files.cylabacademy.net/library/e6fc51b98dd61381c5cd54dc836c8344fb475f17728f2095969e3a0f401ea195/logs.txt"

┌──(kali㉿kali)-[~]
└─$ base64 -d logs.txt > flag.png
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ file flag.png
flag.png: PNG image data, 896 x 1152, 8-bit/color RGB, non-interlaced

xdg-open flag.png

Decodificamos mensaje

academy{forensics_analysis_is_amazing_2043dbd1}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/e6fc51b98dd61381c5cd54dc836c8344fb475f17728f2095969e3a0f401ea195/logs.txt