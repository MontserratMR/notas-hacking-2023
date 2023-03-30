## Descripción
Read the rules of the competition and get a little bonus! [Rules](https://picoctf.org/competitions/2023-spring-rules.html)

## Pistas 
1. Ctrl-F will not work

## Solución
Al analizar el sitio con las reglas, en el último apartado "What are the other rules and terms for picoCTF 2023?" hay una imagen con la bandera. Si analizamos el código HTML, la imagen viene acompañada de un atributo alt, del cual podemos copiarlo directamente.

## Bandera
picoCTF{h34rd_und3r5700d_4ck_cba1c711}

## Notas Adicionales
El atributo alt  especifica un texto alternativo para una imagen, si la imagen no se puede mostrar. 
El atributo alt proporciona información alternativa para una imagen si un usuario por algún motivo no puede verla (debido a una conexión lenta, un error en el atributo src o si el usuario usa un lector de pantalla).

## Referencias
https://www.w3schools.com/tags/att_img_alt.asp