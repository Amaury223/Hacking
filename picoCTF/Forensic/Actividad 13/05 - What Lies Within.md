## Descripción
There's something in the [building](https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png). Can you retrieve the flag?

Hints

1

There is data encoded somewhere... there might be an online decoder.
## Solución
```
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png
--2026-11-20 00:52:35--  https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.88, 18.238.132.49, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 615860 (601K) [application/octet-stream]
Saving to: ‘buildings.png.1’

buildings.png.1             100%[===========================================>] 601.43K  3.14MB/s    in 0.2s    

2026-11-20 00:52:36 (3.14 MB/s) - ‘buildings.png.1’ saved [615860/615860]


┌──(kali㉿kali)-[~]
└─$ gem install zsteg     
Defaulting to user installation because default installation directory (/var/lib/gems/3.3.0) is not writable.
WARNING:  You don't have /home/kali/.local/share/gem/ruby/3.3.0/bin in your PATH,
          gem executables (zsteg, zsteg-mask, zsteg-reflow) will not run.
Successfully installed zsteg-0.2.14
Parsing documentation for zsteg-0.2.14
Done installing documentation for zsteg after 0 seconds
1 gem installed
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ zsteg -a buildings.png
zsteg: command not found
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ export PATH="$HOME/.local/share/gem/ruby/3.3.0/bin:$PATH"


┌──(kali㉿kali)-[~]
└─$ zsteg -a buildings.png                                   
b1,rgb,lsb,xy       .. text: "academy{h1d1ng_1n_th3_b1t5}"

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png
