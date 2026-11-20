## Descripción
Decrypt this message. Message: [message](https://challenge-files.cylabacademy.net/library/297f472a962ab45ee79af5ff4d616ba5206c85d5f4f5cfd41109602354d4121a/data.enc)

Hints

1

Caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/297f472a962ab45ee79af5ff4d616ba5206c85d5f4f5cfd41109602354d4121a/data.enc
--2026-11-20 21:13:47--  https://challenge-files.cylabacademy.net/library/297f472a962ab45ee79af5ff4d616ba5206c85d5f4f5cfd41109602354d4121a/data.enc
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.40, 3.160.5.64, 3.160.5.18, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 36 [application/octet-stream]
Saving to: 'data.enc'

data.enc       0%       0  --.-KB/s  data.enc     100%      36  --.-KB/s    in 0s      

2026-11-20 21:13:47 (2.40 MB/s) - 'data.enc' saved [36/36]

Dark23-academy@webshell:~$ cat data.enc
academy{xmjnndiboczmpwdxjizaukqzbt}

Dark23-academy@webshell:~$ nano resolver.py
Dark23-academy@webshell:~$ python3 resolver.py
0 academy{xmjnndiboczmpwdxjizaukqzbt}
1 zbzcdlx{wlimmchanbylovcwihyztjpyas}
2 yaybckw{vkhllbgzmaxknubvhgxysioxzr}
3 xzxabjv{ujgkkafylzwjmtaugfwxrhnwyq}
4 wywzaiu{tifjjzexkyvilsztfevwqgmvxp}
5 vxvyzht{sheiiydwjxuhkryseduvpfluwo}
6 uwuxygs{rgdhhxcviwtgjqxrdctuoektvn}
7 tvtwxfr{qfcggwbuhvsfipwqcbstndjsum}
8 susvweq{pebffvatgurehovpbarsmcirtl}
9 rtruvdp{odaeeuzsftqdgnuoazqrlbhqsk}
10 qsqtuco{nczddtyrespcfmtnzypqkagprj}
11 prpstbn{mbyccsxqdrobelsmyxopjzfoqi}
12 oqorsam{laxbbrwpcqnadkrlxwnoiyenph}
13 npnqrzl{kzwaaqvobpmzcjqkwvmnhxdmog}
14 mompqyk{jyvzzpunaolybipjvulmgwclnf}
15 lnlopxj{ixuyyotmznkxahoiutklfvbkme}
16 kmknowi{hwtxxnslymjwzgnhtsjkeuajld}
17 jljmnvh{gvswwmrkxlivyfmgsrijdtzikc}
18 ikilmug{furvvlqjwkhuxelfrqhicsyhjb}
19 hjhkltf{etquukpivjgtwdkeqpghbrxgia}
20 gigjkse{dspttjohuifsvcjdpofgaqwfhz}
21 fhfijrd{crossingtherubiconefzpvegy}
22 egehiqc{bqnrrhmfsgdqtahbnmdeyoudfx}
23 dfdghpb{apmqqglerfcpszgamlcdxntcew}
24 cecfgoa{zolppfkdqeboryfzlkbcwmsbdv}
25 bdbefnz{ynkooejcpdanqxeykjabvlracu}
```

academy{crossingtherubiconefzpvegy}
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/297f472a962ab45ee79af5ff4d616ba5206c85d5f4f5cfd41109602354d4121a/data.enc

https://learncryptography.com/classical-encryption/caesar-cipher