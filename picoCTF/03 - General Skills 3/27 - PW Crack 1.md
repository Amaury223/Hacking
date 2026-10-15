## Descripción
Can you crack the password to get the flag? Download the password checker [here](https://challenge-files.cylabacademy.net/library/85308c2e48584c90de2af360f3324194bde62acf79d53364ea85fd34ce0eaa1f/level1.py) and you'll need the encrypted [flag](https://challenge-files.cylabacademy.net/library/85308c2e48584c90de2af360f3324194bde62acf79d53364ea85fd34ce0eaa1f/level1.flag.txt.enc) in the same directory too.

## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/85308c2e48584c90de2af360f3324194bde62acf79d53364ea85fd34ce0eaa1f/level1.py

Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/85308c2e48584c90de2af360f3324194bde62acf79d53364ea85fd34ce0eaa1f/level1.flag.txt.enc

Dark23-academy@webshell:~$  ls
Addadshashanammu      README.txt  codebook.txt  enc_flag  files.zip  fixme2.py    l.save               level1.py
Addadshashanammu.zip  code.py     convertme.py  files     fixme1.py  fixme2.py.1  level1.flag.txt.enc  runme.py

Dark23-academy@webshell:~$ nano level1.py
Dark23-academy@webshell:~$ python3 level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
academy{545h_r1ng1ng_329bb7f6}
```
## Notas Adicionales

## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)
