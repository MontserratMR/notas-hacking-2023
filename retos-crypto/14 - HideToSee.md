## Descripción
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/237/atbash.jpg).

## Pistas 
Download the image and try to extract it.

## Solución
```
┌──(kali㉿kali)-[~]
└─$ steghide extract -sf atbash.jpg
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                            
┌──(kali㉿kali)-[~]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_05y2z65z}

```

- Después de utilizar una herramienta llamada "Atbash cipher" tenemos la bandera: 
## Bandera
picoCTF{atbash_crack_05b2a65a}

## Referencias
https://www.dcode.fr/atbash-cipher