## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

## Pistas 
1. Does that encoding look familiar?
2. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Es el mismo proceso que en los retos anteriores. 
Analizamos el código de validación y hay vemos que han dado valores ASCII de cada letra en la contraseña, los hemos convertido. Usando la herramienta de terminal python3, imprimí los caracteres ASCII. La contraseña es: 39ce
```
dnightshade-picoctf@webshell:~$ python level2.py
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
```

## Bandera
picoCTF{tr45h_51ng1ng_502ec42e}
## Notas Adicionales

## Referencias
