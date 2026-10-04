## Descripción
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz).
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz -o fixme2.tar.gz

Dark23-academy@webshell:~$ tar -xzvf fixme2.tar.gz

Dark23-academy@webshell:~$ cat fixme2/src/main.rs

Dark23-academy@webshell:~$ cat fixme2/Cargo.toml

academy{4r3_y0u_h4v1n5_fun_y31?}


```
## Notas Adicionales
Los comentarios son pistas directas sobre el **borrow checker**: para modificar un valor prestado, se necesita un préstamo **mutable** (`&mut`), no uno inmutable (`&`). Hay 3 cambios relacionados:

1. La función debe recibir `&mut String`, no `&String`
2. La variable `party_foul` debe declararse como `mut`
3. Al llamarla, hay que pasar `&mut party_foul`, no `&party_foul`
## Referencias
https://challenge-files.cylabacademy.net/library/048c73621a97b98cde18eae5a9495279f2396cb64c65235bb310e7ad26d726ac/fixme2.tar.gz