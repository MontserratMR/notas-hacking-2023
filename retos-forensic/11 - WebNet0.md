## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Pistas 
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?

## Solución
* Abrimos el paquete con wireshark. Si tratamos de seguir el stream TLS, no lo vamos a entender, está encriptado, tenemos que cargar la llave privada primero.
* Edición - Preferencias - Protocolos - TLS - RSA keys list - Llave
* Edición - Find Next - Packet details - String - picoCTF
* Y en los detalles del paquete no. 32 tenemos la bandera.

## Bandera
picoCTF{nongshim.shrimp.crackers}

## Notas Adicionales

**What is Transport Layer Security (TLS)?**

Transport Layer Security, or TLS, is a widely adopted security protocol designed to facilitate privacy and data security for communications over the Internet. A primary use case of TLS is encrypting the communication between web applications and servers, such as web browsers loading a website. TLS can also be used to encrypt other communications such as email, messaging, and voice over IP (VoIP).

## Referencias
https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/#:~:text=Transport%20Layer%20Security%2C%20or%20TLS,web%20browsers%20loading%20a%20website.