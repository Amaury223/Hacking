## Descripción
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.

Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!

You can download the challenge files here:

- [challenge.zip](https://challenge-files.cylabacademy.net/library/692c76e6606d080db3acca948e5d4b3994ffc7848a3970e969dc00c8199f261a/challenge.zip) `ssh -p 24515 ctf-player@xebec.cylabacademy.net`

Using the password `8d1db23b`. Accept the fingerprint with `yes`; the game starts as soon as you are connected. Remember, in a shell, passwords are hidden!

Instance

Expires in 14:54

Hints

1

Have you ever played hot or cold? Binary search is a bit like that.

2

You have a very limited number of guesses. Try larger jumps between numbers!

3

The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?
## Solución
```
Dark23-academy@webshell:~$ ssh -p 24515 ctf-player@xebec.cylabacademy.net
ctf-player@xebec.cylabacademy.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 600
Lower! Try again.
Enter your guess: 550
Higher! Try again.
Enter your guess: 575
Lower! Try again.
Enter your guess: 560
Lower! Try again.
Enter your guess: 555
Higher! Try again.
Enter your guess: 557
Higher! Try again.
Enter your guess: 558
Higher! Try again.
Enter your guess: 559
Congratulations! You guessed the correct number: 559
Here's your flag: academy{g00d_gu355_7ba05aa7}
Connection to xebec.cylabacademy.net closed.
```
## Notas Adicionales
## Referencias
https://challenge-files.cylabacademy.net/library/692c76e6606d080db3acca948e5d4b3994ffc7848a3970e969dc00c8199f261a/challenge.zip