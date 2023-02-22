## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

## Datos Acceso
bandit11 
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
```
**Forma 1**
bandit11@bandit:~$ ls 
data.txt 
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi 
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M] The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv  

*Forma 2*
bandit11@bandit:~$ ls 
data.txt 
bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi bandit11@bandit:~$ python3 
Python 3.10.6 (main, Nov 14 2022, 16:10:14) [GCC 11.3.0] on linux Type "help", "copyright", "credits" or "license" for more information. 
>>> import codecs 
>>> >>> codecs.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi','rot13') 
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'
```

## Notas Adicionales
|comando|descripción|opciones|man|
|---|---|---|---|
|tr| traduce o elimina caracteres|-|[tr](https://linux.die.net/man/1/tr)

## Referencias
[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)