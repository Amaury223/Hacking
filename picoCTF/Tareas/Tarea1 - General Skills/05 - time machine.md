## Descripción
What was I last working on? I remember writing a note to help me remember...

You can download the challenge files here:

- [challenge.zip](https://challenge-files.cylabacademy.net/library/7272719b133b310bdbdcf12a116dd4499cd5d2c7247ee62e50f0a113aebfcdfb/challenge.zip)

Hints

1

The `cat` command will let you read a file, but that won't help you here!

2

Read the chapter on Git from the picoPrimer [here](https://primer.cylabacademy.org/#_git_version_control).

3

When committing a file with git, a message can (and should) be included.
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/7272719b133b310bdbdcf12a116dd4499cd5d2c7247ee62e50f0a113aebfcdfb/challenge.zip
--2026-11-20 23:40:34--  https://challenge-files.cylabacademy.net/library/7272719b133b310bdbdcf12a116dd4499cd5d2c7247ee62e50f0a113aebfcdfb/challenge.zip
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.95, 3.160.5.40, 3.160.5.18, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 20808 (20K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zi   0%       0  --.-KB/s challenge.zi 100%  20.32K  --.-KB/s    in 0.008s  

2026-11-20 23:40:35 (2.37 MB/s) - 'challenge.zip' saved [20808/20808]

Dark23-academy@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/push-to-checkout.sample  
  inflating: drop-in/.git/hooks/sendemail-validate.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
  inflating: drop-in/.git/description  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
  inflating: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/c7/
 extracting: drop-in/.git/objects/c7/dc02645dbf0605e6dde1d6296238dd941653dd  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
Dark23-academy@webshell:~$ mkdir time-machine
Dark23-academy@webshell:~$ unzip challenge.zip -d time-machine
Archive:  challenge.zip
   creating: time-machine/drop-in/
  inflating: time-machine/drop-in/message.txt  
   creating: time-machine/drop-in/.git/
   creating: time-machine/drop-in/.git/branches/
   creating: time-machine/drop-in/.git/hooks/
  inflating: time-machine/drop-in/.git/hooks/applypatch-msg.sample  
  inflating: time-machine/drop-in/.git/hooks/commit-msg.sample  
  inflating: time-machine/drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: time-machine/drop-in/.git/hooks/post-update.sample  
  inflating: time-machine/drop-in/.git/hooks/pre-applypatch.sample  
  inflating: time-machine/drop-in/.git/hooks/pre-commit.sample  
  inflating: time-machine/drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: time-machine/drop-in/.git/hooks/pre-push.sample  
  inflating: time-machine/drop-in/.git/hooks/pre-rebase.sample  
  inflating: time-machine/drop-in/.git/hooks/pre-receive.sample  
  inflating: time-machine/drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: time-machine/drop-in/.git/hooks/push-to-checkout.sample  
  inflating: time-machine/drop-in/.git/hooks/sendemail-validate.sample  
  inflating: time-machine/drop-in/.git/hooks/update.sample  
   creating: time-machine/drop-in/.git/info/
  inflating: time-machine/drop-in/.git/info/exclude  
  inflating: time-machine/drop-in/.git/description  
   creating: time-machine/drop-in/.git/refs/
   creating: time-machine/drop-in/.git/refs/heads/
  inflating: time-machine/drop-in/.git/refs/heads/master  
   creating: time-machine/drop-in/.git/refs/tags/
 extracting: time-machine/drop-in/.git/HEAD  
  inflating: time-machine/drop-in/.git/config  
   creating: time-machine/drop-in/.git/objects/
   creating: time-machine/drop-in/.git/objects/pack/
   creating: time-machine/drop-in/.git/objects/info/
   creating: time-machine/drop-in/.git/objects/43/
 extracting: time-machine/drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: time-machine/drop-in/.git/objects/25/
 extracting: time-machine/drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: time-machine/drop-in/.git/objects/c7/
 extracting: time-machine/drop-in/.git/objects/c7/dc02645dbf0605e6dde1d6296238dd941653dd  
  inflating: time-machine/drop-in/.git/index  
 extracting: time-machine/drop-in/.git/COMMIT_EDITMSG  
   creating: time-machine/drop-in/.git/logs/
  inflating: time-machine/drop-in/.git/logs/HEAD  
   creating: time-machine/drop-in/.git/logs/refs/
   creating: time-machine/drop-in/.git/logs/refs/heads/
  inflating: time-machine/drop-in/.git/logs/refs/heads/master  
Dark23-academy@webshell:~$ cd time-machine/drop-in
Dark23-academy@webshell:~/time-machi
ne/drop-in$ git log
[1]+  Stopped                 git log

commit c7dc02645dbf0605e6dde1d6296238dd941653dd (HEAD -> master)
Author: academy <ops@cylabacademy.org>
Date:   Wed Sep 23 05:12:26 2026 +0000

    academy{t1m3m@ch1n3_b260a551}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/7272719b133b310bdbdcf12a116dd4499cd5d2c7247ee62e50f0a113aebfcdfb/challenge.zip

https://primer.cylabacademy.org/#_git_version_control