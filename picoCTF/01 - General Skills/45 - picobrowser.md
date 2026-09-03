## Descripción
This website can be rendered only by picobrowser, go and catch the flag!

[http://fickle-tempest.picoctf.net:59321](http://fickle-tempest.picoctf.net:59321/)
## Solución
```
Dark23-academy@webshell:~$ curl -s http://fickle-tempest.picoctf.net:59321/flag -H "User-Agent: picobrowser" | grep pico
         <!-- <strong>Title</strong> --> picobrowser!
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}</code></p>
```
picoCTF{p1c0_s3cr3t_ag3nt_fba5c48f}
## Notas Adicionales
acceder como picobrowser desde la terminal ya que con otro ... browser ya que con otro cliente no muestra la bandera
## Referencias
