## Descripción
Can you get the flag? Go to this [website](http://saturn.picoctf.net:55825/) and see what you can discover.

## Pistas 
What is the web inspector in web browsers?

## Solución
- Si entramos a la página web nos aparece una explicación de los Histiaeus.
- Click derecho > Inspeccionar > Fuentes
- Tenemos un archivo html, al analizar el código tenemos lo siguiente:
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>On Histiaeus</title>
  </head>
  <body>
    <h1>On Histiaeus</h1>
    <p>However, according to Herodotus, Histiaeus was unhappy having to stay in
       Susa, and made plans to return to his position as King of Miletus by 
       instigating a revolt in Ionia. In 499 BC, he shaved the head of his 
       most trusted slave, tattooed a message on his head, and then waited for 
       his hair to grow back. The slave was then sent to Aristagoras, who was 
       instructed to shave the slave's head again and read the message, which 
       told him to revolt against the Persians.</p>
    <br>
    <p> Source: Wikipedia on Histiaeus </p>
	<!--picoCTF{1n5p3t0r_0f_h7ml_8113f7e2}-->
  </body>
</html>
```

## Bandera
picoCTF{1n5p3t0r_0f_h7ml_8113f7e2}

## Notas Adicionales
Sin embargo, según Herodoto, Histiaeus no estaba feliz de tener que quedarse en Susa e hizo planes para regresar a su posición como rey de Mileto instigando una revuelta en Jonia. En 499 a. C., afeitó la cabeza de su esclavo de mayor confianza, tatuó un mensaje en su cabeza y luego esperó a que le volviera a crecer el cabello. Luego, el esclavo fue enviado a Aristágoras, quien recibió instrucciones de afeitar la cabeza del esclavo nuevamente y leer el mensaje, que le decía que se rebelara contra los persas.

## Referencias
https://en.wikipedia.org/wiki/Histiaeus