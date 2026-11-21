## Descripción
I accidentally wrote the flag down. Good thing I deleted it!

You download the challenge files here:

- [challenge.zip](https://challenge-files.cylabacademy.net/library/eb55b249985e4e0071c4b0d30bda05411072401a22a192c8ba4cefc007b24e90/challenge.zip)

Hints

1

Version control can help you recover files if you change or lose them!

2

Read the chapter on Git from the picoPrimer [here](https://primer.cylabacademy.org/#_git_version_control)

3

You can 'checkout' commits to see the files inside them
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/eb55b249985e4e0071c4b0d30bda05411072401a22a192c8ba4cefc007b24e90/challenge.zip
--2026-11-20 23:20:08--  https://challenge-files.cylabacademy.net/library/eb55b249985e4e0071c4b0d30bda05411072401a22a192c8ba4cefc007b24e90/challenge.zip
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.95, 3.160.5.40, 3.160.5.64, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 22270 (22K) [application/octet-stream]
Saving to: 'challenge.zip.1'

challenge.zip.1     100%[==================>]  21.75K  --.-KB/s    in 0.009s  

2026-11-20 23:20:08 (2.32 MB/s) - 'challenge.zip.1' saved [22270/22270]

Dark23-academy@webshell:~$ unzip challenge.zip

 
Dark23-academy@webshell:~$ cd drop-in

Dark23-academy@webshell:~$ unzip -l challenge.zip.1
Archive:  challenge.zip.1
  Length      Date    Time    Name
---------  ---------- -----   ----
        0  2026-09-23 05:15   drop-in/
        0  2026-09-23 05:15   drop-in/.git/
        0  2026-09-23 05:15   drop-in/.git/branches/
        0  2026-09-23 05:15   drop-in/.git/hooks/
      478  2026-09-23 05:15   drop-in/.git/hooks/applypatch-msg.sample
      896  2026-09-23 05:15   drop-in/.git/hooks/commit-msg.sample
     4726  2026-09-23 05:15   drop-in/.git/hooks/fsmonitor-watchman.sample
      189  2026-09-23 05:15   drop-in/.git/hooks/post-update.sample
      424  2026-09-23 05:15   drop-in/.git/hooks/pre-applypatch.sample
     1643  2026-09-23 05:15   drop-in/.git/hooks/pre-commit.sample
      416  2026-09-23 05:15   drop-in/.git/hooks/pre-merge-commit.sample
     1374  2026-09-23 05:15   drop-in/.git/hooks/pre-push.sample
     4898  2026-09-23 05:15   drop-in/.git/hooks/pre-rebase.sample
      544  2026-09-23 05:15   drop-in/.git/hooks/pre-receive.sample
     1492  2026-09-23 05:15   drop-in/.git/hooks/prepare-commit-msg.sample
     2783  2026-09-23 05:15   drop-in/.git/hooks/push-to-checkout.sample
     2308  2026-09-23 05:15   drop-in/.git/hooks/sendemail-validate.sample
     3650  2026-09-23 05:15   drop-in/.git/hooks/update.sample
        0  2026-09-23 05:15   drop-in/.git/info/
      240  2026-09-23 05:15   drop-in/.git/info/exclude
       73  2026-09-23 05:15   drop-in/.git/description
        0  2026-09-23 05:15   drop-in/.git/refs/
        0  2026-09-23 05:15   drop-in/.git/refs/heads/
       41  2026-09-23 05:15   drop-in/.git/refs/heads/master
        0  2026-09-23 05:15   drop-in/.git/refs/tags/
       23  2026-09-23 05:15   drop-in/.git/HEAD
       92  2026-09-23 05:15   drop-in/.git/config
        0  2026-09-23 05:15   drop-in/.git/objects/
        0  2026-09-23 05:15   drop-in/.git/objects/pack/
        0  2026-09-23 05:15   drop-in/.git/objects/info/
        0  2026-09-23 05:15   drop-in/.git/objects/45/
       43  2026-09-23 05:15   drop-in/.git/objects/45/c4b4ea1617d3cc2f0d5c9bdaa69470c7aae828
        0  2026-09-23 05:15   drop-in/.git/objects/c1/
       56  2026-09-23 05:15   drop-in/.git/objects/c1/8145d0ef759818d4a90d917fd07ff288bd1915
        0  2026-09-23 05:15   drop-in/.git/objects/08/
      124  2026-09-23 05:15   drop-in/.git/objects/08/c903aa2824148d91cd462d37def218762455fc
        0  2026-09-23 05:15   drop-in/.git/objects/d5/
       27  2026-09-23 05:15   drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7
        0  2026-09-23 05:15   drop-in/.git/objects/0c/
       56  2026-09-23 05:15   drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03
        0  2026-09-23 05:15   drop-in/.git/objects/74/
      160  2026-09-23 05:15   drop-in/.git/objects/74/f36590419df729e2b2a97cfd1cc6e9ec02692b
      145  2026-09-23 05:15   drop-in/.git/index
       22  2026-09-23 05:15   drop-in/.git/COMMIT_EDITMSG
        0  2026-09-23 05:15   drop-in/.git/logs/
      320  2026-09-23 05:15   drop-in/.git/logs/HEAD
        0  2026-09-23 05:15   drop-in/.git/logs/refs/
        0  2026-09-23 05:15   drop-in/.git/logs/refs/heads/
      320  2026-09-23 05:15   drop-in/.git/logs/refs/heads/master
       11  2026-09-23 05:15   drop-in/message.txt
---------                     -------
    27574                     50 files
Dark23-academy@webshell:~$ mkdir commitment
Dark23-academy@webshell:~$ 
Dark23-academy@webshell:~$ unzip challenge.zip.1 -d commitment
Archive:  challenge.zip.1
   creating: commitment/drop-in/
   creating: commitment/drop-in/.git/
   creating: commitment/drop-in/.git/branches/
   creating: commitment/drop-in/.git/hooks/
  inflating: commitment/drop-in/.git/hooks/applypatch-msg.sample  
  inflating: commitment/drop-in/.git/hooks/commit-msg.sample  
  inflating: commitment/drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: commitment/drop-in/.git/hooks/post-update.sample  
  inflating: commitment/drop-in/.git/hooks/pre-applypatch.sample  
  inflating: commitment/drop-in/.git/hooks/pre-commit.sample  
  inflating: commitment/drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: commitment/drop-in/.git/hooks/pre-push.sample  
  inflating: commitment/drop-in/.git/hooks/pre-rebase.sample  
  inflating: commitment/drop-in/.git/hooks/pre-receive.sample  
  inflating: commitment/drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: commitment/drop-in/.git/hooks/push-to-checkout.sample  
  inflating: commitment/drop-in/.git/hooks/sendemail-validate.sample  
  inflating: commitment/drop-in/.git/hooks/update.sample  
   creating: commitment/drop-in/.git/info/
  inflating: commitment/drop-in/.git/info/exclude  
  inflating: commitment/drop-in/.git/description  
   creating: commitment/drop-in/.git/refs/
   creating: commitment/drop-in/.git/refs/heads/
 extracting: commitment/drop-in/.git/refs/heads/master  
   creating: commitment/drop-in/.git/refs/tags/
 extracting: commitment/drop-in/.git/HEAD  
  inflating: commitment/drop-in/.git/config  
   creating: commitment/drop-in/.git/objects/
   creating: commitment/drop-in/.git/objects/pack/
   creating: commitment/drop-in/.git/objects/info/
   creating: commitment/drop-in/.git/objects/45/
 extracting: commitment/drop-in/.git/objects/45/c4b4ea1617d3cc2f0d5c9bdaa69470c7aae828  
   creating: commitment/drop-in/.git/objects/c1/
 extracting: commitment/drop-in/.git/objects/c1/8145d0ef759818d4a90d917fd07ff288bd1915  
   creating: commitment/drop-in/.git/objects/08/
 extracting: commitment/drop-in/.git/objects/08/c903aa2824148d91cd462d37def218762455fc  
   creating: commitment/drop-in/.git/objects/d5/
 extracting: commitment/drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: commitment/drop-in/.git/objects/0c/
 extracting: commitment/drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: commitment/drop-in/.git/objects/74/
 extracting: commitment/drop-in/.git/objects/74/f36590419df729e2b2a97cfd1cc6e9ec02692b  
  inflating: commitment/drop-in/.git/index  
 extracting: commitment/drop-in/.git/COMMIT_EDITMSG  
   creating: commitment/drop-in/.git/logs/
  inflating: commitment/drop-in/.git/logs/HEAD  
   creating: commitment/drop-in/.git/logs/refs/
   creating: commitment/drop-in/.git/logs/refs/heads/
  inflating: commitment/drop-in/.git/logs/refs/heads/master  
 extracting: commitment/drop-in/message.txt  
Dark23-academy@webshell:~$ cd commitment/drop-in
Dark23-academy@webshell:~/commitment
/drop-in$ git log --oneline

[6]+  Stopped                 git log --oneline
Dark23-academy@webshell:~/commitment
/drop-in$ git status
On branch master
nothing to commit, working tree clean
Dark23-academy@webshell:~/commitment
/drop-in$ ls -la
total 4
drwxr-xr-x 3 Dark23-academy Dark23-academy  37 Sep 23 05:15 .
drwxrwxr-x 3 Dark23-academy Dark23-academy  21 Nov 20 23:26 ..
drwxr-xr-x 8 Dark23-academy Dark23-academy 166 Nov 20 23:26 .git
-rw-r--r-- 1 Dark23-academy Dark23-academy  11 Sep 23 05:15 message.txt
Dark23-academy@webshell:~/commitment
/drop-in$ git log --all --name-status

[7]+  Stopped                 git log --all --name-status
Dark23-academy@webshell:~/commitment
/drop-in$ 

Dark23-academy@webshell:~/commitment
/drop-in$ git checkout 08c903a -- message.txt
Dark23-academy@webshell:~/commitment
/drop-in$ cat message.txt
academy{s@n1t1z3_43665d2b}
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/eb55b249985e4e0071c4b0d30bda05411072401a22a192c8ba4cefc007b24e90/challenge.zip

https://primer.cylabacademy.org/#_git_version_control