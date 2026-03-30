## Objetivo
How about some hide and seek? Download this file [here](https://artifacts.picoctf.net/c_titan/6/unknown.zip).
## Solución
```bash
ericdiazdeleon in @retos/forensic4 ❯ wget https://artifacts.picoctf.net/c_titan/6/unknown.zip
Saving 'unknown.zip'
HTTP response 200  [https://artifacts.picoctf.net/c_titan/6/unknown.zip]
unknown.zip          100% [======================================================>]    2.14M    2.64MB/s
                          [Files: 1  Bytes: 2.14M [1.25MB/s] Redirects: 0  Todo: 0]

ericdiazdeleon in @retos/forensic4 ❯ ls
unknown.zip
ericdiazdeleon in @retos/forensic4 ❯ unzip unknown.zip 
Archive:  unknown.zip
  inflating: ukn_reality.jpg         

ericdiazdeleon in @retos/forensic4 ❯ ls
ukn_reality.jpg  unknown.zericdiazdeleon in @retos/forensic4 ❯ steghide extract -sf ukn_reality.jpg 
Anotar salvoconducto: 
anot� los datos extra�dos e/"flag".

ericdiazdeleon in @retos/forensic4 ❯ ls
flag  ukn_reality.jpg  unknown.zip

ericdiazdeleon in @retos/forensic4 ❯ cat flag
The flag is not here maybe think in simpler terms. Data that explains data.

ericdiazdeleon in @retos/forensic4 ❯ exiftool ukn_reality.jpg 
ExifTool Version Number         : 13.10
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:02:15 16:40:21-06:00
File Access Date/Time           : 2026:03:29 20:41:44-06:00
File Inode Change Date/Time     : 2026:03:29 20:28:13-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fYTZkZjhkYjh9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4

ericdiazdeleon in @retos/forensic4 ❯ ip
	
```
## Notas Adicionales
intente varias cosas para encontrar la flag, pero al final fue mas fácil de lo que pensé, solamente mire en los metadatos de la imagen y encontré un texto en base 64, el cual pase a texto normal y obtuve la flag: picoCTF{ME74D47A_HIDD3N_a6df8db8}
### Referencias
https://www.base64decode.org/