## Descripción
This [garden](https://jupiter.challenges.picoctf.org/static/4153422e18d40363e7ffc7e15a108683/garden.jpg) contains more than it seems.

## Pistas 
What is a hex editor?
## Solución
Descargamos el archivo en nuestra máquina.
Se nos recomienda usar un editor hexadecimal así que recurrimos al hexeditor de linux:
```
┌──(kali㉿kali)-[~/Desktop/pico/glory]
└─$ hexeditor garden.jpg
```
una vez ahí, tenemos la opción de buscar un patrón en forma de cadena presionando Shift + W. Sabemos que las banderas comienzan por "pico" así que eso es lo que introducimos. Tenemos la bandera.
Otra forma fue la de pasarlo por un cat
```
┌──(kali㉿kali)-[~/Desktop/pico/glory]
└─$ cat garden.jpg
```
Nos aparece mucho código no legible para nosotros, sin embargo, nos manda hasta el final del archivo, y en la última línea también está la bandera.
## Bandera
picoCTF{more_than_m33ts_the_3y33dd2eEF5}

## Notas Adicionales
Editor hexadecimal
Un **editor hexadecimal** (o **editor de archivos binarios**) es un tipo de programa informático que permite a un usuario modificar archivos binarios. Los editores hexadecimales fueron diseñados para editar sectores de datos de disquetes o discos duros por lo que a veces se llaman "editores de sectores".

Por medio del editor hexadecimal, el usuario puede ver o redactar el contenido intacto y exacto de un archivo. Ocurre lo contrario con otros programas de alto nivel que interpretan el mismo contenido del archivo de forma diferente. Por ejemplo, los datos intactos de la imagen (los raws), y la manera de interpretar el mismo archivo del software de edición de imágenes.

## Referencias
https://es.wikipedia.org/wiki/Editor_hexadecimal