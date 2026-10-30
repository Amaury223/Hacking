## Descripción
Someone encrypted a message using AES in ECB mode but they weren’t very careful with their key. Turns out it’s derived from something as simple as the current time! Can you uncover the key and decrypt the flag? Download the encrypted message: [message](https://challenge-files.cylabacademy.net/library/731fb526dfe57435a962b03ac42b15e329870c962f9f2311437d83d4c96448e8/message.txt)  
You may also find the encryption script helpful: [code](https://challenge-files.cylabacademy.net/library/731fb526dfe57435a962b03ac42b15e329870c962f9f2311437d83d4c96448e8/encryption.py)

Hints

1

`encryption.py` is a redacted example of the program
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/731fb526dfe57435a962b03ac42b15e329870c962f9f2311437d83d4c96448e8/message.txt -o message.txt

Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/731fb526dfe57435a962b03ac42b15e329870c962f9f2311437d83d4c96448e8/encryption.py -o encryption.py

Dark23-academy@webshell:~$ cat message.txt
Hint: The encryption was done around 1790147510 UTC
Ciphertext (hex): f4de02cdd646ec8434da64338ea3088b19782037a143d83710869e38ec9f690e

Dark23-academy@webshell:~$ echo "---"
---

Dark23-academy@webshell:~$ cat encryption.py
from hashlib import sha256
import time
from Crypto.Cipher import AES
from Crypto.Util.Padding import pad

def encrypt(plaintext: str, timestamp: int) -> str:
    timestamp = int(time.time())
    key = sha256(str(timestamp).encode()).digest()[:16]
    cipher = AES.new(key, AES.MODE_ECB)
    padded = pad(plaintext.encode(), AES.block_size)
    ciphertext = cipher.encrypt(padded)
    return ciphertext.hex()

if __name__ == "__main__":
  
    plaintext = "academy{...}"
    result = encrypt(plaintext, key)
    print(f"Hint: The encryption was done around {timestamp} UTC\n")
    print(f"Ciphertext (hex): {ciphertext.hex()}\n")
    
    
    academy{sa3S_sEc9t_57326579}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/731fb526dfe57435a962b03ac42b15e329870c962f9f2311437d83d4c96448e8/message.txt

https://challenge-files.cylabacademy.net/library/731fb526dfe57435a962b03ac42b15e329870c962f9f2311437d83d4c96448e8/encryption.py