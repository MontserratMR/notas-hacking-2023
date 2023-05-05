## Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:56469/) and see what you can discover.

## Pistas 
Is there more code than what the inspector initially shows?

## Solución

- Si entramos a la página web nos aparece una explicación de los includes.
- Click derecho > Inspeccionar > Fuentes
- Tenemos dos archivos, uno .js y otro css, al analizar el código tenemos lo siguiente:

```
(script.js)
/*  picoCTF{1nclu51v17y_1of2_  */

(style.css)
f7w_2of2_b8f4b022}
```

## Bandera
picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}

## Notas Adicionales
Muchos lenguajes de programación y otros archivos de computadora tienen una directiva, a menudo llamada include (a veces copiar o importar), que hace que el contenido de un segundo archivo se inserte en el archivo original. Estos archivos incluidos se denominan cuadernos o archivos de encabezado. A menudo se utilizan para definir el diseño físico de los datos del programa, fragmentos de código de procedimiento y/o declaraciones de reenvío, al mismo tiempo que promueven la encapsulación y la reutilización del código.

## Referencias
https://en.wikipedia.org/wiki/Include_directive