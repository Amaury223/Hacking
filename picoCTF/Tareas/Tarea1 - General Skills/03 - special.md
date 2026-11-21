## Descripción
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)

Start your instance to see connection details. `ssh -p 19615 ctf-player@xebec.cylabacademy.net`

The password is `647e170e`

Instance

Expires in 14:54

Hints

1

Experiment with different shell syntax

## Solución
```
Dark23-academy@webshell:~$ ssh -p 19615 ctf-player@xebec.cylabacademy.net
The authenticity of host '[xebec.cylabacademy.net]:19615 ([77.113.98.131]:19615)' can't be established.
ED25519 key fingerprint is SHA256:TMzuFX+tQxG+rVL0CK63ywMGkWGIsWZEgT7sWWAVfMg.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[xebec.cylabacademy.net]:19615' (ED25519) to the list of known hosts.
ctf-player@xebec.cylabacademy.net's password: 
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

Special$ whoami
Whom 
sh: 1: Whom: not found
Special$ pwd
Pod 
sh: 1: Pod: not found
Special$ ls
Ls 
sh: 1: Ls: not found
Special$ /bin/l?
Absolutely not paths like that, please!
Special$ ${SHELL:0:1}
${SHELL:0:1} 
sh: 1: Bad substitution
Special$ echo *
Echo * 
sh: 1: Echo: not found
Special$ $(echo ls)
Echo ls 
sh: 1: Echo: not found
Special$ {l,s}
{l,s} 
sh: 1: {l,s}: not found
Special$ l''s
Li's 
sh: 1: Syntax error: Unterminated quoted string
Special$ /???/???
Absolutely not paths like that, please!
Special$ l\ s
La s 
sh: 1: La: not found
Special$ l$@s
Less 
sh: 1: Less: not found
Special$ /???/???
Absolutely not paths like that, please!
Special$ /???/?????
Absolutely not paths like that, please!
Special$ ??
I 
sh: 1: I: not found
Special$ $(<*)
$(<*) 
sh: 1: cannot open *: No such file
Special$ $'\x6c\x73'
$'\x6c\x73' 
sh: 1: $\x6c\x73: not found
Special$ x=ls
Pals 
sh: 1: Pals: not found
Special$ $x
Ex 
sh: 1: Ex: not found
Special$ x=l
All 
sh: 1: All: not found
Special$ y=s
Yes 
sh: 1: Yes: not found
Special$ $ x$y
$ my 
sh: 1: $: not found
Special$ _=/bin/ls
$__=/bin/ls 
Special$ 
I 
sh: 1: I: not found
Special$ a=/
b=bin
c=ls
$a$b$cA 
sh: 1: A: not found
Special$ Brain 
sh: 1: Brain: not found
Special$ Cols 
sh: 1: Cols: not found
Special$ ${.}
$a$b$c${.} 
sh: 1: Bad substitution
Special$ :;#
:;# 
Special$ *
* 
sh: 1: blargh: not found
Special$ ?*
I 
sh: 1: I: not found
Special$ /???/?????
Absolutely not paths like that, please!
Special$ 


```
## Notas Adicionales
## Referencias
