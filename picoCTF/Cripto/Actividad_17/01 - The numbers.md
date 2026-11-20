## Descripción
The numbers... what do they mean? [numbers](https://challenge-files.cylabacademy.net/library/664bc3a85525cfd5a2af151d29f2744ba334880e28e60f9a513aba13633199d4/the_numbers.png)

Hints

1

The flag is in the format PICOCTF{}
## Solución
```
La imagen contiene números que debes convertir en letras siguiendo esa correspondencia.

Puedes utilizar Python para automatizarlo:
numeros = [16, 9, 3, 15, 3, 20, 6]

mensaje = ""

for n in numeros:
    mensaje += chr(n + 64)

print(mensaje)

PICOCTF{THENUMBERSMASON}
```
![[Pasted image 20261120150739.png]]

## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/664bc3a85525cfd5a2af151d29f2744ba334880e28e60f9a513aba13633199d4/the_numbers.png