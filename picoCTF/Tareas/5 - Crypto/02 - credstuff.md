## Descripción
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here]([https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar](https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar)).  
The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.  
Hints  
1  
Maybe other passwords will have hints about the leak?
## Solución
```
Dark23-academy@webshell:~$ wget -O leak.tar "https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar"

Dark23-academy@webshell:~$ tar -xf leak.tar

Dark23-academy@webshell:~$ cd leak

Dark23-academy@webshell:~/leak$ grep -n "cultiris" usernames.txt
378:cultiris

Dark23-academy@webshell:~/leak$ sed -n '378p' passwords.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
academy{C7r1F_54V35_71M3}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar