## Descripción
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

## Pistas 
1. What does meta mean in the context of files?
2. Ever heard of metadata?

## Solución
Descargamos el archivo
Hay una herramienta en linux  que se llama [exiftool](https://linux.die.net/man/1/exiftool) la cual utilizamos para ver los metadatos de la imagen, ahí en las últimas líneas, en el apartado de "Artist" tenemos la bandera.
```
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ wget https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png

pico_img.png         100%[=====================>] 106.25K  --.-KB/s    in 0.1s    

2023-03-27 20:48:51 (765 KB/s) - ‘pico_img.png’ saved [108795/108795]

┌──(kali㉿kali)-[~/Desktop/pico]
└─$ ls
pico_img.png
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ exiftool pico_img.png
ExifTool Version Number         : 12.57
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2020:10:26 14:38:23-04:00
File Access Date/Time           : 2023:03:27 20:48:51-04:00
File Inode Change Date/Time     : 2023:03:27 20:48:51-04:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360
```

## Bandera
picoCTF{s0_m3ta_d8944929}

## Notas Adicionales
Metadatos
La definición más concreta de los metadatos es qué son “**datos acerca de los datos**” y sirven para suministrar información sobre los datos producidos. Los metadatos consisten en información que caracteriza datos, describen el contenido, calidad, condiciones, historia, disponibilidad y otras características de los datos.

## Referencias
https://www.geoidep.gob.pe/catalogo-metadatos/que-son-los-metadatos#:~:text=La%20definici%C3%B3n%20m%C3%A1s%20concreta%20de,otras%20caracter%C3%ADsticas%20de%20los%20datos

https://linux.die.net/man/1/exiftool