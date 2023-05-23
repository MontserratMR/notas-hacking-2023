## Descripción
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

## Pistas 

## Solución
- Nos proporcionan el siguiente texto:
```
┌──(kali㉿kali)-[~]
└─$ cat message.txt 
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)} 
```
Parecen ser  coordenadas geográficas, correspondientes a:
- Kyoto, Japon
- Odessa, Ukrania
- Dayton, Estados Unidos
- Istanbul, Turquía
- Abu Dhabi, UAE
- Kuala Lampur, Malaysia
- Addis Ababa, Ethiopia
- Loja, Ecuador
- Amsterdam, Netherlands
- Sleepy Hollow, Estados Unidos
- Kodiak, Estados Unidos
- Alexandria, Egipto

Al observar la secuencia de ciudades y países, puede parecer aleatorio, pero si intentamos, por ejemplo, elegir la primera letra de cada ciudad, obtenemos lo siguiente: KODIAKALASKA 

## Bandera
picoCTF{KODIAK_ALASKA}

## Notas Adicionales

## Referencias
