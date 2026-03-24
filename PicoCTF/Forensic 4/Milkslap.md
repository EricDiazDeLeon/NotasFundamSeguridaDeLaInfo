## Objetivo 
[🥛](http://mercury.picoctf.net:7585/)
## Solución  
```bash
kali@KaliEND:~/Downloads/PicoCTF/Act17$ wget http://mercury.picoctf.net:7585/concat_v.png  
--2026-03-19 21:37:41--  http://mercury.picoctf.net:7585/concat_v.png  
Resolviendo mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:7585... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 18095920 (17M) [image/png]  
Grabando a: «concat_v.png»  
  
concat_v.png                      55%[==============================>                          ]   9,56M   326KB/s    en 25s        
  
2026-03-19 21:38:06 (395 KB/s) - Conexión cerrada en el byte 10025280. Reintentando.  
  
--2026-03-19 21:38:07--  (intento: 2)  http://mercury.picoctf.net:7585/concat_v.png  
Conectando con mercury.picoctf.net (mercury.picoctf.net)[18.189.209.142]:7585... conectado.  
Petición HTTP enviada, esperando respuesta... 200 OK  
Longitud: 18095920 (17M) [image/png]  
Grabando a: «concat_v.png»  
  
concat_v.png                     100%[========================================================>]  17,26M   599KB/s    en 27s        
  
2026-03-19 21:38:34 (656 KB/s) - «concat_v.png» guardado [18095920/18095920]  
  
kali@KaliEND:~/Downloads/PicoCTF/Act17$ ls  
concat_v.png  dds1-alpine.flag.img  
kali@KaliEND:~/Downloads/PicoCTF/Act17$zsteg -a concat_v.png | grep pico
```
```
flag: picoCTF{image3_m4n1pul4t10n_sl4p5}
```
## Notas Adicionales 
PicoCTF{imag3_m4n1pul4t10n_sl4p5}
### Referencias

