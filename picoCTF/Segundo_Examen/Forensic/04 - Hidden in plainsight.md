## Descripción
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag. Download the jpg image [here](https://challenge-files.cylabacademy.net/library/90fe779e0989ed7c80652fdd2b165f9661a7a00ba75fc766d01cd4c0e489fdbd/img.jpg).

Hints

1

Download the jpg image and read its metadata
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/90fe779e0989ed7c80652fdd2b165f9661a7a00ba75fc766d01cd4c0e489fdbd/img.jpg

Dark23-academy@webshell:~$ exiftool img.jpg
ExifTool Version Number         : 12.40
File Name                       : img.jpg
Directory                       : .
File Size                       : 72 KiB
File Modification Date/Time     : 2026:09:23 05:38:54+00:00
File Access Date/Time           : 2026:10:28 00:38:17+00:00
File Inode Change Date/Time     : 2026:10:28 00:38:17+00:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Comment                         : c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9
Image Width                     : 640
Image Height                    : 640
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 640x640
Megapixels                      : 0.410


Dark23-academy@webshell:~$ exiftool -b -Comment img.jpg
c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9

Dark23-academy@webshell:~$ exiftool -T -Comment img.jpg | base64 -d
steghide:cEF6endvcmQ=

Dark23-academy@webshell:~$ exiftool -T -Comment img.jpg | base64 -d | cut -d ':' -f2 | base64 -d
pAzzword

Dark23-academy@webshell:~$ steghide extract -sf img.jpg -p 'pAzzword'
wrote extracted data to "flag.txt".

Dark23-academy@webshell:~$ cat flag.txt
academy{h1dd3n_1n_1m4g3_7ba83d11}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/90fe779e0989ed7c80652fdd2b165f9661a7a00ba75fc766d01cd4c0e489fdbd/img.jpg