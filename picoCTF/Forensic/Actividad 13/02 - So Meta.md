## Descripción
Find the flag in this [picture](https://challenge-files.cylabacademy.net/library/7d12ed78e80c80afccae7ae860ed2277f044812e86c7267efbf7e0200fc9fd1e/pico_img.png).

Hints

1

What does meta mean in the context of files?

2

Ever heard of metadata?
## Solución
```
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/7d12ed78e80c80afccae7ae860ed2277f044812e86c7267efbf7e0200fc9fd1e/pico_img.png
--2026-11-20 00:42:58--  https://challenge-files.cylabacademy.net/library/7d12ed78e80c80afccae7ae860ed2277f044812e86c7267efbf7e0200fc9fd1e/pico_img.png
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.49, 18.238.132.26, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: ‘pico_img.png’

pico_img.png                100%[===========================================>] 106.25K  --.-KB/s    in 0.09s   

2026-11-20 00:42:59 (1.20 MB/s) - ‘pico_img.png’ saved [108795/108795]

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 

exiftool pico_img.png
ExifTool Version Number         : 13.55
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2026:09:22 21:49:13-04:00
File Access Date/Time           : 2026:11:20 00:42:59-05:00
File Inode Change Date/Time     : 2026:11:20 00:42:59-05:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : academy{s0_m3ta_d4aa0408}
Image Size                      : 600x600
Megapixels                      : 0.360
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 
strings pico_img.png | grep -a academy
academy{s0_m3ta_d4aa0408}

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/7d12ed78e80c80afccae7ae860ed2277f044812e86c7267efbf7e0200fc9fd1e/pico_img.png
