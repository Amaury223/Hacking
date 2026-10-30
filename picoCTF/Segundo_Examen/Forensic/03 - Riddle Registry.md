## Descripción
Hi, intrepid investigator! 📄🔍 You've stumbled upon a peculiar PDF filled with what seems like nothing more than garbled nonsense. But beware! Not everything is as it appears. Amidst the chaos lies a hidden treasure—an elusive flag waiting to be uncovered. Find the PDF file here [Hidden Confidential Document](https://challenge-files.cylabacademy.net/library/b32f1f1945481591df61d328d02995fe3521d16b70928fbe44e3bd90c4ccb113/confidential.pdf) and uncover the flag within the metadata.

Hints

1

Don't be fooled by the visible text; it’s just a decoy!

2

Look beyond the surface for hidden clues
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/b32f1f1945481591df61d328d02995fe3521d16b70928fbe44e3bd90c4ccb113/confidential.pdf

Dark23-academy@webshell:~$ exiftool confidential.pdf
ExifTool Version Number         : 12.40
File Name                       : confidential.pdf
Directory                       : .
File Size                       : 178 KiB
File Modification Date/Time     : 2026:09:23 06:28:08+00:00
File Access Date/Time           : 2026:10:28 00:35:40+00:00
File Inode Change Date/Time     : 2026:10:28 00:35:40+00:00
File Permissions                : -rw-rw-r--
File Type                       : PDF
File Type Extension             : pdf
MIME Type                       : application/pdf
PDF Version                     : 1.7
Linearized                      : No
Page Count                      : 1
Producer                        : PyPDF2
Author                          : YWNhZGVteXtwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV85ZDNjYzY2OX0=
Dark23-academy@webshell:~$ echo 'YWNhZGVteXtwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV85ZDNjYzY2OX0=' | base64 -d
academy{puzzl3d_m3tadata_f0und!_9d3cc669}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/b32f1f1945481591df61d328d02995fe3521d16b70928fbe44e3bd90c4ccb113/confidential.pdf