## Descripción
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Pistas 
1. How do operating systems know what kind of file it is? (It's not just the ending!
2. Make sure to submit the flag as picoCTF{XXXXX}
## Solución
Descargamos el archivo y al aplicarle el comando "file" para ver que tipo de archivo es nos muestra que se trata de un archivo png, sólo que tiene una extensión incorrecta:
```
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
```
lo único que tenemos que hacer es cambiar el nombre del archivo, con ayuda del comando mv
```
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ mv flag.txt flag.png
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ open flag.png 
```
Y así, nos muestra la imagen con la bandera.
## Bandera
picoCTF{now_you_know_about_extensions]

## Notas Adicionales

## Referencias
