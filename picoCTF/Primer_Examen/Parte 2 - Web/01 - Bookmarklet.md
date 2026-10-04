## Descripción
Why search for the flag when I can make a bookmarklet to print it for me? Browse [here](http://chatelaine.cylabacademy.net:30002/), and find the flag!
http://chatelaine.cylabacademy.net:30002/
## Solución
```
(function() {
    var encryptedBytes = [209,204,196,211,200,225,223,235,217,163,214,150,211,218,229,219,209,162,213,211,202,214,203,198,167,200,215,155,237];
    var key = "picoctf";
    var decryptedFlag = "";
    for (var i = 0; i < encryptedBytes.length; i++) {
        decryptedFlag += String.fromCharCode((encryptedBytes[i] - key.charCodeAt(i % key.length) + 256) % 256);
    }
    console.log(decryptedFlag);
})();
academy{p@g3_turn3r_dfbc8ec5}

```
## Notas Adicionales
Es un **cifrado Vigenère a nivel de bytes**. Cada carácter del flag se cifró sumándole un carácter de la clave `picoctf`, que se repite en ciclo. Para descifrar, se hace la resta inversa.
## Referencias
http://chatelaine.cylabacademy.net:30002/