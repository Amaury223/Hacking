## Descripción
A new modular challenge! Download the message [here](https://challenge-files.cylabacademy.net/library/8493f8b1c07d84e858fa52d3dacdc63752275286da7a30b69fab36993eafb5ea/message.txt).

Take each number mod 41 and find the modular inverse for the result. Then map to the following character set: 1-26 are the alphabet, 27-36 are the decimal digits, and 37 is an underscore.

Wrap your decrypted message in the academy flag format (i.e. `academy{decrypted_message}`)

Hints

1

Do you know what the modular inverse is?

2

The inverse modulo _z_ of _x_ is the number, _y_ that when multiplied by _x_ is 1 modulo _z_

3

It's recommended to use a tool to find the modular inverses
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/8493f8b1c07d84e858fa52d3dacdc63752275286da7a30b69fab36993eafb5ea/message.txt -o message.txt

Dark23-academy@webshell:~$ cat message.txt
432 126 192 354 98 296 272 311 146 297 364 373 262 277 215 377 255 407 72 46 213 448 212 

academy{1nv3r53ly_h4rd_950d690f}
```
## Notas Adicionales
1. Para cada número, calculé `número mod 41`
2. Luego busqué el **inverso modular** de ese resultado mod 41 (usando el algoritmo extendido de Euclides) — es decir, el número `y` tal que `(resultado × y) mod 41 = 1`
3. Mapeé el inverso resultante al conjunto de caracteres dado: 1-26 → a-z, 27-36 → 0-9, 37 → `_`
## Referencias
https://challenge-files.cylabacademy.net/library/8493f8b1c07d84e858fa52d3dacdc63752275286da7a30b69fab36993eafb5ea/message.txt