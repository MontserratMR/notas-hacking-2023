## Descripción
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Pistas 
1. Try fixing the file header

## Solución
* Al inspeccionar el encabezado podemos ver cadenas que son comunes en los archivos PNG. De acuerdo con las especificaciones PNG, los primeros 8 bytes del archivo son constantes, así que arreglamos eso.
* Después del encabezado vienen una serie de fragmentos. Cada fragmento comienza con 4 bytes para la longitud del fragmento, 4 bytes para el tipo, luego el propio contenido del fragmento (con la longitud declarada anteriormente) y 4 bytes de una suma de comprobación. El primer fragmento es IHDR y tiene una longitud de 0xD, arreglamos eso también.
* Ahora el archivo es identificado como un PNG.
* Pero si lo checamos con pngcheck nos muestra varios errores:
* En el fragmento pHYs, el encabezado declaró 9 bytes, luego vienen 4 bytes del tipo (pHYs), luego nueve bytes del payload y 4 bytes del checksum. pngcheck dice que la suma de verificación esperada como se indica en el archivo (0x495224f0) no coincide con la suma de verificación calculada. Por lo tanto, la suma de comprobación está dañada o los datos lo están. Dado que los píxeles por unidad difieren en solo un byte, y el 0xaa para el eje X hace que el valor sea muy grande, colocamos un cero en su lugar.
* Tenemos un fragmento de tamaño 0xaaaaffa5 que es muy grande y un tipo de \xabDET que no existe. El tipo de fragmento más cercano es IDAT, así que arreglamos eso.
* El siguiente fragmento de IDAT está en el desplazamiento 0x10004. Contamos la longitud del primer fragmento IDAT a partir de 0x5B y necesitamos agregar otros 4 bytes adicionales para la suma de verificación. Por lo tanto, obtenemos la longitud de 0x10004 - 0x5B - 0x4 = 0xFFA5 que es buena ya que el valor original es 0xAAAAFFA5. Entonces, solo necesitamos anular 0xAAAA con ceros nuevamente.
* pngcheck ya no nos muestra errores, entonces podemos abrir la imagen y tenemos la bandera.
```
File: mystery ASCII Offset: 0x00000008 / 0x000318BB (%00)  M
00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  43 22 44 52 PNG........C"DR

00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52 PNG........IHDR

00000040  00 09 70 48  59 73 00 00   16 25 00 00  16 25 01 49 .pHYs...%...%.I

00000050  52 24 F0 00  00 FF A5 AB   44 45 54 78  5E EC BD 3F $......DETx^..?

00000050  52 24 F0 00  00 FF A5 49   44 41 54 78  5E EC BD 3F $.....IDATx^..?
```

## Bandera
picoCTF{c0rrupti10n_1847995}

## Notas Adicionales
![[Pasted image 20230329111625.png]]
-   `IHDR` must be the first chunk; it contains (in this order) the image's
    -   width (4 bytes)
    -   height (4 bytes)
    -   bit depth (1 byte, values 1, 2, 4, 8, or 16)
    -   color type (1 byte, values 0, 2, 3, 4, or 6)
    -   compression method (1 byte, value 0)
    -   filter method (1 byte, value 0)
    -   interlace method (1 byte, values 0 "no interlace" or 1 "[Adam7](https://en.wikipedia.org/wiki/Adam7 "Adam7") interlace") (13 data bytes total).

*  `IDAT` contains the image, which may be split among multiple IDAT chunks. Such splitting increases filesize slightly, but makes it possible to generate a PNG in a streaming manner. The IDAT chunk contains the actual image data, which is the output stream of the compression algorithm.}
* `pHYs` holds the intended pixel size (or pixel aspect ratio); the pHYs contains "Pixels per unit, X axis" (4 bytes), "Pixels per unit, Y axis" (4 bytes), and "Unit specifier" (1 byte) for a total of 9 bytes.

## Referencias
https://en.wikipedia.org/wiki/PNG
