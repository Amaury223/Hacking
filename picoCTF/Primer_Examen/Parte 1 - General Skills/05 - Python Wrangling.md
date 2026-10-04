## Descripción
Python scripts are invoked kind of like programs in the Terminal... Can you run [ende.py](https://challenge-files.cylabacademy.net/library/1f8bb290392a5ab6795ba98cf621ec507bd52be282f62f32e35c43e0d7fc2415/ende.py) using [password.txt](https://challenge-files.cylabacademy.net/library/1f8bb290392a5ab6795ba98cf621ec507bd52be282f62f32e35c43e0d7fc2415/password.txt) to get [flag.txt.en](https://challenge-files.cylabacademy.net/library/1f8bb290392a5ab6795ba98cf621ec507bd52be282f62f32e35c43e0d7fc2415/flag.txt.en)?
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/1f8bb290392a5ab6795ba98cf621ec507bd52be282f62f32e35c43e0d7fc2415/ende.py -o ende.py

Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/1f8bb290392a5ab6795ba98cf621ec507bd52be282f62f32e35c43e0d7fc2415/password.txt -o password.txt

Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/1f8bb290392a5ab6795ba98cf621ec507bd52be282f62f32e35c43e0d7fc2415/flag.txt.en -o flag.txt.en

Dark23-academy@webshell:~$ cat ende.py

Dark23-academy@webshell:~$ cat password.txt
563e47ddeaf84eca8b2a31201381a898

Dark23-academy@webshell:~$ python3 ende.py -d flag.txt.en 563e47ddeaf84eca8b2a31201381a898

academy{4p0110_1n_7h3_h0us3_d6af8f37}

```
## Notas Adicionales
ejercicio para familiarizarse con invocar scripts de Python desde terminal con argumentos (`-d`, archivo, contraseña)
## Referencias