## Descripción
This file doesn't look like much... just a bunch of 1s and 0s. But maybe it's not just random noise. Can you recover anything meaningful from this? Download the file [here](https://challenge-files.cylabacademy.net/library/4f119c7324ffc27875b984a1d0db0591c4214fa81bd566946f1d08ed29f35135/digits.bin).
## Solución
```
──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/4f119c7324ffc27875b984a1d0db0591c4214fa81bd566946f1d08ed29f35135/digits.bin 

┌──(kali㉿kali)-[~]
└─$ file digits.bin
head -c 100 digits.bin
digits.bin: ASCII text, with very long lines (65536), with no line terminators
1111111111011000111111111110000000000000000100000100101001000110010010010100011000000000000000010000                                                                                                                
┌──(kali㉿kali)-[~]
└─$ python3 - <<'PY'
bits = open("digits.bin", "r").read()
bits = ''.join(bits.split())

print("Cantidad de bits:", len(bits))
print("Divisible entre 8:", len(bits) % 8 == 0)

data = bytes(
    int(bits[i:i+8], 2)
    for i in range(0, len(bits), 8)
)

with open("decoded.jpg", "wb") as f:
    f.write(data)

print("Imagen guardada como decoded.jpg")
PY
Cantidad de bits: 71312
Divisible entre 8: True
Imagen guardada como decoded.jpg
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ file decoded.jpg
decoded.jpg: JPEG image data, JFIF standard 1.01, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 800x500, components 3
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ xdg-open decoded.jpg


academy{h1dd3n_1n_th3_b1n4ry_75fdfb71}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/4f119c7324ffc27875b984a1d0db0591c4214fa81bd566946f1d08ed29f35135/digits.bin