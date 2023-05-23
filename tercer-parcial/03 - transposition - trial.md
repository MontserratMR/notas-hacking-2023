## Descripción
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://artifacts.picoctf.net/c/192/message.txt).

## Pistas 
Split the message up into blocks of 3 and see how the first block is scrambled

## Solución

El mensaje que nos pasaron es el siguiente:
```
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2   
```
Básicamente tenemos que rotar cada tres letras consecutivas. Aquí está el código Python para el propósito:

```
┌──(kali㉿kali)-[~]
└─$ python3
Python 3.11.2 (main, Feb 12 2023, 00:48:52) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> msg = 'heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2'
>>> soln = ''
>>> 
>>> for n in range(int(len(msg)/3)):
...     n += 1
...     i = n * 3
...     M = msg[i-3:i]
...     soln += M[-1] + M[:-1]
... 
>>> print(soln)
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}

```

## Bandera
picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}

## Notas Adicionales

## Referencias
