## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.

1

After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...
## Solución
```
wget https://challenge-files.picoctf.net/c_wily_courier/ce53ef9432bf367be41e465224d721c1187c39debcd758efcd28e99a6b7ff7a4/Addadshashanammu.zip

Dark23-academy@webshell:~$ unzip Addadshashanammu.zip 


Dark23-academy@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  enc_flag  files  files.zip
Dark23-academy@webshell:~$ cat Addadshashanammu
cat: Addadshashanammu: Is a directory
Dark23-academy@webshell:~$ cd Addadshashanammu/
Dark23-academy@webshell:~/Addadshashanammu$ ls
Almurbalarammi
Dark23-academy@webshell:~/Addadshashanammu$ cat Almurbalarammi/
cat: Almurbalarammi/: Is a directory
Dark23-academy@webshell:~/Addadshashanammu$ cd Almurbalarammi/
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi$ ls
Ashalmimilkala
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi$ cd Ashalmimilkala/
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala$ cd Assurnabitashpi/
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ ls
Maelkashishi
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi$ cd Maelkashishi/
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ 
ls
Onnissiralis
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi$ 
cd Onnissiralis/
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/O
nnissiralis$ cd Ularradallaku/
Dark23-academy@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/O
nnissiralis/Ularradallaku$ ls 
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c

cat fang-of-haynekhtnamet
academy{l3v3l_up!_t4k3_4_r35t!_9d928112}
```
## Notas Adicionales
2 soluciones en la primera hacemos uso de strings y buscamos directamente la bandera y en la solucion 2 descomprimimos el archivo y al ingresar con ayuda de tab nos dirigimos hasta el fondo del el directorio llegando a un archivo el cual solo ejecutamos y obtenemos la bandera
## Referencias
[Webshell](https://webshell.cylabacademy.org/)