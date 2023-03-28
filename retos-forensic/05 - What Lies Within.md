## Descripción
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Pistas 
1. There is data encoded somewhere... there might be an online decoder.
## Solución
Si abrimos el archivo que nos da, es simplemente una imagen donde podemos ver algunos edificios.
Como la pista lo sugiere, recurrimos a una herramienta para decodificar la imagen.
Yo utilicé https://stylesuxx.github.io/steganography/.
Ingresamos el archivo y tenemos la bandera:
```
picoCTF{h1d1ng_1n_th3_b1t5}@  @ @  @@@@      @@@@@@@@@ @ @    @@@@ @@  @@ @ @ @@ 
```

## Bandera
picoCTF{h1d1ng_1n_th3_b1t5}

## Notas Adicionales
Steganography is **the practice of concealing information within another message or physical object to avoid detection**. Steganography can be used to hide virtually any type of digital content, including text, image, video, or audio content. That hidden data is then extracted at its destination.

## Referencias
[kaspersky.com/resource-center/definitions/what-is-steganography](https://www.kaspersky.com/resource-center/definitions/what-is-steganography)