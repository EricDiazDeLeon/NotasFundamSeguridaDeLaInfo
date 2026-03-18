## Objetivo
We found this [packet capture](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/capture.pcap) and [key](https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/picopico.key). Recover the flag.
## Solución
```bash
ericdiazdeleon in @retos/webnet0 ❯ wget https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/capture.pcap
Saving 'capture.pcap'
HTTP response 200  [https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007afcapture.pcap         100% [======================================================>]   12.85K    --.-KB/s
                          [Files: 1  Bytes: 12.85K [18.25KB/s] Redirects: 0  Todo:]

ericdiazdeleon in @retos/webnet0 ❯ wget https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007af1626f99c44fc5cf92333f9fd8876ce9a/picopico.key
Saving 'picopico.key'
HTTP response 200  [https://challenge-files.picoctf.net/c_fickle_tempest/66113619363fca174ef6bf56587007afpicopico.key         100% [======================================================>]    1.66K    --.-KB/s
                          [Files: 1  Bytes: 1.66K [2.96KB/s] Redirects: 0  Todo: 0]

ericdiazdeleon in @retos/webnet0 ❯ ls -la
total 20
drwxr-xr-x. 1 ericdiazdeleon ericdiazdeleon    48 mar 18 14:32 .
drwxr-xr-x. 1 ericdiazdeleon ericdiazdeleon   210 mar 18 14:32 ..
-rw-r--r--. 1 ericdiazdeleon ericdiazdeleon 13163 nov 14 13:58 capture.pcap
-rw-r--r--. 1 ericdiazdeleon ericdiazdeleon  1704 nov 14 13:58 picopico.key

ericdiazdeleon in @retos/webnet0 ❯ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)

ericdiazdeleon in @retos/webnet0 ❯ wireshark capture.pcap &
[1] 7980
```
## Notas Adicionales
abrí el pcap en wireshark, posteriormente importe la llave privada al protocolo TLS y realicé una búsqueda de los detalles del paquete para encontrar un string que contuviera ¨picoCTF¨ y así la encontré.
picoCTF{nongshim.shrimp.crackers}
### Referencias
wireshark