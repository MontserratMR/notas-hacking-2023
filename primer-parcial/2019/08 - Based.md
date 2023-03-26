## Descripción
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Pistas 
1. I hear python can convert things.
2. It might help to have multiple windows open.

## Solución

```
dnightshade-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
Please give the 01110000 01100101 01100001 01110010 as a word.
...
you have 45 seconds.....

Input:
pear
Please give me the  143 157 156 164 141 151 156 145 162 as a word.
Input:
container
Please give me the 74657374 as a word.
Input:
test
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}
```

Una vez más, hay distintas formas de abordar el problema. Como las pistas lo sugieren, usando Python es una forma. Yo recurrí otra vez al CyberChef.
El programa nos brindaba cadenas en sistema binario, octal y hexadecimal, respectivamente. Únicamente ingresé las palabras "traducidas" y me dio la bandera.

## Bandera
picoCTF{learning_about_converting_values_b375bb16}

## Notas Adicionales

## Referencias
https://gchq.github.io/CyberChef/