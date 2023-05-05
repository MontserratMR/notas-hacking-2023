## Descripción
Can you get the flag?Here's the [website](http://saturn.picoctf.net:55287/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Pistas 

## Solución
- La página solicita el nombre del archivo .txt que desees leer.
- El enunciado nos da una pista diciendo que el sitio no está aceptando "rutas absolutas"... pero podemos intentar usando rutas relativas.
- Sabemos que tenemos que pasar 4 niveles para llegar al archivo .txt con la bandera, así que sería algo como esto:
```
../../../../flag.txt
```

## Bandera
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}

## Notas Adicionales
-   **Ruta absoluta:** se indica toda la ruta del archivo incluyendo el directorio raíz. Por ejemplo, **C:\carpeta1\carpeta2\archivo1**.**doc**
-   **Ruta relativa:** se indica la ruta a partir de donde este en ese momento situado. No se incluye el directorio raíz. Por ejemplo, si estamos en la ruta **C:\carpeta1** y queremos acceder al **archivo1** que esta dentro de la **carpeta2,** seria **carpeta2\archivo1.** Para ir al directorio padre, usamos dos puntos seguidos **(**.**.)**

## Referencias
https://www.discoduroderoer.es/rutas-relativas-y-absolutas/