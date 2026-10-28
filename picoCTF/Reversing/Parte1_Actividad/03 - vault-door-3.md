## Descripción
## vault-door-3

Reverse EngineeringMedium

by Mark E. Haase·picoCTF 2019

This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://challenge-files.cylabacademy.net/library/14bca593f597cbc6b521a3deb17bd94a81c603c8cdc801f0a6b41f89ec79e27f/VaultDoor3.java)

Hints

1

Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.
## Solución
```
import java.util.*;

class VaultDoor3 {
    public static void main(String args[]) {
        VaultDoor3 vaultDoor = new VaultDoor3();
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

    // Our security monitoring team has noticed some intrusions on some of the
    // less secure doors. Dr. Evil has asked me specifically to build a stronger
    // vault door to protect his Doomsday plans. I just *know* this door will
    // keep all of those nosy agents out of our business. Mwa ha!
    //
    // -Minion #2671
    public boolean checkPassword(String password) {
        if (password.length() != 32) {
            return false;
        }
        char[] buffer = new char[32];
        int i;
        for (i=0; i<8; i++) {
            buffer[i] = password.charAt(i);
        }
        for (; i<16; i++) {
            buffer[i] = password.charAt(23-i);
        }
        for (; i<32; i+=2) {
            buffer[i] = password.charAt(46-i);
        }
        for (i=31; i>=17; i-=2) {
            buffer[i] = password.charAt(i);
        }
        String s = new String(buffer);
        return s.equals("jU5t_a_sna_3lpm16gd4e_u_4_m7re42");
    }
}




los primeros 8 caracteres se mantienen
jU5t_a_s

del 8 a 15 se invierten y se insertan en el lugar 23-i
1mpl3_an

Los caracteres en las posiciones 16, 18, 20... van en las posiciones 46-i
4, r, m, 4, u, e, d, 6.

los ultimos caracteres
g, 4, _, _, _, 7, e, 2.

jU5t_a_s1mpl3_an4gr4m_4_u_e7de62



academy{jU5t_a_s1mpl3_an4gr4m_4_u_2be258}
```
## Notas Adicionales
## Referencias
