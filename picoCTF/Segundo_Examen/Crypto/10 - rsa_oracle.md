## Descripción
Can you abuse the oracle?

An attacker was able to intercept communications between a bank and a fintech company. They managed to get the [message](https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/secret.enc) (ciphertext) and the [password](https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/password.enc) that was used to encrypt the message. After some intensive reconassainance they found out that the bank has an oracle that was used to encrypt the password and can be found here `nc chatelaine.cylabacademy.net 17340`. Decrypt the password and use it to decrypt the message. The oracle can decrypt anything except the password.

Instance

Expires in 14:48

Hints

1

Crytography Threat models: chosen plaintext attack.

2

OpenSSL can be used to decrypt the message. e.g `openssl enc -aes-256-cbc -d ...`

3

The key to getting the flag is by sending a custom message to the server by taking advantage of the RSA encryption algorithm.

4

Minimum requirements for a useful cryptosystem is CPA security.
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/secret.enc -o secret.enc
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/password.enc -o password.enc
Dark23-academy@webshell:~$ xxd password.enc | head -20
00000000: 3434 3238 3930 3035 3639 3231 3733 3233  4428900569217323
00000010: 3237 3836 3830 3739 3731 3732 3439 3630  2786807971724960
00000020: 3933 3732 3133 3834 3737 3536 3732 3937  9372138477567297
00000030: 3637 3936 3535 3337 3438 3432 3330 3731  6796553748423071
00000040: 3335 3838 3438 3332 3633 3032 3939 3133  3588483263029913
00000050: 3130 3935 3937 3831 3230 3431 3538 3934  1095978120415894
00000060: 3237 3532 3032 3731 3034 3539 3234 3937  2752027104592497
00000070: 3136 3231 3733 3232 3337 3932 3533 3438  1621732237925348
00000080: 3735 3037 3837 3438 3437 3435 3033 3234  7507874847450324
00000090: 3037 3037 3136 3530 3132                 0707165012
Dark23-academy@webshell:~$ echo "---"
---
Dark23-academy@webshell:~$ wc -c secret.enc password.enc
 64 secret.enc
154 password.enc
218 total
Dark23-academy@webshell:~$ echo "---"
---
Dark23-academy@webshell:~$ file secret.enc password.enc
secret.enc:   openssl enc'd data with salted password
password.enc: ASCII text, with no line terminators
Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 17340

Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 17340
*****************************************
****************THE ORACLE***************
*****************************************
what should we do for you? 
E --> encrypt D --> decrypt. 
D
Enter text to decrypt: 4707619883686427763240856106433203231481313994680729548861877810439954027216515481620077982254465432294427487895036699854948548980054737181231034760249505
decrypted ciphertext as hex (c ^ d mod n): 32
decrypted ciphertext: 2

what should we do for you? 
E --> encrypt D --> decrypt. 
^Z
[4]+  Stopped                 nc chatelaine.cylabacademy.net 17340
Dark23-academy@webshell:~$ wget "https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/password.enc"
--2026-10-30 09:11:18--  https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/password.enc
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 154 [application/octet-stream]
Saving to: 'password.enc.1'

password.enc.1                                             100%[========================================================================================================================================>]     154  --.-KB/s    in 0s      

2026-10-30 09:11:18 (5.83 MB/s) - 'password.enc.1' saved [154/154]

Dark23-academy@webshell:~$ wget "https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/secret.enc"
--2026-10-30 09:11:30--  https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/secret.enc
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.40, 3.160.5.64, 3.160.5.18, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 64 [application/octet-stream]
Saving to: 'secret.enc.1'

secret.enc.1                                               100%[========================================================================================================================================>]      64  --.-KB/s    in 0s      

2026-10-30 09:11:30 (345 KB/s) - 'secret.enc.1' saved [64/64]

Dark23-academy@webshell:~$ python3 - <<'PY'
> c = int(open("password.enc").read().strip())
> 
> c2 = 4707619883686427763240856106433203231481313994680729548861877810439954027216515481620077982254465432294427487895036699854948548980054737181231034760249505
> 
> print(c * c2)
> PY
20849580382517609126100472405446958727936236025461771075943446623897452341580567755624000390095145197689939529531811162052257564693673413188239224533728790199587644607936992816006104108196043352341824296335519544112681681748964732338200286122730954536275656549923938133144261644876164732844201900458326319060
Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 17340
*****************************************
****************THE ORACLE***************
*****************************************
what should we do for you? 
E --> encrypt D --> decrypt. 
D
Enter text to decrypt: 20849580382517609126100472405446958727936236025461771075943446623897452341580567755624000390095145197689939529531811162052257564693673413188239224533728790199587644607936992816006104108196043352341824296335519544112681681748964732338200286122730954536275656549923938133144261644876164732844201900458326319060
decrypted ciphertext as hex (c ^ d mod n): afb02fb9bc4
decrypted ciphertext: 
ûû

what should we do for you? 
E --> encrypt D --> decrypt. 
^Z
[5]+  Stopped                 nc chatelaine.cylabacademy.net 17340
Dark23-academy@webshell:~$ python3 - <<'PY'
> h = "afb02fb9bc4"
> m = int(h, 16) // 50
> password = bytes.fromhex(format(m, 'x')).decode()
> print("PASSWORD:", password)
> PY
PASSWORD: 88a12
Dark23-academy@webshell:~$ openssl enc -aes-256-cbc -d -in secret.enc -out secret.txt -pass pass:88a12
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
Dark23-academy@webshell:~$ cat secret.txt
academy{su((3ss_(r@ck1ng_r3@_88a127f1}
```
## Notas Adicionales
Este reto utiliza una vulnerabilidad conocida de RSA llamada RSA multiplicative blinding (cegado multiplicativo).

La idea es recuperar la contraseña sin pedirle al oráculo que descifre directamente `password.enc`, porque el servidor bloquea ese ciphertext.

En lugar de eso, modificamos matemáticamente el ciphertext:

\[ c' = c \cdot r^e \pmod n \]

El oráculo descifra \(c'\) y nos devuelve un resultado relacionado con la contraseña original. Después usamos el inverso modular de \(r\) para recuperar el mensaje original.

No necesitas conocer la clave privada RSA.
## Referencias
https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/secret.enc

https://challenge-files.cylabacademy.net/library/c160444b2e2c0d9b093294670f0feec4d0e65abfcfc56e9524fb337c65cb9110/password.enc
nc chatelaine.cylabacademy.net 17340