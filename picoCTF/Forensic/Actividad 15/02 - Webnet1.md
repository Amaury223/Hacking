## Descripción
We found this [packet capture](https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/webnet1-capture.pcap) and [key](https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/picopico.key). Recover the flag.

Hints

1

Try using a tool like Wireshark.

2

How can you decrypt the TLS stream?
## Solución
```
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ 

wget https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/webnet1-capture.pcap

wget https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/picopico.key
--2026-11-20 03:04:36--  https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/webnet1-capture.pcap
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.26, 18.238.132.49, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘webnet1-capture.pcap’

webnet1-capture.pcap        100%[===========================================>]  90.36K  --.-KB/s    in 0.09s   

2026-11-20 03:04:36 (987 KB/s) - ‘webnet1-capture.pcap’ saved [92525/92525]

--2026-11-20 03:04:36--  https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/picopico.key
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.49, 18.238.132.26, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key.1’

picopico.key.1              100%[===========================================>]   1.66K  --.-KB/s    in 0s      

2026-11-20 03:04:37 (11.7 MB/s) - ‘picopico.key.1’ saved [1704/1704]

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wireshark webnet1-capture.pcap

academy{honey.roasted.peanuts}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/webnet1-capture.pcap

https://challenge-files.cylabacademy.net/library/afb7599dd63cad30a04eb98d0e4057608120371eb3e8943b632505e32c8b622c/picopico.key
