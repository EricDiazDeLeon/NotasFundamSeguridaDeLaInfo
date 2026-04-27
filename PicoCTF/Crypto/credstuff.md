## Objetivo
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
## Solución
```bash
ericdiazdeleon in @retos/credstuff ❯ wget https://artifacts.picoctf.net/c/151/leak.tar
Saving 'leak.tar'
HTTP response 200  [https://artifacts.picoctf.net/c/151/leak.tar]
leak.tar             100% [======================================================>]   30.00K    --.-KB/s
                          [Files: 1  Bytes: 30.00K [36.80KB/s] Redirects: 0  Todo:]

ericdiazdeleon in @retos/credstuff ❯ ls
leak.tar
ericdiazdeleon in @credstuff/leak ❯ ls
leak

ericdiazdeleon in @credstuff/leak ❯ cd leak/

ericdiazdeleon in @leak/leak ❯ ls
passwords.txt  usernames.txt
```
## Notas Adicionales
busque el username leakeado y era la linea 378, despues busque la misma linea en las contrasenas y encontre cvpbPGS{P7e1S_54I35_71Z3} la cual mande a cyberchef con un rot13 de fuerza bruta.
picoCTF{C7r1F_54V35_71M3}
### Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13_Brute_Force(true,true,false,100,0,true,'')&input=Y3ZwYlBHU3tQN2UxU181NEkzNV83MVozfQ