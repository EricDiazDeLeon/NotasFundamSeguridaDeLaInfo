## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [dolls.jpg](https://challenge-files.picoctf.net/c_wily_courier/1709f471bed1c90c7b343b2d6a4f0d1257abed9ef467457d6438adb71be0b37c/dolls.jpg)
## Solución
```bash
ericdiazdeleon in @Descargas/retos ❯ wget https://challenge-files.picoctf.net/c_wily_courier/1709f471bed1c90c7b343b2d6a4f0d1257abed9ef467457d6438adb71be0b37c/dolls.jpg
Saving 'dolls.jpg'
HTTP response 200  [https://challenge-files.picoctf.net/c_wily_courier/1709f471bed1c90c7b343b2d6a4f0d1257dolls.jpg            100% [======================================================>]  636.34K    5.67MB/s
                          [Files: 1  Bytes: 636.34K [620.82KB/s] Redirects: 0  Tod]
ericdiazdeleon in @Descargas/retos ❯ ls
'[Content_Types].xml'   docProps   dolls.jpg   Forensics_is_fun.pptm   ppt   _rels

ericdiazdeleon in @Descargas/retos ❯ binwalk -e dolls.jpg 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378933, uncompressed size: 383920, name: base_images/2_c.jpg
651591        0x9F147         End of Zip archive, footer length: 22


ericdiazdeleon in @Descargas/retos ❯ ls
'[Content_Types].xml'   dolls.jpg              Forensics_is_fun.pptm   _rels
 docProps               _dolls.jpg.extracted   ppt

ericdiazdeleon in @Descargas/retos ❯ cd _dolls.jpg.extracted/

ericdiazdeleon in @retos/_dolls.jpg.extracted ❯ ls
4286C.zip  base_images

ericdiazdeleon in @retos/_dolls.jpg.extracted ❯ cd base_images/

ericdiazdeleon in @_dolls.jpg.extracted/base_images ❯ ls
2_c.jpg

ericdiazdeleon in @_dolls.jpg.extracted/base_images ❯ binwalk 2_c.jpg 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196025, uncompressed size: 201427, name: base_images/3_c.jpg
383787        0x5DB2B         End of Zip archive, footer length: 22
383898        0x5DB9A         End of Zip archive, footer length: 22
ericdiazdeleon in @_dolls.jpg.extracted/base_images ❯ binwalk -e 2_c.jpg 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196025, uncompressed size: 201427, name: base_images/3_c.jpg
383787        0x5DB2B         End of Zip archive, footer length: 22
383898        0x5DB9A         End of Zip archive, footer length: 22


ericdiazdeleon in @_dolls.jpg.extracted/base_images ❯ ls
2_c.jpg  _2_c.jpg.extracted

ericdiazdeleon in @_dolls.jpg.extracted/base_images ❯ cd _2_c.jpg.extracted/

ericdiazdeleon in @base_images/_2_c.jpg.extracted ❯ cd base_images/

ericdiazdeleon in @_2_c.jpg.extracted/base_images ❯ ls
3_c.jpg

ericdiazdeleon in @_2_c.jpg.extracted/base_images ❯ binwalk -e 3_c.jpg 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77633, uncompressed size: 79786, name: base_images/4_c.jpg
201405        0x312BD         End of Zip archive, footer length: 22


ericdiazdeleon in @_2_c.jpg.extracted/base_images ❯ ls
3_c.jpg  _3_c.jpg.extracted

ericdiazdeleon in @_2_c.jpg.extracted/base_images ❯ cd _3_c.jpg.extracted/

ericdiazdeleon in @base_images/_3_c.jpg.extracted ❯ cd base_images/

ericdiazdeleon in @_3_c.jpg.extracted/base_images ❯ ls
4_c.jpg

ericdiazdeleon in @_3_c.jpg.extracted/base_images ❯ binwalk 4_c.jpg 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v1.0 to extract, compressed size: 42, uncompressed size: 42, name: flag.txt
79764         0x13794         End of Zip archive, footer length: 22


ericdiazdeleon in @_3_c.jpg.extracted/base_images ❯ ls
4_c.jpg

ericdiazdeleon in @_3_c.jpg.extracted/base_images ❯ binwalk -e 4_c.jpg 
/usr/lib/python3.14/site-packages/binwalk/core/magic.py:431: SyntaxWarning: "\." is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\."? A raw string is also an option.
  self.period = re.compile("\.")

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v1.0 to extract, compressed size: 42, uncompressed size: 42, name: flag.txt
79764         0x13794         End of Zip archive, footer length: 22


ericdiazdeleon in @_3_c.jpg.extracted/base_images ❯ ls
4_c.jpg  _4_c.jpg.extracted

ericdiazdeleon in @_3_c.jpg.extracted/base_images ❯ cd _4_c.jpg.extracted/

ericdiazdeleon in @base_images/_4_c.jpg.extracted ❯ ls
136DA.zip  flag.txt

ericdiazdeleon in @base_images/_4_c.jpg.extracted ❯ cat flag.txt 
picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}
```
## Notas Adicionales
Habia carpetas comprimidas dentro de la imagen, y dentro de esta habia otra y otra y otra.
extraje cada una de estas hasta que encontré un archivo llamado flag.txt a el cual le hice un cat y obtuve la flag.
picoCTF{LL9lb1dR4QbGe4l4iWCvGq9pdtwt7392}
### Referencias
