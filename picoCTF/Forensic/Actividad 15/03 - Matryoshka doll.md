## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [dolls.jpg](https://challenge-files.cylabacademy.net/library/370b91d430bc7ec8382557bcd2fba17a0e4e8ff86df14476a40c9f4b91276fa8/dolls.jpg)

Hints

1

Wait, you can hide files inside files? But how do you find them?

2

Make sure to submit the flag as academy{XXXXX}
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget "https://challenge-files.cylabacademy.net/library/370b91d430bc7ec8382557bcd2fba17a0e4e8ff86df14476a40c9f4b91276fa8/dolls.jpg" -O dolls.jpg
--2026-11-20 03:09:20--  https://challenge-files.cylabacademy.net/library/370b91d430bc7ec8382557bcd2fba17a0e4e8ff86df14476a40c9f4b91276fa8/dolls.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.49, 18.238.132.26, 18.238.132.88, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651609 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg                   100%[===========================================>] 636.34K  3.31MB/s    in 0.2s    

2026-11-20 03:09:21 (3.31 MB/s) - ‘dolls.jpg’ saved [651609/651609]

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378929, uncompressed size: 383919, name: base_images/2_c.jpg
651587        0x9F143         End of Zip archive, footer length: 22

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ sudo apt install binwalk -y
[sudo] password for kali: 
binwalk is already the newest version (2.4.3+dfsg1-3).
binwalk set to manually installed.
Summary:                    
  Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 1150
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ binwalk -Me dolls.jpg

Scan Time:     2026-11-20 03:09:49
Target File:   /home/kali/dolls.jpg
MD5 Checksum:  1b06594ad8610fea397cff63dfb51410
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378929, uncompressed size: 383919, name: base_images/2_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


Scan Time:     2026-11-20 03:09:49
Target File:   /home/kali/_dolls.jpg.extracted/base_images/2_c.jpg
MD5 Checksum:  fe7145cb4d1bcdb17c28e141a9e47c9a
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196024, uncompressed size: 201426, name: base_images/3_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


Scan Time:     2026-11-20 03:09:49
Target File:   /home/kali/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/3_c.jpg
MD5 Checksum:  28d50d0bf349b643b82a3fd48e283e08
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77632, uncompressed size: 79786, name: base_images/4_c.jpg

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


Scan Time:     2026-11-20 03:09:49
Target File:   /home/kali/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/4_c.jpg
MD5 Checksum:  0ee09e5faaf2c4892ea57a6fdfa49e40
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
79578         0x136DA         Zip archive data, at least v1.0 to extract, compressed size: 42, uncompressed size: 42, name: flag.txt

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


Scan Time:     2026-11-20 03:09:49
Target File:   /home/kali/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted/flag.txt
MD5 Checksum:  08c3fd098fed8bdc83a59ef3608e3713
Signatures:    436

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ find . -type f -name "flag.txt"
./_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted/flag.txt
./flag.txt
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ cat "./_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted/flag.txt"
academy{ZNTyvSDXRNO1d0xCkBRMhAoiafpCTvgW}

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/370b91d430bc7ec8382557bcd2fba17a0e4e8ff86df14476a40c9f4b91276fa8/dolls.jpg
