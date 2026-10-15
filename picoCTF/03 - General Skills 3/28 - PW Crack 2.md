## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://challenge-files.cylabacademy.net/library/da3b21f411362ad5c273b3a48a829e1a6f011d43998fabc480a2b1f3585aff0b/level2.py) and you'll need the encrypted [flag](https://challenge-files.cylabacademy.net/library/da3b21f411362ad5c273b3a48a829e1a6f011d43998fabc480a2b1f3585aff0b/level2.flag.txt.enc) in the same directory too.

## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/da3b21f411362ad5c273b3a48a829e1a6f011d43998fabc480a2b1f3585aff0b/level2.py

Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/da3b21f411362ad5c273b3a48a829e1a6f011d43998fabc480a2b1f3585aff0b/level2.flag.txt.enc

Dark23-academy@webshell:~$ nano level2.py

Dark23-academy@webshell:~$ python3                     
.cache/           .ssh/             code.py           files/            fixme2.py         level2.py         
.local/           Addadshashanammu/ convertme.py      fixme1.py         level1.py         runme.py          
Dark23-academy@webshell:~$ python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
academy{tr45h_51ng1ng_ab548076}
```
## Notas Adicionales

## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)
[)