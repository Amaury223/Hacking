## Descripción
What can you do with this file? I forgot the key to my safe but this [file](https://challenge-files.cylabacademy.net/library/1937d782bd52c58eba27872bc91abb6506ff944075f3e2fcb27595fa319f5f5d/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

Hints

1

Download and try to decompile the file.
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/1937d782bd52c58eba27872bc91abb6506ff944075f3e2fcb27595fa319f5f5d/SafeOpener.class

Dark23-academy@webshell:~$ file SafeOpener.class
SafeOpener.class: compiled Java class data, version 52.0 (Java 1.8)

Dark23-academy@webshell:~$ strings SafeOpener.class | grep academy
,academy{SAf3_0p3n3rr_y0u_solv3d_it_99d44813}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/1937d782bd52c58eba27872bc91abb6506ff944075f3e2fcb27595fa319f5f5d/SafeOpener.class