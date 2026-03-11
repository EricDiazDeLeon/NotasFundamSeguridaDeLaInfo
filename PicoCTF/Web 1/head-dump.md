## Objetivo
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag. The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden. The website is running [picoCTF News](http://verbal-sleep.picoctf.net:60954/).
## Solución
```bash
picoCTF{Pat!3nt_15_Th3_K3y_546786ba}
```
## Notas Adicionales
Una vulnerabilidad muy fuerte es dejar accesible el heapbump accesible para todos, lo cual es un archivo de todo lo que se guarda en memoria, fue solo cuestión de filtrar entre el todo documento "picoctf" y así encontré la flag.
### Referencias