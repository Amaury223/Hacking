## Descripción
How well can you perfom basic binary operations? Start searching for the flag here `nc xebec.cylabacademy.net 46616`
## Solución
```
Dark23-academy@webshell:~$ nc xebec.cylabacademy.net 46616

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11111110
Binary Number 2: 00001111


Question 1/6:
Operation 1: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111111
Correct!

Question 2/6:
Operation 2: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00000111
Correct!

Question 3/6:
Operation 3: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 111011100010
Correct!

Question 4/6:
Operation 4: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 111111100
Correct!

Question 5/6:
Operation 5: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 00001110
Correct!

Question 6/6:
Operation 6: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 100001101
Correct!

Enter the results of the last operation in hexadecimal: 10D

Correct answer!
The flag is: academy{b1tw^3se_0p3eR@tI0n_su33essFuL_316363ba}

```
## Notas Adicionales
## Referencias
nc xebec.cylabacademy.net 46616
