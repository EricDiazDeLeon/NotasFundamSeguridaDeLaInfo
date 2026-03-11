## Objetivo
Help us test the form by submiting the username as `test` and password as `test!` The website running [here](http://saturn.picoctf.net:62851/).
## Solución
```bash
picoCTF{proxies_all_the_way_3d9e3697}
```
## Notas Adicionales
Este reto se puede resolver también con burpsuite, pero yo lo hice con la opción de el inspector de red que esta predeterminado en firefox para obtener las redirecciones de la pagina y al ver los url pude obtener la flag dividida en dos partes:
`cGljb0NURntwcm94aWVzX2Fs`
`bF90aGVfd2F5XzNkOWUzNjk3fQ==`
esto es base64 por lo que use una herramienta para desencriptarlo y obtener la flag.
### Referencias
https://www.base64decode.org/