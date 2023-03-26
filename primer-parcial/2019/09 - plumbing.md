## Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

## Pistas 
1. Remember the flag format is picoCTF{XXXX}
2. What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)
## Solución
```
dnightshade-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 | grep 'picoCTF'
picoCTF{digital_plumb3r_5ea1fbd7}
```

Utilizando lo aprendido de los retos anteriores, buscamos el patrón de la bandera "picoCTF" con el comando  "grep" al mismo tiempo que nos conectamos al servidor con ayuda de un "pipe", de tal manera que podamos acceder a la información sin necesidad de entrar al archivo.

## Bandera
picoCTF{digital_plumb3r_5ea1fbd7}

## Notas Adicionales
A pipe is designated in commands by the vertical bar character, which is located on the same key as the backslash on U.S. keyboards. The general syntax for pipes is:

command_1 | command_2 [| command_3 . . . ]

This chain can continue for any number of commands or programs.

## Referencias
http://www.linfo.org/pipes.html