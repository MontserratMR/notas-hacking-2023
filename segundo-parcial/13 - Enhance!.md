## Descripción
Download this image file and find the flag.

-   [Download image file](https://artifacts.picoctf.net/c/100/drawing.flag.svg)

## Pistas 

## Solución
```
┌──(kali㉿kali)-[~]
└─$ strings drawing.flag.svg
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<!-- Created with Inkscape (http://www.inkscape.org/) -->
<svg
....
 id="tspan3764">F { 3 n h 4 n </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11588"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3752">c 3 d _ a a b 7 2 9 d d }</tspan></text>
....
```

## Bandera
picoCTF{3nh4nc3d_aab729dd}

## Notas Adicionales
Scalable Vector Graphics (SVG) is a web-friendly vector file format. As opposed to pixel-based raster files like JPEGs, vector files store images via mathematical formulas based on points and lines on a grid. This means that vector files like SVG can be significantly resized without losing any of their quality, which makes them ideal for logos and complex online graphics.

The **strings** command looks for printable strings in a file. A string is any sequence of 4 or more printable characters that end with a new-line or a null character. The **strings** command is useful for identifying random object files.
## Referencias
https://www.adobe.com/creativecloud/file-types/image/vector/svg-file.html

[ibm.com/docs/en/aix/7.2?topic=s-strings-command](https://www.ibm.com/docs/en/aix/7.2?topic=s-strings-command)