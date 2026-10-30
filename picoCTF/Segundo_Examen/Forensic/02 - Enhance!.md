## Descripción
Download this image file and find the flag.

- [Download image file](https://challenge-files.cylabacademy.net/library/83bfcd323363337f297f4d4ee3bff06df8564155aa2037148151710fa8baec04/drawing.flag.svg)
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/83bfcd323363337f297f4d4ee3bff06df8564155aa2037148151710fa8baec04/drawing.flag.svg

Dark23-academy@webshell:~$ grep '</tspan>' drawing.flag.svg | cut -d '>' -f2 | cut -d '<' -f1 | tr -d '\n ' 
academy{3nh4nc3d_5b5e6f18}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/83bfcd323363337f297f4d4ee3bff06df8564155aa2037148151710fa8baec04/drawing.flag.svg