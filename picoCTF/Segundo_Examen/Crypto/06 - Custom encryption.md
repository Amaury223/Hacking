## Descripción
Can you get sense of this code file and write the function that will decode the given encrypted file content.

Find the encrypted file here [flag_info](https://challenge-files.cylabacademy.net/library/98cdf4861b6c249cc4b06324768d9fbe57cc1cd8512fce4d03595601f380fc0f/enc_flag) and [code file](https://challenge-files.cylabacademy.net/library/98cdf4861b6c249cc4b06324768d9fbe57cc1cd8512fce4d03595601f380fc0f/custom_encryption.py) might be good to analyze and get the flag.

Hints

1

Understanding encryption algorithm to come up with decryption algorithm.
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/98cdf4861b6c249cc4b06324768d9fbe57cc1cd8512fce4d03595601f380fc0f/enc_flag -o enc_flag

Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/98cdf4861b6c249cc4b06324768d9fbe57cc1cd8512fce4d03595601f380fc0f/custom_encryption.py -o custom_encryption.py

Dark23-academy@webshell:~$ cat custom_encryption.py
from random import randint
import sys


def generator(g, x, p):
    return pow(g, x) % p


def encrypt(plaintext, key):
    cipher = []
    for char in plaintext:
        cipher.append(((ord(char) * key*311)))
    return cipher


def is_prime(p):
    v = 0
    for i in range(2, p + 1):
        if p % i == 0:
            v = v + 1
    if v > 1:
        return False
    else:
        return True


def dynamic_xor_encrypt(plaintext, text_key):
    cipher_text = ""
    key_length = len(text_key)
    for i, char in enumerate(plaintext[::-1]):
        key_char = text_key[i % key_length]
        encrypted_char = chr(ord(char) ^ ord(key_char))
        cipher_text += encrypted_char
    return cipher_text


def test(plain_text, text_key):
    p = 97
    g = 31
    if not is_prime(p) and not is_prime(g):
        print("Enter prime numbers")
        return
    a = randint(p-10, p)
    b = randint(g-10, g)
    print(f"a = {a}")
    print(f"b = {b}")
    u = generator(g, a, p)
    v = generator(g, b, p)
    key = generator(v, a, p)
    b_key = generator(u, b, p)
    shared_key = None
    if key == b_key:
        shared_key = key
    else:
        print("Invalid key")
        return
    semi_cipher = dynamic_xor_encrypt(plain_text, text_key)
    cipher = encrypt(semi_cipher, shared_key)
    print(f'cipher is: {cipher}')


if __name__ == "__main__":
    message = sys.argv[1]
    test(message, "trudeau")
    
Dark23-academy@webshell:~$ echo "---"
---

Dark23-academy@webshell:~$ xxd enc_flag | head -20
00000000: 6120 3d20 3934 0a62 203d 2032 320a 6369  a = 94.b = 22.ci
00000010: 7068 6572 2069 733a 205b 3232 3637 3139  pher is: [226719
00000020: 2c20 3136 3837 3739 372c 2031 3633 3734  , 1687797, 16374
00000030: 3135 2c20 3530 3338 322c 2032 3531 3931  15, 50382, 25191
00000040: 2c20 3130 3037 3634 2c20 3137 3633 3337  , 100764, 176337
00000050: 302c 2031 3731 3239 3838 2c20 3136 3132  0, 1712988, 1612
00000060: 3232 342c 2031 3035 3830 3232 2c20 302c  224, 1058022, 0,
00000070: 2032 3039 3038 3533 2c20 3532 3930 3131   2090853, 529011
00000080: 2c20 3132 3539 3535 2c20 3137 3132 3938  , 125955, 171298
00000090: 382c 2030 2c20 3535 3432 3032 2c20 3231  8, 0, 554202, 21
000000a0: 3636 3432 362c 2032 3531 3931 2c20 3135  66426, 25191, 15
000000b0: 3631 3834 322c 2036 3034 3538 342c 2036  61842, 604584, 6
000000c0: 3830 3135 372c 2031 3531 3134 362c 2031  80157, 151146, 1
000000d0: 3531 3134 362c 2034 3238 3234 372c 2031  51146, 428247, 1
000000e0: 3531 3134 362c 2036 3534 3936 362c 2033  51146, 654966, 3
000000f0: 3032 3239 322c 2036 3239 3737 352c 2035  02292, 629775, 5
00000100: 3739 3339 332c 2034 3238 3234 372c 2031  79393, 428247, 1
00000110: 3235 3935 352c 2031 3531 3134 362c 2030  25955, 151146, 0
00000120: 5d0a      
                               ].
Dark23-academy@webshell:~$ echo "---"
---

Dark23-academy@webshell:~$ file enc_flag
enc_flag: ASCII text

Dark23-academy@webshell:~$ wc -c enc_flag
290 enc_flag

academy{custom_d2cr0pt6d_203edf41}
```
## Notas Adicionales
1. Recalcular el `shared_key` con Diffie-Hellman (p=97, g=31, a=94, b=22)
2. Deshacer `encrypt()`: dividir cada número entre `shared_key * 311` para recuperar los códigos ASCII
3. Deshacer `dynamic_xor_encrypt()`: aplicar XOR con la clave `"trudeau"` y luego **invertir el string** (porque la función original itera sobre el texto invertido)
## Referencias

https://challenge-files.cylabacademy.net/library/98cdf4861b6c249cc4b06324768d9fbe57cc1cd8512fce4d03595601f380fc0f/enc_flag

https://challenge-files.cylabacademy.net/library/98cdf4861b6c249cc4b06324768d9fbe57cc1cd8512fce4d03595601f380fc0f/custom_encryption.py