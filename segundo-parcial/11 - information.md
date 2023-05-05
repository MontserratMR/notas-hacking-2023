## Descripción
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/d1375e383810d8d957c04eef9e345732/cat.jpg)

## Pistas 
1. Look at the details of the file
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
- Con el comando hexeditor podemos ver los metadatos de la imagen que nos proporcionaron.
- En la columna de la derecha hay una sección con una cadena de texto que podría ser la bandera:
```
  0A 20 20 3C  63 63 3A 6C   69 63 65 6E  73 65 20 72               .  <cc:license r
  64 66 3A 72  65 73 6F 75   72 63 65 3D  27 63 47 6C               df:resource='cGl
  6A 62 30 4E  55 52 6E 74   30 61 47 56  66 62 54 4E               jb0NURnt0aGVfbTN
  30 59 57 52  68 64 47 46   66 4D 58 4E  66 62 57 39               0YWRhdGFfMXNfbW9
  6B 61 57 5A  70 5A 57 52   39 27 2F 3E  0A 20 3C 2F               kaWZpZWR9'/>. 
```
con cyberchef sabemos que se trata de base64. La decodificamos y tenemos la bandera.

## Bandera
picoCTF{the_m3tadata_1s_modified}

## Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjk