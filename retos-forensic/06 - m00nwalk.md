## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

## Pistas 
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option
3. 
## Solución
* Instalamos el qsstv.
* La mascota de cmu es Scotty the Scottie Dog, lo que los indica que tenemos que seleccionar el modo "Scottie 1".
* En este punto, podemos hacer clic en el botón "Reproducir" en QSSTV para iniciar el receptor y luego reproducir el archivo de audio:
```
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ paplay -d virtual-cable message.wav 
```
después de que el programa procesa el audio, nos muestra una imagen con la bandera volteada, simplemente la ponemos en la dirección correcta.

## Bandera
picoCTF{beep_boop_im_in_space}

## Notas Adicionales
La televisión de exploración lenta (SSTV) es un método de transmisión de imágenes utilizado principalmente por radioaficionados para transmitir y recibir imágenes estáticas por radio en monocromo o en color. Las cámaras de televisión del Apolo utilizaron SSTV para transmitir imágenes desde el interior del Apolo 7, el Apolo 8 y el Apolo 9, así como la televisión del Módulo Lunar del Apolo 11 desde la Luna.
[This tutorial](https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04)  explica cómo usar un programa llamado qsstv para convertir los archivos de audio a imágenes.

## Referencias
https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04
