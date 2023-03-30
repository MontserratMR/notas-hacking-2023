# Descripcion
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/260/flag.png).


# Pistas

# Solucion
```
┌──(kali㉿kali)-[~/PicoCTF2023]
└─$ mkdir hideme             
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/PicoCTF2023]
└─$ cd hideme 
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/PicoCTF2023/hideme]
└─$ wget https://artifacts.picoctf.net/c/260/flag.png  
--2023-03-28 00:10:25--  https://artifacts.picoctf.net/c/260/flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 99.84.203.115, 99.84.203.9, 99.84.203.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|99.84.203.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43005 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                                                   100%[========================================================================================================================================>]  42.00K  --.-KB/s    in 0.07s   

2023-03-28 00:10:26 (613 KB/s) - ‘flag.png’ saved [43005/43005]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/PicoCTF2023/hideme]
└─$ open flag.png  
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/PicoCTF2023/hideme]
└─$ unzip flag.png 
Archive:  flag.png
warning [flag.png]:  39739 extra bytes at beginning or within zipfile
  (attempting to process anyway)
   creating: secret/
  inflating: secret/flag.png         
                                                                                  
┌──(kali㉿kali)-[~/PicoCTF2023/hideme]
└─$ ls
flag.png  secret
                                                                                  
┌──(kali㉿kali)-[~/PicoCTF2023/hideme]
└─$ cd secret 
                                                                                  
┌──(kali㉿kali)-[~/PicoCTF2023/hideme/secret]
└─$ ls
flag.png
                                                                                  
┌──(kali㉿kali)-[~/PicoCTF2023/hideme/secret]
└─$ open flag.png

picoCTF{Hiddinng_An_imag3_within_@n_ima9e_ad9f6587}
```

# Bandera
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_ad9f6587}

# Notas adicionales
Para la solución de este reto se hizo la descarga del  archivo proporcionado en el reto, enseguida se mandan abrir con el comando open, se observa que es un archivo .png pero se encuentra comprimido , para lo cual con ayuda del comado unzip se manda descomprimir, con el comando ls se observa que es lo que contiene, dentro de el se encuentra otra carpeta, nuevamente se observa que hay dentro de ella y ahí se encuentra un archivo .png, se manda abrir  con un open  y es así como se obtiene la bandera de este reto.

# Referencias



