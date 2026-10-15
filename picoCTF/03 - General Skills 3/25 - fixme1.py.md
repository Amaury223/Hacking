## Descripción
Fix the syntax error in this Python script to print the flag. [Download Python script](https://challenge-files.cylabacademy.net/library/a7565be9118cb42cf66dd23265088dc898cf9a845849c2d4833d40b1714ada46/fixme1.py)
`
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/a7565be9118cb42cf66dd23265088dc898cf9a845849c2d4833d40b1714ada46/fixme1.py

Dark23-academy@webshell:~$ python3 fixme1.py 
  File "/home/Dark23-academy/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent


Dark23-academy@webshell:~$ nano fixme1.py


def str_xor(secret, key):
    # extender la clave a la longitud del secreto
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c, new_key_c) in zip(secret, new_key)])

flag_enc = chr(0x04) + chr(0x0d) + chr(0x0a) + chr(0x0d) + chr(0x01) + chr(0x18) + chr(0x1c) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x5a) + chr(0x08) + chr(0x57) + chr(0x10) + chr(0x01) + chr(0x0f) + chr(0x5a) + chr(0x14)

flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)


Dark23-academy@webshell:~$ python3 fixme1.py 
That is correct! Here's your flag: academy{1nd3nt1ty_cr1515_11a3eda1}
```
## Notas Adicionales
- Los programas en Python pueden no ejecutarse correctamente debido a errores de sintaxis, se corrigieron y listo
- nano -l - abre el archivo en el editor y muestra los números de línea

## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)