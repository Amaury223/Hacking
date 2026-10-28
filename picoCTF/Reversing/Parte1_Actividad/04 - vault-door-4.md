## Descripción
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://challenge-files.cylabacademy.net/library/b21cf2891dc0aa8e13e806fc64fbf0a6f01d47760f7905540cf3a7139a3fc778/VaultDoor4.java)

Hints

1

Use a search engine to find an "ASCII table"

2

You will also need to know the difference between octal, decimal, and hexadecimal numbers.
## Solución
```
import java.util.*;

  

class VaultDoor4 {

    public static void main(String args[]) {

        VaultDoor4 vaultDoor = new VaultDoor4();

        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter vault password: ");

        String userInput = scanner.next();

    String input = userInput.substring("academy{".length(),userInput.length()-1);

    if (vaultDoor.checkPassword(input)) {

        System.out.println("Access granted.");

    } else {

        System.out.println("Access denied!");

        }

    }

  

    // I made myself dizzy converting all of these numbers into different bases,

    // so I just *know* that this vault will be impenetrable. This will make Dr.

    // Evil like me better than all of the other minions--especially Minion

    // #5620--I just know it!

    //

    //  .:::.   .:::.

    // :::::::.:::::::

    // :::::::::::::::

    // ':::::::::::::'

    //   ':::::::::'

    //     ':::::'

    //       ':'

    // -Minion #7781

    public boolean checkPassword(String password) {

        byte[] passBytes = password.getBytes();

        byte[] myBytes = {

            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,

            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,

            0142, 0131, 0164, 063 , 0163, 0137, 070 , 070 ,

            'a' , '3' , '1' , 'd' , 'a' , 'd' , '6' , 'c' ,

        };

        for (int i=0; i<32; i++) {

            if (passBytes[i] != myBytes[i]) {

                return false;

            }

        }

        return true;

    }

}

academy{jU5t_4_bUnCh_0f_bYt3s_88a31dad6c}
```
## Notas Adicionales
## Referencias
[CyberChef](https://gchq.github.io/CyberChef/)
