## Descripción
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/504/big-zip-files.zip)

Can grep be instructed to look at every file in a directory and its subdirectories?
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/b150f6f4d21f46fc2bba57ef49c7305541fa8e9bfa4241dfe8d066b99de56200/big-zip-files.zip

Dark23-academy@webshell:~$ unzip big-zip-files


picoCTF{gr3p_15_m4g1c_ef8790dc}
 

```
## Notas Adicionales
grep -r "pico" big-zip-files/

con grep llamamos la herramienta de busqueda con -r hacemos el proceso recursivo y colocamos la palabra a buscar seguido del directorio con / al final
## Referencias
https://challenge-files.cylabacademy.net/library/b150f6f4d21f46fc2bba57ef49c7305541fa8e9bfa4241dfe8d066b99de56200/big-zip-files.zip
