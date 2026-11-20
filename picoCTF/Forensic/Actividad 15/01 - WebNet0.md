## Descripción
We found this [packet capture](https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/webnet0-capture.pcap) and [key](https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/picopico.key). Recover the flag.

Hints

1

Try using a tool like Wireshark.

2

How can you decrypt the TLS stream?
## Solución
```
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/webnet0-capture.pcap

wget https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/picopico.key
--2026-11-20 02:55:42--  https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/webnet0-capture.pcap
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.115, 18.238.132.88, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13163 (13K) [application/octet-stream]
Saving to: ‘webnet0-capture.pcap’

webnet0-capture.pcap        100%[===========================================>]  12.85K  --.-KB/s    in 0s      

2026-11-20 02:55:43 (125 MB/s) - ‘webnet0-capture.pcap’ saved [13163/13163]

--2026-11-20 02:55:43--  https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/picopico.key
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.49, 18.238.132.88, 18.238.132.115, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key                100%[===========================================>]   1.66K  --.-KB/s    in 0s      

2026-11-20 02:55:43 (22.7 MB/s) - ‘picopico.key’ saved [1704/1704]



academy{nongshim.shrimp.crackers}

```

![[Pasted image 20261120020302.png]]
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/webnet0-capture.pcap

https://challenge-files.cylabacademy.net/library/2d15538465c5948f0f0626d0cdd271f74363c00aa99d694730fe98331946ab88/picopico.key