## Objetivo
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/258/flag.png)
## Solución
```bash
ericdiazdeleon in @retos/forensic4 ❯ wget https://artifacts.picoctf.net/c/258/flag.png
Saving 'flag.png'
HTTP response 200  [https://artifacts.picoctf.net/c/258/flag.png]
flag.png             100% [======================================================>]   41.93K    --.-KB/s
                          [Files: 1  Bytes: 41.93K [47.37KB/s] Redirects: 0  Todo:]

ericdiazdeleon in @retos/forensic4 ❯ ls
flag.png

ericdiazdeleon in @retos/forensic4 ❯ binwalk flag.png 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2876, uncompressed size: 3029, name: secret/flag.png
42915         0xA7A3          End of Zip archive, footer length: 22


ericdiazdeleon in @retos/forensic4 ❯ binwalk -e flag.png 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 512 x 504, 8-bit/color RGBA, non-interlaced
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2876, uncompressed size: 3029, name: secret/flag.png
42915         0xA7A3          End of Zip archive, footer length: 22


ericdiazdeleon in @retos/forensic4 ❯ ls
flag.png  _flag.png.extracted

ericdiazdeleon in @retos/forensic4 ❯ cd _flag.png.extracted/

ericdiazdeleon in @forensic4/_flag.png.extracted ❯ ls
29  29.zlib  9B3B.zip  secret

ericdiazdeleon in @forensic4/_flag.png.extracted ❯ cd secret/

ericdiazdeleon in @_flag.png.extracted/secret ❯ ls
flag.png

ericdiazdeleon in @_flag.png.extracted/secret ❯ eog flag.png 
```
## Notas Adicionales
Dentro de la imagen había un directorio secreto y dentro de el una imagen que contenia la flag en texto plano, usé binwalk para extraer y acceder a los datos dentro de la imagen.
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_d55982e8}
### Referencias
