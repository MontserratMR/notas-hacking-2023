## Descripción
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Pistas 
The flag is in the format PICOCTF{}

## Solución
Abrimos el archivo png y vemos lo siguiente:
![[the_numbers.png]]

- Como tiene las llaves {} y un conjunto de siete números, nos damos cuenta que tiene formato de una bandera. Corresponde a la posición de la letra en el alfabeto (en inglés).
- Lo que tenemos que hacer es, con ayuda de una herramienta como cyberchef, decodificarlo de A1Z26.

## Bandera
picoCTF{thenumbersmason}

## Referencias
https://gchq.github.io/CyberChef/#recipe=A1Z26_Cipher_Decode('Space')&input=MjAtIDgtIDUtIDE0LSAyMS0gMTMtIDItIDUtIDE4LSAxOS0gMTMtIDEtIDE5LSAxNS0gMTQK