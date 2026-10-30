## Descripción
You will find the flag after decrypting this file Download the encrypted flag [here](https://challenge-files.cylabacademy.net/library/545f29dd6d01fbbfe2cb0c2616132c3b10c64c676d94c9cc88d3fc15020078a2/encrypted.txt).

Hints

1

Sometimes rotation is right
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/545f29dd6d01fbbfe2cb0c2616132c3b10c64c676d94c9cc88d3fc15020078a2/encrypted.txt -o encrypted.txt

Dark23-academy@webshell:~$ cat encrypted.txt
ikilmug{z0bib1wv_l3kzgxb3l_91mllij9}

academy{r0tat1on_d3crypt3d_91eddab9}
```
## Notas Adicionales
Era un cifrado **ROT-N** (César), y encontré el desplazamiento correcto (N=18) probando las 26 rotaciones posibles hasta que una produjo el prefijo `academy{` esperado. El hint (“a veces la rotación es hacia la derecha”) confirma que no era el típico ROT13, sino una rotación distinta — en este caso, rotar cada letra 18 posiciones.
## Referencias
https://challenge-files.cylabacademy.net/library/545f29dd6d01fbbfe2cb0c2616132c3b10c64c676d94c9cc88d3fc15020078a2/encrypted.txt