## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg)

## Pistas 
1. Wait, you can hide files inside files? But how do you find them?
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
* Si abrimos la imagen podemos ver lo siguiente
![[Pasted image 20230331191227.png]]
* A simple vista no hay nada, pero si lo pasamos por un strings nos damos cuenta que ahí adentro hay algo más
```
wkwwG;~A
base_images/2_c.jpgUT*
Hr~&    8Ja7i,
t+Vp`B2AYq
```
* Así que, usando una herramienta llamada binwalk, nos podemos dar cuenta de que se trata de un archivo zip.
```

┌──(kali㉿kali)-[~/Desktop/pico]
└─$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22
```
+ Extraemos el contenido 
```
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                             
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ ls
dolls.jpg  _dolls.jpg.extracted  pasados
                                                                                             
┌──(kali㉿kali)-[~/Desktop/pico]
└─$ cd _dolls.jpg.extracted 
                                                                                             
┌──(kali㉿kali)-[~/Desktop/pico/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                             
┌──(kali㉿kali)-[~/Desktop/pico/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                             
┌──(kali㉿kali)-[~/Desktop/pico/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                             
┌──(kali㉿kali)-[~/Desktop/pico/_dolls.jpg.extracted/base_images]
└─$ open 2_c.jpg 
```
![[Pasted image 20230331192721.png]]
Tenemos otra Matryoshka más chiquita... repetimos el procedimiento
![[Pasted image 20230331193008.png]]
Hasta que llegamos a un archivo txt
```
──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 62, uncompressed size: 81, name: flag.txt
79784         0x137A8         End of Zip archive, footer length: 22

                                                                                             
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg  _4_c.jpg.extracted
                                                                                             
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                                             
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                             
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt         
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}
```

## Bandera
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}

## Notas Adicionales
Binwalk is **a command-line tool in Linux that is used to analyze and extract the contents of binary files**. It is commonly used to reverse engineer firmware images or other types of binary files to discover hidden or encoded data, such as bootloaders, kernel images, or filesystems.

## Referencias
https://www.thegeekdiary.com/binwalk-command-examples-in-linux/#:~:text=binwalk%20is%20a%20command%2Dline,%2C%20kernel%20images%2C%20or%20filesystems.