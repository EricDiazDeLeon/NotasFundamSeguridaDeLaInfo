## Objetivo
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead? You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/15/challenge.zip)

The same files are accessible via SSH here: `ssh -p 56390 ctf-player@atlas.picoctf.net` Using the password `1db87a14`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
## Solución
```bash
ericdiazdeleon in @retos/forensic4 ❯ wget https://artifacts.picoctf.net/c_atlas/15/challenge.zip
Saving 'challenge.zip'
HTTP response 200  [https://artifacts.picoctf.net/c_atlas/15/challenge.zip]
challenge.zip        100% [======================================================>]     741     --.-KB/s
                          [Files: 1  Bytes: 741  [779 B/s] Redirects: 0  Todo: 0  ]

ericdiazdeleon in @retos/forensic4 ❯ unzip challenge.zip 
Archive:  challenge.zip
   creating: home/ctf-player/drop-in/
 extracting: home/ctf-player/drop-in/flag.png  

ericdiazdeleon in @retos/forensic4 ❯ ls
challenge.zip  home

ericdiazdeleon in @retos/forensic4 ❯ cd home/

ericdiazdeleon in @forensic4/home ❯ ls
ctf-player

ericdiazdeleon in @forensic4/home ❯ cd ctf-player/

ericdiazdeleon in @home/ctf-player ❯ ls
drop-in

ericdiazdeleon in @home/ctf-player ❯ cd drop-in/

ericdiazdeleon in @ctf-player/drop-in ❯ ls
flag.png

ericdiazdeleon in @ctf-player/drop-in ❯ ls -la
total 4
drwxr-xr-x. 1 ericdiazdeleon ericdiazdeleon  16 mar 11  2024 .
drwxr-xr-x. 1 ericdiazdeleon ericdiazdeleon  14 mar 29 21:24 ..
-rw-r--r--. 1 ericdiazdeleon ericdiazdeleon 351 mar 11  2024 flag.png

ericdiazdeleon in @ctf-player/drop-in ❯ 
```
## Notas Adicionales
En el zip habia una imagen con un qr.
Use un lector de qr online para obtener la flag: 
picoCTF{p33k_@_b00_19eccd10}

### Referencias
https://scanqr.org/