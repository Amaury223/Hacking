## Descripción
Can you get the flag? Go to this [website](http://chatelaine.cylabacademy.net:46934/) and see what you can discover.

Instance

Expires in 14:54

Hints

1

Is there more code than what the inspector initially shows?
## Solución
```
Dark23-academy@webshell:~$ curl -s http://chatelaine.cylabacademy.net:46934/script.js



function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_254cc2a8}
Dark23-academy@webshell:~$ curl -s http://chatelaine.cylabacademy.net:46934/style.css
body {
  background-color: lightblue;
}

/*  academy{1nclu51v17y_1of2_  */
Dark23-academy@webshell:~$ 


academy{1nclu51v17y_1of2_f7w_2of2_254cc2a8}
```
## Notas Adicionales
## Referencias
http://chatelaine.cylabacademy.net:46934/
