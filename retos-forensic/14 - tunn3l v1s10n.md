## Descripción
We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

## Pistas 
Weird that it won't display right...

## Solución
* Por el header BM sabemos que es un archivo bitmap, así que le cambiamos en el nombre la extensión.
* No se puede abrir
* Analizamos el código hexadecimal y arreglamos algunos errores, (originalmente están marcados con BAD)
```
00000000  42 4D 8E 26  2C 00 00 00   00 00 **28 00**  00 00 **28 00**               
```
* Ya abre la imagen. En la parte superior viene una leyenda "not a flag, sorry", por lo que debemos seguir buscando.
![[Pasted image 20230331200622.png]]
* Si vemos los metadatos, nos podemos dar cuenta que el alto de la imagen está un poco limitado a comparación del tamaño del archivo, vamos a ver si podemos ampliar las dimensiones.
```
00000010  00 00 6E 04  00 00 40 04   00 00 01 00  18 00 00 00               
```
* Ahora sí, agrandamos el alto de la imagen y se alcanza a ver la bandera.

## Bandera
picoCTF{qu1t3_a_v13w_2020}
## Notas Adicionales

|Hex signature | Extension| Referencia |
|--|--|--|
|42 4D | BM| [bitmap](https://en.wikipedia.org/wiki/Bitmap)|
 
## Referencias
https://en.wikipedia.org/wiki/List_of_file_signatures
https://en.wikipedia.org/wiki/BMP_file_format