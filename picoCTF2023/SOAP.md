## Descripción
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

Additional details will be available after launching your challenge instance.

## Pistas 
None

## Solución
* Iniciamos el reto
* Cuando nos cargue la pagina del reto iniciamos el burpsuite con intercept on
* Le damos en cualquier opción de details dentro de la pagina
![[Imagen de WhatsApp 2023-03-20 a las 01.18.33.jpg]]
Cuando le demos nos va a cargar un método post que contiene lo siguiente
![[Imagen de WhatsApp 2023-03-20 a las 01.19.17.jpg]]
* Eso lo mandamos al repeater
* Dentro vamos a hacer la xml entity injection
* Quedaría algo así
![[Imagen de WhatsApp 2023-03-20 a las 01.21.57.jpg]]
* Escribimos lo de la linea 14 que eso se usa para acceder al archivo passwd en la página web y en ID lo llamamos, ya solo presionamos send
* Y debería de llegar la siguiente respuesta del servidor

## Bandera
![[Imagen de WhatsApp 2023-03-20 a las 01.22.39 2.jpg]]

## Notas Adicionales

## Referencias
https://youtu.be/UfILDa_qStQ

https://www.north-networks.com/que-es-xml-external-entity-xxe-injection/
