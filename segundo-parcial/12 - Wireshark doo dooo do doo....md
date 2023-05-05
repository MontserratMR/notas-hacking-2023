## Descripción
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/ae5b2bc07928fca272ff3900dc9a6cef/shark1.pcapng).

## Pistas 

## Solución
- Abrimos el archivo pcapng que nos proporcionaron.
- En el primer paquete damos click derecho > Follow > TCP Stream
- Nos vamos cambiando de stream hasta que salga algo parecido al formato de la bandera o con la palabra "pico" en ello.
- En el 5° hay algo en el último reglón que parece necesitar ser decodificado.
```
┌──(kali㉿kali)-[~]
└─$ wireshark shark1.pcapng                                                               
                             


(follow tcp stream)
...
Stream 5

HTTP/1.1 200 OK
Date: Mon, 10 Aug 2020 01:51:45 GMT
Server: Apache/2.4.29 (Ubuntu)
Last-Modified: Fri, 07 Aug 2020 00:45:02 GMT
ETag: "2f-5ac3eea4fcf01"
Accept-Ranges: bytes
Content-Length: 47
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/html


Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

```

- Lo pasamos al cyberchef y sabemos que está en ROT13.
- El mensaje decodificado dice: The flag is picoCTF{p33kab00_1_s33_u_deadbeef}
## Bandera
picoCTF{p33kab00_1_s33_u_deadbeef}

## Notas Adicionales
Pcapng

What is a PCAPNG file. PCAPNG files mostly belong to Wireshark by The Wireshark team. PCAPNG is **a format used to record captured network packet traces to a file**. It was designed to be an extensible successor to the original PCAP format used by tcpdump and other software using the libpcap library.

## Referencias
https://filext.com/file-extension/PCAPNG#:~:text=What%20is%20a%20PCAPNG%20file,software%20using%20the%20libpcap%20library.

https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=R3VyIHN5bnQgdmYgY3ZwYlBHU3tjMzN4bm8wMF8xX2YzM19oX3FybnFvcnJzfQ