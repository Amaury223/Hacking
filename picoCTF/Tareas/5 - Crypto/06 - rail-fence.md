## Descripción
A type of transposition cipher is the rail fence cipher, which is described [here](https://en.wikipedia.org/wiki/Rail_fence_cipher). Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it? Download the message [here](https://challenge-files.cylabacademy.net/library/54f070d7a4fbb401b7ae06e5f41a3071cc195039368a58d9c6bb6f5a95b7913c/message.txt).

The decoded message names a phrase. Put that phrase, and nothing else, in the academy flag format: `academy{phrase}`.
## Solución
```
Dark23-academy@webshell:~$ wget -O message.txt "https://challenge-files.cylabacademy.net/library/54f070d7a4fbb401b7ae06e5f41a3071cc195039368a58d9c6bb6f5a95b7913c/message.txt"

Dark23-academy@webshell:~$ cat message.txt
Ta _7N6D86hlg:W3D_H3C31N__C16ef sHR053F38N43DE1 i33___NFDark23-academy@webshell:~$ 
Dark23-academy@webshell:~$ cat > rail_fence.py << 'EOF'
> def decode_rail_fence(cipher, rails):
>     # Crear patrón zigzag de índices de rieles
>     pattern = list(range(rails)) + list(range(rails - 2, 0, -1))
>     if not pattern:
>         pattern = [0]
>     n = len(cipher)
>     rail_idx = [pattern[i % len(pattern)] for i in range(n)]
> 
>     # Contar cuántos caracteres van en cada riel
>     counts = [rail_idx.count(r) for r in range(rails)]
> 
>     # Dividir el cifrado en bloques según los counts, en orden de riel
>     rail_chars = []
>     pos = 0
>     for c in counts:
>         rail_chars.append(list(cipher[pos:pos+c]))
>         pos += c
> 
>     # Reconstruir el mensaje siguiendo el patrón zigzag
>     result = []
>     rail_pointers = [0] * rails
>     for r in rail_idx:
>         result.append(rail_chars[r][rail_pointers[r]])
>         rail_pointers[r] += 1
> 
>     return "".join(result)
> 
> with open("message.txt") as f:
>     cipher = f.read().strip()
> 
> plain = decode_rail_fence(cipher, 4)
> print("Mensaje:", plain)
> EOF
Dark23-academy@webshell:~$ python3 rail_fence.py
Mensaje: The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_8CEF1166

academy{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_8CEF1166}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/54f070d7a4fbb401b7ae06e5f41a3071cc195039368a58d9c6bb6f5a95b7913c/message.txt