## Descripción
Fix the syntax error in the Python script to print the flag. [Download Python script](https://challenge-files.cylabacademy.net/library/3a038347d42971d0651b7f6e3342f48ad23427ef7b34b94b5077d4f29af12415/fixme2.py)
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/3a038347d42971d0651b7f6e3342f48ad23427ef7b34b94b5077d4f29af12415/fixme2.py


Dark23-academy@webshell:~$ nano fixme2.py 


import random

def str_xor(secret, key):
    # extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c, new_key_c) in zip(secret, new_key)])

flag_enc = chr(0x04) + chr(0x0d) + chr(0x0a) + chr(0x0d) + chr(0x01) + chr(0x18) + chr(0x1c) + chr(0x15) + chr(0x58) + chr(0x18) + chr(0x11) + chr(0x41) + chr(0x09) + chr(0x5f) + chr(0x1f) + chr(0x10) + chr(0x3b) + chr(0x1b) + chr(0x55) + chr(0x10) + chr(0x01) + chr(0x0f) + chr(0x5a) + chr(0x14)

flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
    print('String XOR encountered a problem, quitting.')
else:
    print('That is correct! Here\'s your flag: ' + flag)
    
    
    Dark23-academy@webshell:~$ python3 fixme2.py.1 
That is correct! Here's your flag: academy{3qu4l1ty_n0t_4551gnm3nt_ad29eab9}
```
## Notas Adicionales
## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)