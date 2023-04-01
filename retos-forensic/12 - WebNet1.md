## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Pistas 
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

## Solución
* Abrimos el paquete con wireshark. Si tratamos de seguir el stream TLS, no lo vamos a entender, está encriptado, tenemos que cargar la llave privada primero.
* Edición - Preferencias - Protocolos - TLS - RSA keys list - Llave
* En uno de los paquetes en color amarillo (los desencriptados) resalta el no. 47 porque lleva un archivo jpg que se está descargando. Podemos extraerla del tráfico.
*  File - Export objects - HTTP - archivo - save
* Abrimos la imagen:
![[Pasted image 20230331185354.png]]
* Un memillo, no hay bandera, pero si lo pasamos por strings en la tercera línea
```
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ open vulture.jpg 
                                                                             
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ strings vulture.jpg 
JFIF
Exif
picoCTF{honey.roasted.peanuts}
...
```

## Bandera
picoCTF{honey.roasted.peanuts}

## Notas Adicionales

## Referencias
