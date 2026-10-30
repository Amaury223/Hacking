## Descripción
This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life? Download the file [here](https://challenge-files.cylabacademy.net/library/03e658f970a580c265471fa9e2477a66457bed10e5f89da0fe70c141c3509f3b/file).

Hints

1

Try checking the file’s header.

2

JPEG

3

Tools like xxd or hexdump can help you inspect and edit file bytes.
## Solución
```
Dark23-academy@webshell:~$ wget "https://challenge-files.cylabacademy.net/library/03e658f970a580c265471fa9e2477a66457bed10e5f89da0fe70c141c3509f3b/file" -O file

Dark23-academy@webshell:~$ xxd -l 32 file
00000000: 5c78 ffe0 0010 4a46 4946 0001 0100 0001  \x....JFIF......
00000010: 0001 0000 ffdb 0043 0008 0606 0706 0508  .......C........

Dark23-academy@webshell:~$ file file
file: data

Dark23-academy@webshell:~$ cp file file_original

Dark23-academy@webshell:~$ cp file file.jpg

Dark23-academy@webshell:~$ printf '\xff\xd8\xff' | dd of=file.jpg bs=1 count=3 conv=notrunc
3+0 records in
3+0 records out
3 bytes copied, 5.5401e-05 s, 54.2 kB/s

Dark23-academy@webshell:~$ file file.jpg
file.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 800x500, components 3

┌──(kali㉿kali)-[~]
└─$ xdg-open file.jpg

academy{r3st0r1ng_th3_by73s_69066302}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/03e658f970a580c265471fa9e2477a66457bed10e5f89da0fe70c141c3509f3b/file