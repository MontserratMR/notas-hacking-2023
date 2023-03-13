## Descripción
The factory is hiding things form all of its users. Can you login as Joe and find what they've been looking at? https://jupiter.challenges.picoctf.org/problem/13594/

## Pistas 
Hmm it doesn't seem to check anyone's password, except for Joe's?

## Solución
No importa qué datos usemos para el inicio de sesión, nos deja ingresar pero no nos da la bandera. Esto sugiere que una cookie podría estar siendo usada para almacenar una variable que impida que veamos la bandera. Efectivamente, notamos una cookie de administrador establecida en False. Cambiar esto a Verdadero y actualizar la página nos da la bandera.

## Bandera
picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}

## Notas Adicionales

**Using HTTP cookies**
An HTTP cookie (web cookie, browser cookie) is a small piece of data that a server sends to a user's web browser. The browser may store the cookie and send it back to the same server with later requests. Typically, an HTTP cookie is used to tell if two requests come from the same browser—keeping a user logged in, for example. It remembers stateful information for the stateless HTTP protocol.

## Referencias
[http](https://developer.mozilla.org/en-US/docs/Web/HTTP)
[headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)