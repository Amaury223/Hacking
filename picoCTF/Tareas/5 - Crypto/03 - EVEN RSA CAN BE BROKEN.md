## Descripción
This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat:

`$ nc chatelaine.cylabacademy.net 41174`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/8d8b38c88a9606bca290997e6dc1bd9205ebc794cf16c913a56b487dbf220849/encrypt.py).
## Solución
```
Dark23-academy@webshell:~$ wget -O encrypt.py "https://challenge-files.cylabacademy.net/library/8d8b38c88a9606bca290997e6dc1bd9205ebc794cf16c913a56b487dbf220849/encrypt.py"


Dark23-academy@webshell:~$ cat encrypt.py
from sys import exit
from Crypto.Util.number import bytes_to_long, inverse
from setup import get_primes

e = 65537

def gen_key(k):
    """
    Generates RSA key with k bits
    """
    p,q = get_primes(k//2)
    N = p*q
    d = inverse(e, (p-1)*(q-1))

    return ((N,e), d)

def encrypt(pubkey, m):
    N,e = pubkey
    return pow(bytes_to_long(m.encode('utf-8')), e, N)

def main(flag):
    pubkey, _privkey = gen_key(1024)
    encrypted = encrypt(pubkey, flag) 
    return (pubkey[0], encrypted)

if __name__ == "__main__":
    flag = open('flag.txt', 'r').read()
    flag = flag.strip()
    N, cypher  = main(flag)
    print("N:", N)
    print("e:", e)
    print("cyphertext:", cypher)
    exit()


Dark23-academy@webshell:~$ nc chatelaine.cylabacademy.net 41174
N: 23280029927918763655802993711669783708667964825276913593374324278735770948507700089773957819857814301849299464033896427050715362049316996619868223640752826
e: 65537
cyphertext: 4167885127662477221185585081646825751703632864909712145809648975569132608208512626429214414723693385042143081502664386305687616718105340241180571820407697


Dark23-academy@webshell:~$ cat > solve.py << 'EOF'
> from Crypto.Util.number import inverse, long_to_bytes
> 
> N = 23280029927918763655802993711669783708667964825276913593374324278735770948507700089773957819857814301849299464033896427050715362049316996619868223640752826
> e = 65537
> c = 4167885127662477221185585081646825751703632864909712145809648975569132608208512626429214414723693385042143081502664386305687616718105340241180571820407697
> 
> p = 2
> q = N // p
> assert p * q == N
> phi = (p - 1) * (q - 1)
> d = inverse(e, phi)
> m = pow(c, d, N)
> print(long_to_bytes(m).decode(errors="ignore"))
> EOF
> 
> 
Dark23-academy@webshell:~$ python3 solve.py
academy{tw0_1$_pr!m3cfb893a9}
```
## Notas Adicionales
## Referencias
`$ nc chatelaine.cylabacademy.net 41174`

https://challenge-files.cylabacademy.net/library/8d8b38c88a9606bca290997e6dc1bd9205ebc794cf16c913a56b487dbf220849/encrypt.py


