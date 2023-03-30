## Descripción
Help us test the form by submiting the username as `test` and password as `test!`

Additional details will be available after launching your challenge instance.

## Pistas 
None

## Solución
* Accedemos al reto y lo iniciamos
* Iniciamos sesion en burpsuite
* Iniciamos el reto a la ventana de inicio de sesion
* Una vez ahi interceptamos la pagina web dentro de burpsuite
* Iniciamos sesion y usuario en la pagina test:test!
* Nos vamos a burpsuite y nos daremos cuenta que antes de ir a la pagina como normalmente lo haria interceptó otras 2
 ![[Imagen de WhatsApp 2023-03-20 a las 01.07.33.jpg]]
* En ambas se encuentra esa id
* Si la metemos a cyberchef  en base64 cada una nos dara la mitad de la bandera

