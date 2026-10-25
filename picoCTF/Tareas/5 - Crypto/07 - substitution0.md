## Descripción
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher? Download the message [here](https://challenge-files.cylabacademy.net/library/0a2e91276318c0f6d400f5096fdaf87fcf57f37ebabf90004552502979a581c8/message.txt).
## Solución
```
Dark23-academy@webshell:~$ wget -O message.txt "https://challenge-files.cylabacademy.net/library/0a2e91276318c0f6d400f5096fdaf87fcf57f37ebabf90004552502979a581c8/message.txt"

Dark23-academy@webshell:~$ cat message.txt
HRZUEVABDLIOJYTGNXCMWPKSQF 

Bexewgty Oeaxhyu hxtce, kdmb h axhpe hyu cmhmeoq hdx, hyu rxtwabm je mbe reemoe
vxtj h aohcc zhce dy kbdzb dm khc eyzotceu. Dm khc h rehwmdvwo czhxhrhewc, hyu, hm
mbhm mdje, wyiytky mt yhmwxhodcmc—tv ztwxce h axehm gxdfe dy h czdeymdvdz gtdym
tv pdek. Mbexe kexe mkt xtwyu rohzi cgtmc yehx tye esmxejdmq tv mbe rhzi, hyu h
otya tye yehx mbe tmbex. Mbe czhoec kexe eszeeudyaoq bhxu hyu aotccq, kdmb hoo mbe
hggehxhyze tv rwxydcbeu atou. Mbe kedabm tv mbe dycezm khc pexq xejhxihroe, hyu,
mhidya hoo mbdyac dymt ztycduexhmdty, D ztwou bhxuoq rohje Lwgdmex vtx bdc tgdydty
xecgezmdya dm.

Mbe voha dc: hzhuejq{5WR5717W710Y_3P0OW710Y_4VRU1ER7}


Dark23-academy@webshell:~$ cat > solve.py << 'EOF'
> import string
> 
> with open("message.txt") as f:
>     raw_lines = f.read().split("\n")
> 
> # Quita líneas vacías solo al identificar la key; luego usa TODO el resto del archivo
> non_empty = [l for l in raw_lines if l.strip() != ""]
> key = non_empty[0].strip().lower()
> 
> # El resto del texto (todo después de la primera línea), preservando saltos de línea
> rest_start = raw_lines.index(non_empty[0]) + 1
> ciphertext = "\n".join(raw_lines[rest_start:])
> 
> alphabet = string.ascii_lowercase
> decrypt_map = {k: p for k, p in zip(key, alphabet)}
> 
> def decrypt(text):
>     result = []
>     for ch in text:
>         if ch.lower() in decrypt_map:
>             d = decrypt_map[ch.lower()]
>             result.append(d.upper() if ch.isupper() else d)
>         else:
>             result.append(ch)
>     return "".join(result)
> 
> print(decrypt(ciphertext))
> EOF
> 
Dark23-academy@webshell:~$ python3 solve.py

Hereupon Legrand arose, with a grave and stately air, and brought me the beetle
from a glass case in which it was enclosed. It was a beautiful scarabaeus, and, at
that time, unknown to naturalists—of course a great prize in a scientific point
of view. There were two round black spots near one extremity of the back, and a
long one near the other. The scales were exceedingly hard and glossy, with all the
appearance of burnished gold. The weight of the insect was very remarkable, and,
taking all things into consideration, I could hardly blame Jupiter for his opinion
respecting it.

The flag is: academy{5UB5717U710N_3V0LU710N_4FBD1EB7}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/0a2e91276318c0f6d400f5096fdaf87fcf57f37ebabf90004552502979a581c8/message.txt