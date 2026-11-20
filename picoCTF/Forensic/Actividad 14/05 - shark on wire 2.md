## Descripción
We found this [packet capture](https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap). Recover the flag that was pilfered from the network.
## Solución
```
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap
--2026-11-20 01:25:02--  https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.26, 18.238.132.88, 18.238.132.115, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘shark-on-wire-2-capture.pcap’

shark-on-wire-2-capture.pca 100%[===========================================>] 109.69K  --.-KB/s    in 0.09s   

2026-11-20 01:25:02 (1.21 MB/s) - ‘shark-on-wire-2-capture.pcap’ saved [112318/112318]

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ tshark --version
TShark (Wireshark) 4.6.6.

Copyright 1998-2026 Gerald Combs <gerald@wireshark.org> and contributors.
Licensed under the terms of the GNU General Public License (version 2 or later).
This is free software; see the file named COPYING in the distribution. There is
NO WARRANTY; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

Compile-time info:
 Bit width: 64-bit
  Compiler: GCC 15.2.0
      GLib: 2.88.1
 With:
  +brotli                      +MaxMind
  +Gcrypt 1.12.2               +nghttp2 1.69.0
  +GnuTLS 3.8.13 and PKCS#11   +nghttp3 1.15.0
  +Kerberos (MIT)              +PCRE2 10.46 2025-08-27
  +libnl 3                     +POSIX capabilities (Linux)
  +libpcap                     +Snappy 1.2.2
  +libsmi 0.4.8                +xxhash 0.8.3
  +libxml2 2.15.2              +zlib 1.3.2
  +Lua 5.4.8                   +Zstandard 1.5.7
  +LZ4 1.10.0
 Without:
  -zlib-ng

Runtime info:
      OS: Linux 7.1.5+kali-amd64
     CPU: 13th Gen Intel(R) Core(TM) i5-13420H (with SSE4.2)
  Memory: 1968 MB of physical memory
    GLib: 2.88.3
  Locale: LC_TYPE=en_US.UTF-8
 Plugins: supported, 0 loaded
 With:
  +brotli 1.2.0
  +c-ares 1.34.8
  +Gcrypt 1.12.2
  +GnuTLS 3.8.13
  +libpcap 1.10.6 (64-bit time_t, with TPACKET_V3)
  +libsmi 0.4.8
  +LZ4 1.10.0
  +nghttp2 1.70.0
  +nghttp3 1.17.0
  +PCRE2 10.46 2025-08-27
  +xxhash 803
  +zlib 1.3.2
  +Zstandard 1.5.7
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ tshark -r shark-on-wire-2-capture.pcap -q -z io,phs

===================================================================
Protocol Hierarchy Statistics
Filter: 

frame                                    frames:1326 bytes:91078
  eth                                    frames:1326 bytes:91078
    ipv6                                 frames:22 bytes:3067
      udp                                frames:15 bytes:2457
        mdns                             frames:13 bytes:2267
        llmnr                            frames:2 bytes:190
      icmpv6                             frames:7 bytes:610
    ip                                   frames:743 bytes:54351
      udp                                frames:599 bytes:45573
        mdns                             frames:13 bytes:2007
        _ws.malformed                    frames:6 bytes:360
        data                             frames:537 bytes:34356
        ssdp                             frames:40 bytes:8640
        llmnr                            frames:2 bytes:150
        ntp                              frames:1 bytes:60
          _ws.malformed                  frames:1 bytes:60
      tcp                                frames:138 bytes:8418
      igmp                               frames:6 bytes:360
    arp                                  frames:560 bytes:33600
    lldp                                 frames:1 bytes:60
===================================================================
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ tshark -r shark-on-wire-2-capture.pcap -Y "udp" -T fields -e udp.srcport -e udp.dstport

┌──(kali㉿kali)-[~]
└─$ tshark -r shark-on-wire-2-capture.pcap -Y "udp.dstport == 22" -T fields -e udp.srcport


┌──(kali㉿kali)-[~]
└─$ nano resolver.py

from scapy.all import rdpcap, UDP

archivo = "shark-on-wire-2-capture.pcap"

paquetes = rdpcap(archivo)

bandera = ""

for paquete in paquetes:
    if UDP in paquete:
        udp = paquete[UDP]

        # Filtrar tráfico hacia el puerto 22
        if udp.dport == 22 and udp.sport > 5000:
            caracter = chr(udp.sport - 5000)
            bandera += caracter

print("[+] Mensaje recuperado:")
print(bandera)

                                                                                                                
┌──(kali㉿kali)-[~]
└─$ python3 resolver.py
[+] Mensaje recuperado:
academy{p1LLf3r3d_data_v1a_st3g0}
                                   
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/f76620763560ca0683be36e0ed4648743f969ab4d852fda0d8fb4d3ae21a173d/shark-on-wire-2-capture.pcap