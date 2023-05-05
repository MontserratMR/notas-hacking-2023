## Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:65442/) and see what you can discover.

## Pistas 
Do you know how to modify cookies?

## Solución

- Si damos click en el botón "Continuar como invitado" la página simplemente nos muestra un mensaje de que aún no hay servicios para invitados.
- Con ayuda de un editor de cookies, podemos ver que se creó una con nombre "isAdmin" cuyo valor es 0.
- Cambiamos el valor de la cookie a 1 y obtenemos la bandera.
- 
## Bandera
picoCTF{gr4d3_A_c00k13_5d2505be}

## Referencias
Cookie-Editor 
https://lh3.googleusercontent.com/B7zVzT2oGn0vZ8UZBV6-DQ2H3ADspMtdwMcot3U7ejNa8TYa1d7qu8tXA4-_wh4n061V1AT1cwv52UchItZZ1GXlReM=w440-h280-e365-rj-sc0x00ffffff
