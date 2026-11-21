## Descripción
How to automate tasks to run at intervals on linux servers? Use ssh to connect to this server:

```
Server: xebec.cylabacademy.net
Port: 39603
Username: picoplayer 
Password: 51XZIFfAcV
```

## Solución
```
Dark23-academy@webshell:~$ ssh -p 39603 picoplayer@xebec.cylabacademy.net
The authenticity of host '[xebec.cylabacademy.net]:39603 ([77.113.98.131]:39603)' can't be established.
ED25519 key fingerprint is SHA256:QuJB8WE/XfIZWwKHMLbqbyAjQ4Ds/Ulok523zsjElx0.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[xebec.cylabacademy.net]:39603' (ED25519) to the list of known hosts.
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

picoplayer@challenge:~$ crontab -l
no crontab for picoplayer
picoplayer@challenge:~$ ls -la /etc/cron*
-rw-r--r-- 1 root root 43 Sep 23 04:46 /etc/crontab

/etc/cron.d:
total 8
drwxr-xr-x 1 root root  26 Sep 23 04:46 .
drwxr-xr-x 1 root root  66 Nov 20 23:43 ..
-rw-r--r-- 1 root root 102 Mar 31  2024 .placeholder
-rw-r--r-- 1 root root 201 Apr  8  2024 e2scrub_all

/etc/cron.daily:
total 12
drwxr-xr-x 1 root root   26 Sep 23 04:46 .
drwxr-xr-x 1 root root   66 Nov 20 23:43 ..
-rw-r--r-- 1 root root  102 Mar 31  2024 .placeholder
-rwxr-xr-x 1 root root 1478 Mar 22  2024 apt-compat
-rwxr-xr-x 1 root root  123 Feb  5  2024 dpkg

/etc/cron.hourly:
total 4
drwxr-xr-x 2 root root  26 Sep 23 04:46 .
drwxr-xr-x 1 root root  66 Nov 20 23:43 ..
-rw-r--r-- 1 root root 102 Mar 31  2024 .placeholder

/etc/cron.monthly:
total 4
drwxr-xr-x 2 root root  26 Sep 23 04:46 .
drwxr-xr-x 1 root root  66 Nov 20 23:43 ..
-rw-r--r-- 1 root root 102 Mar 31  2024 .placeholder

/etc/cron.weekly:
total 4
drwxr-xr-x 2 root root  26 Sep 23 04:46 .
drwxr-xr-x 1 root root  66 Nov 20 23:43 ..
-rw-r--r-- 1 root root 102 Mar 31  2024 .placeholder

/etc/cron.yearly:
total 4
drwxr-xr-x 2 root root  26 Sep 23 04:46 .
drwxr-xr-x 1 root root  66 Nov 20 23:43 ..
-rw-r--r-- 1 root root 102 Mar 31  2024 .placeholder
picoplayer@challenge:~$ cat /etc/crontab
# academy{Sch3DUL7NG_T45K3_L1NUX_5ea693bf}
```

## Notas Adicionales
## Referencias

