## Objetivo
Can you get the real meaning from this file. Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).
## Solución
```bash
ericdiazdeleon in @retos/interencdec ❯ wget https://artifacts.picoctf.net/c_titan/108/enc_flag
Saving 'enc_flag'
HTTP response 200  [https://artifacts.picoctf.net/c_enc_flag             100% [=>]      73     --.-KB/s
                          [Fi]

ericdiazdeleon in @retos/interencdec ❯ ls
enc_flag

ericdiazdeleon in @retos/interencdec ❯ cat enc_flag YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==

ericdiazdeleon in @retos/interencdec ❯ base64 -d enc_flag 
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='
```
## Notas Adicionales
Encontre el string YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==
dentro del archivo enc_flag, posteriormente lo pase a base64decode para obtener el siguiente string:
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='
el cual pasamos a cyberchef y convertimos a:
wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}

posteriormente encontre una herramienta que hace cifrados cesar (rot13) y le pase la cadena obteniendo asi la flag.
flag: picoCTF{caesar_d3cr9pt3d_a47c6d69}

el cual 
### Referencias
https://www.dcode.fr/cifrado-cesar

https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=ZDNCcWRrcEJUWHRxYUd4NmFIbGZhek5xZVRsM1lUTnJYMmcwTjJvMmF6WTVmUT09