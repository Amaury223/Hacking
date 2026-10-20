## Descripción
In RSA, a small ee value can be problematic, but what about NN? Can you decrypt this? [values](https://challenge-files.cylabacademy.net/library/4a3b1aca528881eece43ed483e527d3700c5e388eb5ab2291015dbd67a809f31/values)
## Solución
```

┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/4a3b1aca528881eece43ed483e527d3700c5e388eb5ab2291015dbd67a809f31/values
--2026-10-19 12:44:15--  https://challenge-files.cylabacademy.net/library/4a3b1aca528881eece43ed483e527d3700c5e388eb5ab2291015dbd67a809f31/values
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.66, 13.226.187.37, 13.226.187.22, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 207 [application/octet-stream]
Saving to: ‘values’

values                                                     100%[=======================================================================================================================================>]     207  --.-KB/s    in 0s      

2026-10-19 12:44:17 (617 MB/s) - ‘values’ saved [207/207]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ ls
values
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ cat values 
Decrypt my super sick RSA:
c: 717608817902276639011922897702552744324264244069272484013719744328086856277690292
n: 1368992139315019955067447961537607041364451719382349005056752379702694554965203011
e: 65537
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~]
└─$ python3 - <<'PY'
import re
from pathlib import Path

data = Path('values').read_text()
v = {
    name: int(re.search(rf'^{name}:\s*(\d+)', data, re.M).group(1))
    for name in ('c', 'n', 'e')
}
c, n, e = (v[name] for name in ('c', 'n', 'e'))

p = 2074606527507983503944226222695401999839
q = 659880377875535146491994798968813949893149
assert p * q == n

phi = (p - 1) * (q - 1)
d = pow(e, -1, phi)
m = pow(c, d, n)
assert pow(m, e, n) == c

raw = m.to_bytes((m.bit_length() + 7) // 8, 'big')
print('Bytes descifrados:', raw)
print('Bandera:', raw[::-1].decode().strip())
PY
Bytes descifrados: b'\n}2517ca3a_do0g_0n_N_11ams{ymedaca'
Bandera: academy{sma11_N_n0_g0od_a3ac7152}



academy{sma11_N_n0_g0od_a3ac7152}
```
## Notas Adicionales
## Referencias
