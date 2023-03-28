## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Pistas 
1. Try using a tool like Wireshark
2. What are streams?

## Solución
Descargamos el archivo y lo vamos a analizar con wireshark. Wireshark es un analizador de paquetes gratuito y de código abierto. Se utiliza para la solución de problemas de red, el análisis, el desarrollo de protocolos de comunicación y software.
```
──(kali㉿kali)-[~/Desktop/pico]
└─$ file capture.pcap
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                                   
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ wireshark capture.pcap

```
Una vez ahí, seleccionamos cualquier paquete dentro del stream y nos abre una ventana con la información que va transfiriendo, en la cual podemos ir cambiándonos de **stream.** En el 6° encontramos la bandera. 
## Bandera
picoCTF{StaT31355_636f6e6e}

## Notas Adicionales

**What is PCAP?**
Packet Capture or PCAP (also known as libpcap) is an application programming interface (API) that captures live network packet data from OSI model Layers 2-7. Network analyzers like Wireshark create .pcap files to collect and record packet data from a network. PCAP comes in a range of formats including Libpcap, WinPcap, and PCAPng.

These PCAP files can be used to view TCP/IP and UDP network packets. If you want to record network traffic then you need to create a .pcapfile. You can create a .pcapfile by using a network analyzer or packet sniffing tool like Wireshark or tcpdump. In this article, we’re going to look at what PCAP is, and how it works.

Stream: Los flujos de red son un método de comunicación dinámico, estrechamente integrado y fácil de configurar para transferir datos de una aplicación a otra con características de rendimiento y latencia comparables con TCP.

## Referencias
https://www.comparitech.com/net-admin/pcap-guide/

https://en.wikipedia.org/wiki/Wireshark

https://www.ni.com/es-mx/innovations/white-papers/10/lossless-communication-with-network-streams--components--archite.html