## Descripción
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 53638`

## Pistas 
1. ASCII is one of the most common encodings used in programming
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución
```
dnightshade-picoctf@webshell:~$ nc saturn.picoctf.net 53638 
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
^C
dnightshade-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')
picoCTF{gl17ch_m3_n07_bda68f75}
```

## Bandera
picoCTF{gl17ch_m3_n07_bda68f75}

## Notas Adicionales

## Referencias
