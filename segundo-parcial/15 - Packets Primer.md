## Descripción
Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/195/network-dump.flag.pcap)

## Pistas 
Wireshark, if you can install and use it, is probably the most beginner friendly packet analysis software product.

## Solución

Abrimos el archivo pcap con wireshark
```
┌──(kali㉿kali)-[~]
└─$ wireshark network-dump.flag.pcap  
```
Click derecho en el primer paquete > Follow > TCP Stream
```
p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ b 9 d 5 3 7 6 5 }
```

## Bandera
picoCTF{p4ck37_5h4rk _b9d53765}

## Notas Adicionales
Wireshark provides the feature of reassembling a stream of plain text protocol packets into a human-readable format

For instance, assembling an HTTP session will display the GET requests sent from the client and the responses received from the server. There is specific color coding that is followed by the request and response messages shown in the Follow TCP Stream dialog. Client requests are shown in red, and any text in blue denotes the response received from the server.

## Referencias
https://www.oreilly.com/library/view/wireshark-2-quick/9781789342789/d6185a39-0580-4b7f-b393-16b339b3ba37.xhtml#:~:text=Wireshark%20provides%20the%20feature%20of,responses%20received%20from%20the%20server.