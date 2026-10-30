## Descripción
A message was encrypted using a shared secret... but it looks like one side of the exchange leaked something. Can you piece together the secret and get the flag? Download the [message](https://challenge-files.cylabacademy.net/library/229381d5dd0dd4fa9da2439cb70d3b5dd39bc39c605506118af8c135142fa9f3/message.txt). And source [code](https://challenge-files.cylabacademy.net/library/229381d5dd0dd4fa9da2439cb70d3b5dd39bc39c605506118af8c135142fa9f3/encryption.py)

Hints

1

What do you get if you combine a public key with a known private one?
## Solución
```
Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/229381d5dd0dd4fa9da2439cb70d3b5dd39bc39c605506118af8c135142fa9f3/message.txt -o message.txt

Dark23-academy@webshell:~$ curl -s https://challenge-files.cylabacademy.net/library/229381d5dd0dd4fa9da2439cb70d3b5dd39bc39c605506118af8c135142fa9f3/encryption.py -o encryption.py

Dark23-academy@webshell:~$ cat message.txt
g = 2
p = 2716364814884550237465696555767460559305292109414659314625633598209808946902955057986874285825211962030472778484595021898576015206041353395402903710135592347564814005251850437151022528759258562721609015607233879113800710584958913364070123689823797175552331226421723239425431018809618178946011898707090291352011196553
A = 1875807084116198824616668657798004707773600519641472313891196096327362508171339765723700836223532999998551325957351471365823095565057047826789177821436255218470435841164565457241657341782497997219091365061089727972177156197835055807742301826902043235491172826362189131517321797417259679333440516329947082931072946480
b = 786965768465176569266948096765850814795445726866810260933747441060425049138464682204892870080451660024166255735652749214414667929260785857508850632419694357752701996902341777129205037460209728285759562802514473257288502073534018499588334976702005797449942610445844263028043875662700401049071221221245404980737787575
enc = faf8fafffef6e2e0fff3c4e8a8f8e9a8efc4aeffa2f8a3fdf9fee6

Dark23-academy@webshell:~$ echo "---"
---

Dark23-academy@webshell:~$ cat encryption.py
import os
import sys

from Crypto.Util.number import getPrime
from random import randint

# Public parameters
g = 2
p = getPrime(1048)

# Server's secret
a = randint(2, p-2)
A = pow(g, a, p)

# Client secret
b = randint(2, p-2)

B = pow(g, b, p)

# Shared key
shared = pow(A, b, p)

# Encrypt flag
flag = b"academy{...}"
enc = bytes([x ^ (shared % 256) for x in flag])

# Write challenge info
#
# You were handed message.txt alongside this script, and this writes that same
# name. Running it here would overwrite the file you have to solve with a fresh
# transcript over the redacted flag above -- a different p and b, and nothing to
# recover. So refuse rather than clobber.
if os.path.exists("message.txt"):
    sys.exit("message.txt already exists here -- that is the file you were given, "
             "and running this would overwrite it. Move it aside first, or run "
             "this somewhere else.")

with open("message.txt", "w") as f:
    f.write(f"g = {g}\n")
    f.write(f"p = {p}\n")
    f.write(f"A = {A}\n")
    f.write(f"b = {b}\n")
    f.write(f"enc = {enc.hex()}\n")
    
    academy{dh_s3cr3t_5d9c8fbe}
    
```
## Notas Adicionales
**La vulnerabilidad (y el chiste del nombre “Shared Secrets”):** Este es un intercambio de claves tipo **Diffie-Hellman**, donde se supone que `a` y `b` (los secretos privados del servidor y del cliente) nunca deben revelarse — solo se comparten `A = g^a mod p` y `B = g^b mod p` públicamente.

Pero el código filtra **`b` directamente** en `message.txt` (se supone que era “el secreto del cliente”, ¡pero lo escribieron en el archivo de salida pública!). Con `A`, `b` y `p` ya podemos calcular directamente el secreto compartido sin necesitar resolver el logaritmo discreto:
## Referencias
https://challenge-files.cylabacademy.net/library/229381d5dd0dd4fa9da2439cb70d3b5dd39bc39c605506118af8c135142fa9f3/message.txt

https://challenge-files.cylabacademy.net/library/229381d5dd0dd4fa9da2439cb70d3b5dd39bc39c605506118af8c135142fa9f3/encryption.py