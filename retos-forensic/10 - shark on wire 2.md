## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Pistas 
None

## Solución
* Nos dan una captura de paquetes con poca descripción de lo que debemos buscar. Mientras miraba a través de los flujos UDP, encontré dos paquetes con el inicio y el final del texto en la sección de datos:
paquete 1104:
![[Pasted image 20230329112326.png]]
paquete 1303:
![[Pasted image 20230329112414.png]]

Los únicos bytes que cambiaron entre el paquete de inicio (#1104) y el siguiente paquete UDP (#1106) fueron el campo de datos, las sumas de verificación y el puerto de origen. La diferencia entre los puertos de origen de estos dos paquetes (5112 - 5000 = 112) es código ASCII de la letra p. Repetimos esto para todos los paquetes UDP (excluyendo consultas MDNS) y encontramos los siguientes números:
```
112 97 97 97 97 97 105 99 111 67 84 70 123 112 49 76 76 102 51 97 97 97 97 97 114 51 100 97 97 95 97 100 97 97 116 97 95 118 49 97 95 115 116 97 97 97 51 103 97 97 97 97 48 125
```
Unicamente lo cambiamos cambiamos a texto y tenemos la bandera. 

## Bandera
picoCTF{p1LLf3r3data_v1a_st3g0}

## Notas Adicionales

## Referencias
https://photo333.com/ascii-to-text-es.php