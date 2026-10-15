## Descripción
Unzip this archive and find the file named 'uber-secret.txt'
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/72ca8cb60e55a597886dfb8e20bdb28d3ea7e73ca72987eb813a3558a8dd22bf/files.zip

Dark23-academy@webshell:~$ ls
files.zip
Dark23-academy@webshell:~$ unzip files.zip 

Dark23-academy@webshell:~$ cd files/
Dark23-academy@webshell:~/files$ cd adequate_books/
Dark23-academy@webshell:~/files/adequate_books$ cd .secret
-bash: cd: .secret: No such file or directory
Dark23-academy@webshell:~/files/adequate_books$ cd deeper_secrets
-bash: cd: deeper_secrets: No such file or directory
Dark23-academy@webshell:~/files/adequate_books$ cd more_books/
Dark23-academy@webshell:~/files/adequate_books/more_books$ cd .secret/
Dark23-academy@webshell:~/files/adequate_books/more_books/.secret$ cd deeper_secrets/
Dark23-academy@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets$ cd deepest_secrets/
Dark23-academy@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ ls
uber-secret.txt
Dark23-academy@webshell:~/files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets$ cat uber-secret.txt 
academy{f1nd_15_f457_ab443fd1}
```
## Notas Adicionales
bajar el archivo y descomprimirlo dirijirse al directorio del archivo de forma manual o con uso de un grep recursivo buscar la bandera entre todos los archivos.


## Referencias
[Webshell](https://webshell.cylabacademy.org/) grep --help -r, --recursive like --directories=recurse [https://gemini.google.com/](https://gemini.google.com/)