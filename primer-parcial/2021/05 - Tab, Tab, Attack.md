## Descripción
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip)

## Pistas 
After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

## Solución

Descargamos el archivo a la terminal web
Descomprimimos el archivo Addadshashanammu.zip y vemos que contiene directorios con nombres muy largos y un poco complicados, por lo que tenemos que usar el auto completado para cambiarnos de directorio, presionando Tab hasta donde sea posible. 
Finalmente vemos el tipo de archivo que nos queda. Como es un ejecutable usamos el comando ./*archivo* y tenemos la bandera.
```
dnightshade-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
--2023-03-26 01:31:40--  https://mercury.picoctf.net/static/72712e82413e78cc8aa8d553ffea42b0/Addadshashanammu.zip
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 4520 (4.4K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip         100%[=============================================>]   4.41K  --.-KB/s    in 0s      

2023-03-26 01:31:40 (2.59 GB/s) - 'Addadshashanammu.zip' saved [4520/4520]

dnightshade-picoctf@webshell:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
dnightshade-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt  bandera.py  file  flag  static  strings  warm
dnightshade-picoctf@webshell:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
dnightshade-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissir
alis/Ularradallaku$ ls
fang-of-haynekhtnamet
dnightshade-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissir
alis/Ularradallaku$ file fang-of-haynekhtnamet 
fang-of-haynekhtnamet: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b71f20bc162221a31840f68a978261097ecadac2, not stripped
dnightshade-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissir
alis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
```

## Bandera
picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}
## Notas Adicionales

## Referencias
