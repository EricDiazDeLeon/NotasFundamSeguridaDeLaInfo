## Objetivo
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key). Recover the flag.
## Solución
```bash
ericdiazdeleon in @retos/webnet1 ❯ wget https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/capture.pcap
Saving 'capture.pcap'
HTTP response 200  [https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972capture.pcap         100% [======================================================>]   90.35K    --.-KB/s
                          [Files: 1  Bytes: 90.35K [140.08KB/s] Redirects: 0  Todo]

ericdiazdeleon in @retos/webnet1 ❯ wget https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972f9bed7bd4932f931e14bfba80d75f815/picopico.key
Saving 'picopico.key'
HTTP response 200  [https://challenge-files.picoctf.net/c_fickle_tempest/d1e9add4e31989553f239ebf71ba5972picopico.key         100% [======================================================>]    1.66K    --.-KB/s
                          [Files: 1  Bytes: 1.66K [2.59KB/s] Redirects: 0  Todo: 0]

ericdiazdeleon in @retos/webnet1 ❯ ls -la
total 96
drwxr-xr-x. 1 ericdiazdeleon ericdiazdeleon    48 mar 18 14:45 .
drwxr-xr-x. 1 ericdiazdeleon ericdiazdeleon   224 mar 18 14:44 ..
-rw-r--r--. 1 ericdiazdeleon ericdiazdeleon 92525 nov 14 13:58 capture.pcap
-rw-r--r--. 1 ericdiazdeleon ericdiazdeleon  1704 nov 14 13:58 picopico.key
ericdiazdeleon in @retos/webnet1 ❯ eog vulture.jpg 
```
## Notas Adicionales
Usando wireshark para desencriptar el trafico usando la llave privada encontré una imagen la cual guarde y al abrirla y observar los metadatos encontré la flag en el campo Artist.
picoCTF{honey.roasted.peanuts}
### Referencias
