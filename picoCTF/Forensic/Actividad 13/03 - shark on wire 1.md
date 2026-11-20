## Descripción
We found this [packet capture](https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap). Recover the flag.

Hints

1

Try using a tool like Wireshark, What are streams?
## Solución
```
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap
--2026-11-20 00:45:13--  https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.26, 18.238.132.49, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘shark-on-wire-1-capture.pcap’

shark-on-wire-1-capture.pca 100%[===========================================>] 233.84K  --.-KB/s    in 0.1s    

2026-11-20 00:45:14 (1.71 MB/s) - ‘shark-on-wire-1-capture.pcap’ saved [239455/239455]

                                                                                                                
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
└─$ tshark -r shark-on-wire-1-capture.pcap | head
    1   0.000000  192.168.2.1 → 239.255.255.250 SSDP 216 M-SEARCH * HTTP/1.1 
    2   1.000498  192.168.2.1 → 239.255.255.250 SSDP 216 M-SEARCH * HTTP/1.1 
    3   2.001016  192.168.2.1 → 239.255.255.250 SSDP 216 M-SEARCH * HTTP/1.1 
    4   3.002419  192.168.2.1 → 239.255.255.250 SSDP 216 M-SEARCH * HTTP/1.1 
    5  14.589681  192.168.2.1 → 192.168.2.255 BROWSER 243 Local Master Announcement LAPTOP-HCSFMST7, Workstation, Server, NT Workstation, Potential Browser, Master Browser
    6  21.094272 fe80::8dd3:64c9:4ef3:82a3 → ff02::1:3    LLMNR 84 Standard query 0x724e A wpad
    7  21.094285  192.168.2.1 → 224.0.0.252  LLMNR 64 Standard query 0x724e A wpad
    8  21.506682 fe80::8dd3:64c9:4ef3:82a3 → ff02::1:3    LLMNR 84 Standard query 0x724e A wpad
    9  21.506697  192.168.2.1 → 224.0.0.252  LLMNR 64 Standard query 0x724e A wpad
   10  35.861119 VMware_b9:02:a9 → Broadcast    ARP 60 Who has 10.0.0.5? Tell 10.0.0.6
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ tshark -r shark-on-wire-1-capture.pcap -T fields -e udp.stream | sort -nu
0
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100
101
102
103
104
105
106
107
108
109
110
111
112
113
114
115
116
117
118
119
120
121
122
123
124
125
126
127
128
129
130
131
132
133
134
135
136
137
138
139
140
141
142
143
144
145
146
147
148
149
150
151
152
153
154
155
156
157
158
159
160
161
162
163
164
165
166
167
168
169
170
171
172
173
174
175
176
177
178
179
180
181
182
183
184
185
186
187
188
189
190
191
192
193
194
195
196
197
198
199
200
201
202
203
204
205
206
207
208
209
210
211
212
213
214
215
216
217
218
219
220
221
222
223
224
225
226
227
228
229
230
231
232
233
234
235
236
237
238
239
240
241
242
243
244
245
246
247
248
249
250
251
252
253
254
255
256
257
258
259
260
261
262
263
264
265
266
267
268
269
270
271
272
273
274
275
276
277
278
279
280
281
282
283
284
285
286
287
288
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ tshark -r shark-on-wire-1-capture.pcap -Y "udp.stream eq 6" -T fields -e data
61
63
61
64
65
6d
79
7b
53
74
61
54
33
31
33
35
35
5f
36
33
36
66
36
65
36
65
7d
                                                                                                                
┌──(kali㉿kali)-[~]
└─$ tshark -r shark-on-wire-1-capture.pcap -q -z follow,udp,ascii,6

===================================================================
Follow: udp,ascii
Filter: udp.stream eq 6
Node 0: 10.0.0.2:5000
Node 1: 10.0.0.12:8888
1
a
1
c
1
a
1
d
1
e
1
m
1
y
1
{
1
S
1
t
1
a
1
T
1
3
1
1
1
3
1
5
1
5
1
_
1
6
1
3
1
6
1
f
1
6
1
e
1
6
1
e
1
}
===================================================================
academy{StaT31355_636f6e6e}

```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap
