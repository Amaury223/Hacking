## Descripción
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz).
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz -o fixme3.tar.gz

Dark23-academy@webshell:~$ tar -xzvf fixme3.tar.gz

Dark23-academy@webshell:~$ cat fixme3/src/main.rs

Dark23-academy@webshell:~$ cat fixme3/Cargo.toml

academy{n0w_y0uv3_f1x3d_1h3m_411}
```
## Notas Adicionales
**El fix:** solo había que descomentar el bloque `unsafe { ... }` que envuelve la llamada a `std::slice::from_raw_parts`. En Rust, operaciones como deferenciar punteros crudos solo están permitidas dentro de bloques marcados explícitamente como `unsafe`, porque el compilador no puede garantizar su seguridad de memoria ahí — el programador asume esa responsabilidad manualmente.


1. **fixme1** → errores básicos de sintaxis (`;` faltante, `ret` vs `return`, formato de `println!`)
2. **fixme2** → _borrowing_ mutable (`&mut`)
3. **fixme3** → bloques `unsafe` para operaciones con punteros crudos
## Referencias
https://challenge-files.cylabacademy.net/library/6df8b7779faf29e53f515922041d99bc26381a332ca090c291ba20577ac7cf92/fixme3.tar.gz