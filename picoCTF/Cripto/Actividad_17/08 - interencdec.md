## Descripción
Can you get the real meaning from this file.

Download the file [here](https://challenge-files.cylabacademy.net/library/b3f59d53f35ecfe9653969976a94f04fefc2a728e1974b51063c9db793731fcd/enc_flag).

Hints

1

Engaging in various decoding processes is of utmost importance

## Solución
```
Dark23-academy@webshell:~$ wget -O enc_flag "https://challenge-files.cylabacademy.net/library/b3f59d53f35ecfe9653969976a94f04fefc2a728e1974b51063c9db793731fcd/enc_flag"
--2026-11-20 21:50:08--  https://challenge-files.cylabacademy.net/library/b3f59d53f35ecfe9653969976a94f04fefc2a728e1974b51063c9db793731fcd/enc_flag
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.64, 3.160.5.95, 3.160.5.18, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag       0%       0  --.-KB/s  enc_flag     100%      73  --.-KB/s    in 0s      

2026-11-20 21:50:08 (4.47 MB/s) - 'enc_flag' saved [73/73]

Dark23-academy@webshell:~$ cat enc_flag
YidhR3BvYTJ4MFpudHFhR3g2YUhsZmF6TnFlVGwzWVROclh6azVORGhyYldneWZRPT0nCg==
Dark23-academy@webshell:~$ base64 -d enc_flag
b'aGpoa2x0ZntqaGx6aHlfazNqeTl3YTNrXzk5NDhrbWgyfQ=='
Dark23-academy@webshell:~$ base64 -d enc_flag | cut -d "'" -f2 | base64 -d
hjhkltf{jhlzhy_k3jy9wa3k_9948kmh2}
Dark23-academy@webshell:~$

-----------------------------
python3 - <<'PY'
texto = "hjhkltf{jhlzhy_k3jy9wa3k_9948kmh2}"

for c in texto:
    if c.isalpha():
        print(chr((ord(c) - ord('a') + 19) % 26 + ord('a')), end='')
    else:
        print(c, end='')
print()
PY
----------------------------------------
academy{caesar_d3cr9pt3d_9948dfa2}
```

## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/b3f59d53f35ecfe9653969976a94f04fefc2a728e1974b51063c9db793731fcd/enc_flag
