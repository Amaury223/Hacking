## Descripción
Can you make sense of this file?

Download the file [here](https://artifacts.picoctf.net/c/474/enc_flag).

Multiple decoding is always good.
## Solución
```
wget https://challenge-files.cylabacademy.net/library/4341c214a057d1b6f5e849c64611635897ab3e8d0225540cecd8adc28541d295/enc_flag

Dark23-academy@webshell:~$ ls
enc_flag  files  files.zip
Dark23-academy@webshell:~$ file enc_flag 
enc_flag: ASCII text
Dark23-academy@webshell:~$ cat enc_flag 
Vm1wR1lXRXhVWGxTYTJScVVsZG9XRmx0ZUV0ak1WbDNZVVpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbGhhTTBKeldXeFZkMlF4V2tkV2JFNXBDazFyV2xoWk1HaFRWMGRHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==


academy{base64_n3st3d_dic0d!n8_d0wnl04d3d_c7808bff}
```
## Notas Adicionales
base 64 anidados, usando cybercheff anide 6 conversores de base 64 al texto del archivo y asi obtuve la respuesta.
## Referencias
[From Base64, 5 more - CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64\('A-Za-z0-9%2B/%3D',true,false\)From_Base64\('A-Za-z0-9%2B/%3D',true,false\)From_Base64\('A-Za-z0-9%2B/%3D',true,false\)From_Base64\('A-Za-z0-9%2B/%3D',true,false\)From_Base64\('A-Za-z0-9%2B/%3D',true,false\)From_Base64\('A-Za-z0-9%2B/%3D',true,false\)&input=Vm1wR1UxRXlSWGxVV0d4VFlteEtWVll3WkZOV2JHeHlWMjFHVjFKdGVEQlViRnBQWVd4S2RGVnNhRnBXVmxVeFdWWmFTMVpXV25WaA0KUm1SWFpXdGFiMWRXV210U01rNXlUbFpXV0FwaVZWcFVWbTEwZDFWV1pGZFZhMlJwWWxaYVdGWnROVmRWWjNCcFUwVktlbGRXVWtOaw0KTWxaWFZsaG9XR0pZUWs5VmJGSlhVMFprY1ZSdVRsZGFNMEpaVldwR1MyVldXa2RhU0dSWENrMXNXbnBXVjNoaFZtMUtSazVYT1ZWVw0KVmtwRVZHeGFZVmRGTVZoU2JGWmhUVEJLVUZkWGRHdGxiVkY0VjJ0a1dHSllVbGxEYlVZMlVXcFNXbUV5YUZSV2FrcEhaRWRXUmxacw0KYUdrS1lsUnJlbFpFUmxkVU1rcHpVV3hXVGxKWVRreERaejA5Q2c9PQ&ieol=CRLF)