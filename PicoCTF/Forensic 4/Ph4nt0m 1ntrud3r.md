## Objetivo
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag. To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder! Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/4d25aca04e2409ba0d917d8ed27d49c6fb616ff9603fa3926712cce623a3d7f5/myNetworkTraffic.pcap) and try to get the flag.
## Solución
```bash
ericdiazdeleon in @retos/forensic4 ❯ wget https://challenge-files.picoctf.net/c_verbal_sleep/4d25aca04e2409ba0d917d8ed27d49c6fb616ff9603fa3926712cce623a3d7f5/myNetworkTraffic.pcap
Saving 'myNetworkTraffic.pcap'
HTTP response 200  [https://challenge-files.picoctf.net/c_verbal_sleep/4d25aca04e2409ba0d917d8ed27d49c6fbmyNetworkTraffic.pca 100% [======================================================>]    1.41K    --.-KB/s
                          [Files: 1  Bytes: 1.41K [1.68KB/s] Redirects: 0  Todo: 0]

ericdiazdeleon in @retos/forensic4 ❯ ls
flag  myNetworkTraffic.pcap  ukn_reality.jpg  unknown.zip

ericdiazdeleon in @retos/forensic4 ❯ tshark -r myNetworkTraffic.pcap -T fields -e tcp.payload
ericdiazdeleon in @retos/forensic4 ❯ tshark -r myNetworkTraffic.pcap -T fields -e tcp.payload
583577344f5a6f3d
48374455666a6b3d
6f62306f3569303d
7935305a646d493d
7931765a7470593d
6842466d7833553d
6230676b4445453d
66513d3d
63476c6a62304e5552673d3d
38575855506c773d
4b5748393856633d
6b70524d31436b3d
5a5445775a54677a4f513d3d
36646d645738553d
587a4d3063336c6664413d3d
464e6f4e3374633d
626e52666447673064413d3d
4c4a7a68474c593d
745863592f45773d
596d68664e484a664f413d3d
657a46305833633063773d3d
465569577832383d

```
## Notas Adicionales
dentro del pcap y en los campos tcp.payload se encontraba la flag descompuesta en pedazos, solo era cambiarlos de hexadecimal y base64 a texto normal y acomodarlos de algun modo que tuviera sentido.
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_8e10e839}
### Referencias
https://gchq.github.io/CyberChef/#recipe=Fork('%5C%5Cn','%5C%5Cn',false)From_Hex('Auto')From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Cgo1YTU0NDU3NzVhNTQ2NzdhNGY1MTNkM2QKNTg3YTRkMzA2MzMzNmM2NjY0NDEzZDNkCjYyNmU1MjY2NjQ0NzY3MzA2NDQxM2QzZAo1OTZkNjg2NjRlNDg0YTY2NGY0MTNkM2QKCg