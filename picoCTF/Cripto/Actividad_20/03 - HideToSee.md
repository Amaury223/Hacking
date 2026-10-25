## Descripción
How about some hide and seek heh? Look at this image [here](https://challenge-files.cylabacademy.net/library/d1a6b6365f32679d90a52e42234c7bad12bdfb9ac5e87598af9f1202ee047227/atbash.jpg).

Hints

1

Download the image and try to extract it.
## Solución
```
Dark23-academy@webshell:~$ wget -O atbash.jpg "https://challenge-files.cylabacademy.net/library/d1a6b6365f32679d90a52e42234c7bad12bdfb9ac5e87598af9f1202ee047227/atbash.jpg"

Dark23-academy@webshell:~$ cat encrypted.txt
zxzwvnb{zgyzhs_xizxp_02u11yy3}
Dark23-academy@webshell:~$ python3 -c "
> text = open('encrypted.txt').read().strip()
> def atbash(ch):
>     if ch.isalpha():
>         base = ord('a') if ch.islower() else ord('A')
>         return chr(base + 25 - (ord(ch) - base))
>     return ch
> print(''.join(atbash(c) for c in text))
> "
academy{atbash_crack_02f11bb3}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/d1a6b6365f32679d90a52e42234c7bad12bdfb9ac5e87598af9f1202ee047227/atbash.jpg