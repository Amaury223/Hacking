
## Descripción
We have recovered a [binary](https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev) and a [text file](https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev_this). Can you reverse the flag.

Hints

1

objdump and Gihdra are some tools that could assist with this
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev
--2026-11-20 05:07:12--  https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.95, 3.160.5.18, 3.160.5.64, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16856 (16K) [application/octet-stream]
Saving to: 'rev'

rev                                                        100%[========================================================================================================================================>]  16.46K  --.-KB/s    in 0.006s  

2026-11-20 05:07:12 (2.61 MB/s) - 'rev' saved [16856/16856]

Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev_this
--2026-11-20 05:07:19--  https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev_this
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.40, 3.160.5.64, 3.160.5.18, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24 [application/octet-stream]
Saving to: 'rev_this'

rev_this                                                   100%[========================================================================================================================================>]      24  --.-KB/s    in 0s      

2026-11-20 05:07:19 (20.6 MB/s) - 'rev_this' saved [24/24]

Dark23-academy@webshell:~$ cat rev_this
academy{w1{1wq8684;3g5k}Dark23-academy@webshell:~$ file rev
rev: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=523d51973c11197605c76f84d4afb0fe9e59338c, not stripped
Dark23-academy@webshell:~$ strings rev
/lib64/ld-linux-x86-64.so.2
libc.so.6
exit
fopen
puts
fputc
fclose
fread
__cxa_finalize
__libc_start_main
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
u/UH
[]A\A]A^A_
flag.txt
rev_this
No flag found, please make sure this is run on the server
please run this on the server
;*3$"
GCC: (Debian 8.2.0-14) 8.2.0
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.7325
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
rev.c
__FRAME_END__
__init_array_end
_DYNAMIC
__init_array_start
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
puts@@GLIBC_2.2.5
fread@@GLIBC_2.2.5
_edata
fclose@@GLIBC_2.2.5
fputc@@GLIBC_2.2.5
__libc_start_main@@GLIBC_2.2.5
__data_start
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
fopen@@GLIBC_2.2.5
exit@@GLIBC_2.2.5
__TMC_END__
_ITM_registerTMCloneTable
__cxa_finalize@@GLIBC_2.2.5
.symtab
.strtab
.shstrtab
.interp
.note.ABI-tag
.note.gnu.build-id
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.got.plt
.data
.bss
.comment

Dark23-academy@webshell:~$ objdump -d -M intel rev | less

[1]+  Stopped                 objdump -d -M intel rev | less
Dark23-academy@webshell:~$ nano solve.py
with open("rev_this", "rb") as archivo:
    texto = bytearray(archivo.read())

# Los primeros 8 caracteres no cambian

# Descifrar los caracteres del índice 8 al 22
for i in range(8, 23):

    if i % 2 == 0:
        texto[i] -= 5

    else:
        texto[i] += 2

# Mostrar la bandera
print(texto.decode())
Dark23-academy@webshell:~$ python3 solve.py
academy{r3v3rs383665b7f}
Dark23-academy@webshell:~$ 
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev

https://challenge-files.cylabacademy.net/library/9e68aee0a9e7ba6d6eb5a562c7967f6d2c7cfc9179e9b0f5a75153c65c403198/rev_this
