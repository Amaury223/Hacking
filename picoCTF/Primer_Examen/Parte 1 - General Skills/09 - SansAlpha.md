## Descripción
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols. `ssh -p 11409 ctf-player@chatelaine.cylabacademy.net`

Use password: `fa1a82ad`
## Solución
```
Dark23-academy@webshell:~$ ssh -p 11409 ctf-player@chatelaine.cylabacademy.net

Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

ctf-player@chatelaine.cylabacademy.net's password: fa1a82ad

SansAlpha$ "$(<~/*/????.???)"
\x1b[?2004l
bash: return 0 academy{7h15_mu171v3r53_15_m4dn355_9b767f07}: command not found
\x1b[?2004h
SansAlpha$  

academy{7h15_mu171v3r53_15_m4dn355_9b767f07}

```
## Notas Adicionales
- **Expansión de comodines (`~/*/????.???`)**:
    
    - `~` se expande a tu directorio personal (`/home/ctf-player`).
        
    - `/*` coincide con el subdirectorio donde está guardado el reto.
        
    - `/????.???` coincide con el nombre del archivo de la bandera (por ejemplo, `flag.txt`).
        
- **Redirección de entrada (`<`)**: El operador `<` lee el contenido del archivo de la bandera y lo envía como entrada.
    
- **Sustitución de comandos (`"$( ... )"`)**: Bash intenta ejecutar el contenido de la bandera como si fuera un comando. Como el archivo contiene texto plano que inicia con el formato de la bandera, Bash generará un error de este tipo:
## Referencias
`ssh -p 11409 ctf-player@chatelaine.cylabacademy.net`

Use password: `fa1a82ad`