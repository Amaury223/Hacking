## Descripción
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

You can download the challenge files here:

- [challenge.zip](https://challenge-files.cylabacademy.net/library/f6083bff1452adfb4071460c0181f287b12f033aeb1e5d20e3326f213726ec69/challenge.zip)

Hints

1

`git branch -a` will let you see available branches

2

How can file 'diffs' be brought to the main branch? Don't forget to `git config`!

3

Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.
## Solución
```
Dark23-academy@webshell:~$ wget https://challenge-files.cylabacademy.net/library/f6083bff1452adfb4071460c0181f287b12f033aeb1e5d20e3326f213726ec69/challenge.zip
--2026-11-20 23:03:38--  https://challenge-files.cylabacademy.net/library/f6083bff1452adfb4071460c0181f287b12f033aeb1e5d20e3326f213726ec69/challenge.zip
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 3.160.5.18, 3.160.5.95, 3.160.5.40, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27727 (27K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip       100%[==================>]  27.08K  --.-KB/s    in 0.01s   

2026-11-20 23:03:38 (2.20 MB/s) - 'challenge.zip' saved [27727/27727]

Dark23-academy@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
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
 extracting: drop-in/.git/refs/heads/main  
   creating: drop-in/.git/refs/heads/feature/
  inflating: drop-in/.git/refs/heads/feature/part-1  
 extracting: drop-in/.git/refs/heads/feature/part-2  
  inflating: drop-in/.git/refs/heads/feature/part-3  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/77/
 extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690  
   creating: drop-in/.git/objects/b9/
 extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a  
   creating: drop-in/.git/objects/19/
 extracting: drop-in/.git/objects/19/5eace652745c7bc15e1804518c730163d4a625  
   creating: drop-in/.git/objects/e4/
 extracting: drop-in/.git/objects/e4/684235acb1830f8229aea5b620bf425ad16426  
   creating: drop-in/.git/objects/a7/
 extracting: drop-in/.git/objects/a7/48ccd793b2a552b4f4cc23947eb63da08f3bf4  
   creating: drop-in/.git/objects/e2/
 extracting: drop-in/.git/objects/e2/9282e2f80283e4e3402aebcb2efff732ea5b03  
   creating: drop-in/.git/objects/7a/
 extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833  
   creating: drop-in/.git/objects/d1/
 extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258  
   creating: drop-in/.git/objects/54/
 extracting: drop-in/.git/objects/54/76122aae17405690c35ee527bf5b6dfb1b92fc  
   creating: drop-in/.git/objects/a8/
 extracting: drop-in/.git/objects/a8/b4d453f11fd1334bb675bdde64d99de173260e  
   creating: drop-in/.git/objects/d7/
 extracting: drop-in/.git/objects/d7/9b9574cf2e54afdae0dfbeb5dc6e360b388600  
   creating: drop-in/.git/objects/fd/
 extracting: drop-in/.git/objects/fd/8439cf302c2438bdd9cfc8e4cf3b33083db13d  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/main  
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1  
  inflating: drop-in/.git/logs/refs/heads/feature/part-2  
  inflating: drop-in/.git/logs/refs/heads/feature/part-3  
  inflating: drop-in/flag.py         
Dark23-academy@webshell:~$ ls
challenge.zip  drop-in
Dark23-academy@webshell:~$ cd drop-in
Dark23-academy@webshell:~/drop-in$ git branch -a

[2]+  Stopped                 git branch -a
Dark23-academy@webshell:~/drop-in$ git status
On branch main
nothing to commit, working tree clean
Dark23-academy@webshell:~/drop-in$ git log --oneline --all --graph

[3]+  Stopped                 git log --oneline --all --graph
Dark23-academy@webshell:~/drop-in$ git branch -a

[4]+  Stopped                 git branch -a
Dark23-academy@webshell:~/drop-in$ git log --oneline --all --graph

[5]+  Stopped                 git log --oneline --all --graph
Dark23-academy@webshell:~/drop-in$ git config user.name "CTF Player"
Dark23-academy@webshell:~/drop-in$ git config user.email "player@example.com"
Dark23-academy@webshell:~/drop-in$ git merge feature/part-1
Updating 195eace..e29282e
Fast-forward
 flag.py | 1 +
 1 file changed, 1 insertion(+)
Dark23-academy@webshell:~/drop-in$ git merge feature/part-2
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.
Dark23-academy@webshell:~/drop-in$ git merge feature/part-3
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
Dark23-academy@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")
<<<<<<< HEAD
print("academy{t3@mw0rk_", end='')
=======

print("m@k3s_th3_dr3@m_", end='')
>>>>>>> feature/part-2
Dark23-academy@webshell:~/drop-in$ git add flag.py
Dark23-academy@webshell:~/drop-in$ git commit -m "merge feature part 2"
[main 4969532] merge feature part 2
Dark23-academy@webshell:~/drop-in$ git merge feature/part-3
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.
Dark23-academy@webshell:~/drop-in$ cat flag.py
print("Printing the flag...")
<<<<<<< HEAD
<<<<<<< HEAD
print("academy{t3@mw0rk_", end='')
=======

print("m@k3s_th3_dr3@m_", end='')
>>>>>>> feature/part-2
=======

print("w0rk_07f8061f}")
>>>>>>> feature/part-3
Dark23-academy@webshell:~/drop-in$ python3 flag.py
  File "/home/Dark23-academy/drop-in/flag.py", line 2
    <<<<<<< HEAD
    ^^
SyntaxError: invalid syntax
Dark23-academy@webshell:~/drop-in$ nano flag.py

academy{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_07f8061f}
```
![[Pasted image 20261120171000.png]]
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/f6083bff1452adfb4071460c0181f287b12f033aeb1e5d20e3326f213726ec69/challenge.zip