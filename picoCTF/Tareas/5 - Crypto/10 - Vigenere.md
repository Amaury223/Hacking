## Descripción
Can you decrypt this message? Decrypt this [message](https://challenge-files.cylabacademy.net/library/7e1288d31bc6645f95d07bcf09caaf93210591ba082ba0f14490f0767ad7fd33/cipher.txt) using this key "CYLAB".

Hints

1

[https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher](https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher)
## Solución
```
Dark23-academy@webshell:~$ wget -O cipher.txt "https://challenge-files.cylabacademy.net/library/7e1288d31bc6645f95d07bcf09caaf93210591ba082ba0f14490f0767ad7fd33/cipher.txt"

Dark23-academy@webshell:~$ cat cipher.txt

caldfow{O0NU_WQ3_G1G3O3T3_A1AH3S_4c372077}

Dark23-academy@webshell:~$ cat > vigenere.py << 'EOF'
> def decrypt(ciphertext, key):
>     key = key.upper()
>     result = []
>     ki = 0
>     for ch in ciphertext:
>         if ch.isalpha():
>             shift = ord(key[ki % len(key)]) - ord('A')
>             base  = ord('A') if ch.isupper() else ord('a')
>             result.append(chr((ord(ch) - base - shift) % 26 + base))
>             ki += 1
>         else:
>             result.append(ch)
>     return "".join(result)
> 
> cipher = open("cipher.txt").read().strip()
> print(decrypt(cipher, "CYLAB"))
> EOF



Dark23-academy@webshell:~$ python3 vigenere.py
academy{D0NT_US3_V1G3N3R3_C1PH3R_4a372077}
```
## Notas Adicionales
.
## Referencias

https://challenge-files.cylabacademy.net/library/7e1288d31bc6645f95d07bcf09caaf93210591ba082ba0f14490f0767ad7fd33/cipher.txt

https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher