## Descripción
Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way.
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/2e9bfa4e1d90ac25a999fefdfb4feb8a2ff4eb73e4c61af4889a3762687ada01/file
--2026-08-20 05:33:14--  https://challenge-files.picoctf.net/c_fickle_tempest/2e9bfa4e1d90ac25a999fefdfb4feb8a2ff4eb73e4c61af4889a3762687ada01/file
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.40, 3.160.5.95, 3.160.5.18, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14546 (14K) [application/octet-stream]
Saving to: 'file'

file                 100%[===================>]  14.21K  --.-KB/s    in 0s      

Descargué el archivo usando wget "link" luego usé cat file | grep pico
- picoCTF{grep_is_good_to_find_things_29f42460}
```



## Notas Adicionales
## Referencias

- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)