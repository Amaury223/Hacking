## Descripción
How about we take you on an adventure on exploring certificate signing requests Take a look at this CSR file [here](https://challenge-files.cylabacademy.net/library/936e82e74aef68c1a8fcc80b032ea33d65adda1f04b5c46085d44a5d6ff7cb71/readmycert.csr).

Hints

1

Download the certificate signing request and try to read it.
## Solución
```
Dark23-academy@webshell:~$ wget -O readmycert.csr "https://challenge-files.cylabacademy.net/library/936e82e74aef68c1a8fcc80b032ea33d65adda1f04b5c46085d44a5d6ff7cb71/readmycert.csr"

Dark23-academy@webshell:~$ openssl req -in readmycert.csr -noout -text
Certificate Request:
    Data:
        Version: 1 (0x0)
        Subject: CN = academy{read_mycert_dcfb9c76}, name = ctfPlayer
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:90:8e:93:0e:23:a5:97:5c:bb:75:ef:61:d6:6a:
                    4f:65:13:de:6d:01:21:dc:54:0f:b8:25:b9:96:9c:
                    b3:bd:8d:b9:d5:d3:c4:cf:62:31:73:bf:1c:a4:66:
                    e1:74:8a:6d:35:ef:a6:af:42:db:1e:8c:da:e3:0a:
                    d0:1c:d0:3f:c0:1f:35:1b:99:76:31:66:ef:e8:0f:
                    fe:58:42:a6:cc:1b:0f:e5:c8:9f:51:ba:2a:fa:cc:
                    81:1b:21:6d:ad:29:20:cf:f1:be:7e:11:7a:b3:22:
                    66:df:7d:d8:d7:c4:07:04:b1:b7:e5:77:9a:6f:10:
                    a2:f0:b4:24:7a:63:b7:48:10:09:a8:15:80:9b:20:
                    5d:5a:78:ce:6b:50:5a:a3:31:65:9c:ad:0d:e9:ce:
                    15:4d:b3:83:d5:38:7e:1c:16:06:d5:84:2c:2b:43:
                    19:98:be:c1:8e:d6:a6:17:47:34:47:1b:10:97:ea:
                    54:e9:b2:67:18:57:6c:f6:cc:6b:0a:3e:26:91:89:
                    6b:2b:16:ca:7d:6f:51:6f:52:0a:58:11:d5:07:48:
                    37:cf:fc:2d:1c:ba:18:04:71:f1:af:06:e9:24:f3:
                    c2:7e:b8:29:91:ec:6e:99:2e:4f:cb:af:bf:da:88:
                    02:5d:88:4a:f3:22:45:38:4f:7d:fa:6a:1c:68:86:
                    3e:3d
                Exponent: 65537 (0x10001)
        Attributes:
            Requested Extensions:
                X509v3 Extended Key Usage: 
                    TLS Web Client Authentication
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        21:15:bc:5b:d0:64:9c:1f:ec:75:83:7f:41:0c:27:51:d0:51:
        29:ba:b2:83:24:18:d7:3f:08:ef:99:c3:4e:1a:75:f9:3d:70:
        c9:8a:6c:07:3b:3d:1d:32:14:6d:c3:94:18:de:b0:97:7c:53:
        d4:fc:d8:51:82:58:da:1e:93:3d:4c:85:fe:45:8c:3a:49:ca:
        40:c8:11:d8:8f:20:70:c1:0d:d9:ae:14:de:ba:a0:ed:eb:e8:
        10:11:e0:f9:1c:50:ed:bd:bf:e3:8e:8d:62:c6:fd:48:6b:35:
        a1:8f:dc:4e:c9:9f:2d:d1:25:31:60:4f:0a:25:b3:2e:fe:f9:
        12:f7:ee:5d:8e:fe:17:f0:32:53:19:3c:4d:ec:e5:ff:be:de:
        29:4b:50:cf:f7:25:ce:fe:f6:5a:b3:93:7b:01:02:9f:d0:f5:
        d4:8f:79:61:cb:c9:c2:62:f2:ca:99:9f:9f:04:37:39:ca:07:
        59:c3:fc:e9:68:c9:d3:8e:f6:e2:75:b7:11:61:6c:c1:99:37:
        0e:6b:ff:54:66:10:ae:ef:9d:e7:df:3d:b9:fa:10:57:32:2a:
        bd:3e:ea:cb:79:6a:2c:4d:56:29:c6:31:52:a8:bb:18:7e:68:
        03:d5:f8:78:fa:e8:b8:e0:a8:11:a4:c7:07:a8:49:7d:a6:ee:
        8f:64:eb:66
        
        
academy{read_mycert_dcfb9c76}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/936e82e74aef68c1a8fcc80b032ea33d65adda1f04b5c46085d44a5d6ff7cb71/readmycert.csr