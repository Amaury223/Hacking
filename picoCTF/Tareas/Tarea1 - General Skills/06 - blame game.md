## Descripción
Someone's commits seems to be preventing the program from working. Who is it?

You can download the challenge files here:

- [challenge.zip](https://challenge-files.cylabacademy.net/library/d512f346c4d9094e7a493e9cf487c9e42ef328aef5f876980ae7ba1df71e29da/challenge.zip)

Hints

1

In collaborative projects, many users can make many changes. How can you see the changes within one file?

2

Read the chapter on Git from the picoPrimer [here](https://primer.cylabacademy.org/#_git_version_control).

3

You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/d512f346c4d9094e7a493e9cf487c9e42ef328aef5f876980ae7ba1df71e29da/challenge.zip
--2026-11-20 22:52:58--  https://challenge-files.cylabacademy.net/library/d512f346c4d9094e7a493e9cf487c9e42ef328aef5f876980ae7ba1df71e29da/challenge.zip
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.95, 3.160.5.40, 3.160.5.18, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 297469 (290K) [application/octet-stream]
Saving to: 'challenge.zip.1'

challenge.zip.1     100%[==================>] 290.50K  1.84MB/s    in 0.2s    

2026-11-20 22:52:58 (1.84 MB/s) - 'challenge.zip.1' saved [297469/297469]

Dark23-academy@webshell:~$ unzip challenge.zip


Dark23-academy@webshell:~$ find . -type f

Dark23-academy@webshell:~$ cd drop-in
Dark23-academy@webshell:~/drop-in$ git blame message.py

[1]+  Stopped                 git blame message.py

6512138f (academy{@sk_th3_1nt3rn_4361f04c} 2026-09-23 05:06:46 +0000 1) print("Hello, World!"
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/d512f346c4d9094e7a493e9cf487c9e42ef328aef5f876980ae7ba1df71e29da/challenge.zip

https://primer.cylabacademy.org/#_git_version_control