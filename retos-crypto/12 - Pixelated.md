## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)

## Pistas 
1. [https://en.wikipedia.org/wiki/Visual_cryptography](https://en.wikipedia.org/wiki/Visual_cryptography)
2. Think of different ways you can "stack" images

## Solución

Utilizamos una herramienta llamada stegsolve para fusionar las dos imágenes que nos dieron
```
┌──(kali㉿kali)-[~]
└─$ sudo chmod +x stegsolve.jar                          
[sudo] password for kali: 
                                                                                            
┌──(kali㉿kali)-[~]
└─$ java -jar stegsolve.jar
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

```
![[Pasted image 20230502193040.png]]

## Bandera
picoCTF{2a4d45c7}

## Notas Adicionales
In this example, the image has been split into two component images. Each component image has a _pair_ of pixels for every pixel in the original image. These pixel pairs are shaded black or white according to the following rule: if the original image pixel was black, the pixel pairs in the component images must be complementary; randomly shade one ■□, and the other □■. When these complementary pairs are overlapped, they will appear dark gray. On the other hand, if the original image pixel was white, the pixel pairs in the component images must match: both ■□ or both □■. When these matching pairs are overlapped, they will appear light gray.

So, when the two component images are superimposed, the original image appears. However, without the other component, a component image reveals no information about the original image; it is indistinguishable from a random pattern of ■□ / □■ pairs. Moreover, if you have one component image, you can use the shading rules above to produce a _counterfeit_ component image that combines with it to produce any image at all.

