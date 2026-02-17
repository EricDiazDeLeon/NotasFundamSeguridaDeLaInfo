## Objetivo
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.`ssh -p 50935 ctf-player@saturn.picoctf.net`The password is `8a707622`
## Solución
```bash
EricDiaz-picoctf@webshell:~$ ssh -p 50935 ctf-player@saturn.picoctf.net
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.8.0-1044-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Tue Feb 17 14:13:13 2026 from 127.0.0.1
Special$ ((ls))
((ls)) 
blargh
Special$ (ls)
Also 
sh: 1: Also: not found
Special$ ((Cat))
((Cat)) 
sh: 1: Cat: not found
Special$ ((cat)) < blargh
((cat)) < large 
sh: 1: cannot open large: No such file
Special$ ((cat)) <blargh/flag.txt
((cat)) <blargh/flag.txt
picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}
```
## Notas Adicionales
Al probar distintos comandos, se notó que la sintaxis normal (cat archivo, ls -al, etc.) no funcionaba correctamente, después de experimentar bastante con sintaxis de bash, se encontró que escribir los comandos dentro de doble paréntesis funcionaba: `((cat))`
El sistema no permitía pasar argumentos dentro de (( )).
Por ejemplo:
`((cat blargh))`

descubrí que sí funcionaba la redirección de entrada <`
por lo que usé ((cat)) de modo que pude usar el comando:
`<blargh/flag.txt` para obtener la bandera.
`picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}`
### Referencias