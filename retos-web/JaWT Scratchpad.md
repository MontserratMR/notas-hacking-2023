## Descripción
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

## Pistas 
1. What is that cookie?
2. Have you heard of JWT?

## Solución
Primero ingresamos al sitio web con algún nombre de usuario y notamos que se nos ha emitido una cookie jwt. Este es un token web JSON. También podemos decodificar nuestro token, donde vemos que la carga útil es:
```
{ "user": "john" }
```
Obviamente, nos gustaría cambiar el usuario a administrador, sin embargo, para codificar esto, se requiere la clave secreta. En la sección ¡Regístrese con su nombre!, un hipervínculo que enlaza con la página de GitHub de la herramienta JohnTheRipper sugiere que se requiere un método de fuerza bruta. 

La calve que se uso para codificar la firma es ilovepico.

Generamos un nuevo token con una firma diferente y lo pegamos en la cookie que se había generado al principio. 
Eso nos da la bandera
## Bandera
picoCTF{jawt_was_just_what_you_thought_1ca14548}

## Referencias
https://jwt.io/
[JSON Web Token](https://es.wikipedia.org/wiki/JSON_Web_Token)
