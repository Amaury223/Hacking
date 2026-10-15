## Descripción
Using a Secure Shell (SSH) is going to be pretty important. Can you `ssh` as `ctf-player` to `xebec.cylabacademy.net` at port `11861` to get the flag?

You'll also need the password `647e170e`. If asked, accept the fingerprint with `yes`.

If your device doesn't have a shell, you can use: [https://webshell.cylabacademy.org](https://webshell.cylabacademy.org/)

If you're not sure what a shell is, check out our Primer: [https://primer.cylabacademy.org/#_the_shell](https://primer.cylabacademy.org/#_the_shell)

## Solución
```
Dark23-academy@webshell:~$ ssh ctf-player@xebec.cylabacademy.net  -p 11861
The authenticity of host '[xebec.cylabacademy.net]:11861 ([3.14.181.178]:11861)' can't be established.
ED25519 key fingerprint is SHA256:kVN52XVkz2iIK4aejnbgUtjII8pR3AC32uXQ9QHITDI.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[xebec.cylabacademy.net]:11861' (ED25519) to the list of known hosts.
ctf-player@xebec.cylabacademy.net's password: 
Welcome ctf-player, here's your flag: academy{s3cur3_c0nn3ct10n_a827223e}
Connection to xebec.cylabacademy.net closed.

academy{s3cur3_c0nn3ct10n_a827223e}

```
## Notas Adicionales

## Referencias
- [https://webshell.cylabacademy.org/](https://webshell.cylabacademy.org/)
- [https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)
