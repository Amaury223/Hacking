## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.py) and you'll need the encrypted [flag](https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.flag.txt.enc) and the [hash](https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.hash.bin) in the same directory too.

There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.py
 
 
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.flag.txt.enc

Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/ae8548417223f50bd8a748c28e60fc688e1426cc7be7b09142456c1427def2c3/level3.hash.bin


Dark23-academy@webshell:~$ tail level3.py



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

Dark23-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: f06e
That password is incorrect
Dark23-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: 4dcf
That password is incorrect
Dark23-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: 87ab
That password is incorrect
Dark23-academy@webshell:~$ python3 level3.py
Please enter correct password for flag: dba8
Welcome back... your flag, user:
academy{m45h_fl1ng1ng_f684152a}
```
## Notas Adicionales

## Referencias

- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)