## Descripción
Can you break into this super secure portal?

[http://fickle-tempest.picoctf.net:59053](http://fickle-tempest.picoctf.net:59053/)
## Solución
```
encotrar el script que mada la badera y con ayuda de gemini descifrar la bandera
|   |
|---|
|<script type="text/javascript">|
|function verify() {|
|checkpass = document.getElementById("pass").value;|
|split = 4;|
|if (checkpass.substring(0, split) == 'pico') {|
|if (checkpass.substring(split*6, split*7) == 'eb02') {|
|if (checkpass.substring(split, split*2) == 'CTF{') {|
|if (checkpass.substring(split*4, split*5) == 'ts_p') {|
|if (checkpass.substring(split*3, split*4) == 'lien') {|
|if (checkpass.substring(split*5, split*6) == 'lz_2') {|
|if (checkpass.substring(split*2, split*3) == 'no_c') {|
|if (checkpass.substring(split*7, split*8) == 'b45}') {|
|alert("Password Verified")|
|}|
|}|
|}|
||
|}|
|}|
|}|
|}|
|}|
|else {|
|alert("Incorrect password");|
|}|
||
|}|
|</script>|

```
```
picoCTF{no_clients_plz_2eb02b45}
```
## Notas Adicionales
Encontrar el script que oculta la bandera y con ayuda de gemin obtenerla.
## Referencias
https://gemini.google.com/app