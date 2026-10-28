## Descripción
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://challenge-files.cylabacademy.net/library/17c5c9578078962dbf80a9a2901feca3411343c5aa04a3d139ee9c16779c9e58/VaultDoor5.java)

Hints

1

You may find an encoder/decoder tool helpful, such as [https://encoding.tools/](https://encoding.tools/)

2

Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.
## Solución
```
import java.net.URLDecoder;

import java.util.*;

  

class VaultDoor5 {

    public static void main(String args[]) {

        VaultDoor5 vaultDoor = new VaultDoor5();

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

  

    // Minion #7781 used base 8 and base 16, but this is base 64, which is

    // like... eight times stronger, right? Riiigghtt? Well that's what my twin

    // brother Minion #2415 says, anyway.

    //

    // -Minion #2414

    public String base64Encode(byte[] input) {

        return Base64.getEncoder().encodeToString(input);

    }

  

    // URL encoding is meant for web pages, so any double agent spies who steal

    // our source code will think this is a web site or something, defintely not

    // vault door! Oh wait, should I have not said that in a source code

    // comment?

    //

    // -Minion #2415

    public String urlEncode(byte[] input) {

        StringBuffer buf = new StringBuffer();

        for (int i=0; i<input.length; i++) {

            buf.append(String.format("%%%2x", input[i]));

        }

        return buf.toString();

    }

  

    public boolean checkPassword(String password) {

        String urlEncoded = urlEncode(password.getBytes());

        String base64Encoded = base64Encode(urlEncoded.getBytes());

        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"

                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"

                        + "JTM0JTVmJTMzJTYzJTYzJTM4JTYxJTM5JTY0JTM2";

        return base64Encoded.equals(expected);

    }

}



academy{c0nv3rt1ng_fr0m_ba5e_64_3cc8a9d6}
```
## Notas Adicionales
El código hace: `password → urlEncode → base64Encode → expected`. Para recuperar la contraseña original, solo había que **revertir el proceso en orden inverso**:

1. **Decodificar Base64** de la cadena `expected` → esto nos da la versión URL-encoded (`%63%30%6e%76...`)
2. **Decodificar URL-encoding** de eso → nos da el password en texto plano

import base64, urllib.parse
expected = "JTYzJTMwJTZlJTc2..." # (el string completo)
url_encoded = base64.b64decode(expected).decode() # => "%63%30%6e%76%33%72%74..."

password = urllib.parse.unquote(url_encoded)# => "c0nv3rt1ng_fr0m_ba5e_64_3cc8a9d6"
## Referencias
