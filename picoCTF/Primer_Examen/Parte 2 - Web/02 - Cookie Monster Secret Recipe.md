## Descripción
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe? You can access the Cookie Monster [here](http://xebec.cylabacademy.net:15090/) and good luck

http://xebec.cylabacademy.net:15090/
## Solución
```
secret_recipe

YWNhZGVteXtjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzM0RUYyQ0U4fQ%3D%3D

Base64
academy{c00k1e_m0nster_l0ves_c00kies_34EF2CE8}
```
## Notas Adicionales
1. El sitio protegía el acceso con una verificación basada en **cookies**, no en contraseña (tal como decía la pista "Me no need password. Me just need cookies!").
2. se encontró una cookie llamada **`secret_recipe`** con un valor codificado.
3. El valor estaba en **Base64** (con `%3D%3D` al final, que es `==` codificado como entidad URL — típico relleno de Base64).
4. Al decodificar `YWNhZGVteXtjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzM0RUYyQ0U4fQ==` se obtiene directamente la flag en texto plano.
## Referencias
http://xebec.cylabacademy.net:15090/