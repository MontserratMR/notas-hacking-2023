## Descripción
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py)

## Pistas 
1. Are equality and assignment the same symbol?
2. To view the file in the webshell, do: `$ nano fixme2.py`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Es básicamente el mismo proceso que el reto anterior.
En esta ocasión lo que está mal con el código es que en en la línea con el if "if flag ="":" está usando un solo signo de igual, lo que hace es asignar un valor no compararlo. Agregamos otro = y tenemos la bandera.
```
dnightshade-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/4/fixme2.py
--2023-03-26 02:28:43--  https://artifacts.picoctf.net/c/4/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.120, 108.156.172.6, 108.156.172.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.120|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                    100%[=============================================>]   1.00K  --.-KB/s    in 0s      

2023-03-26 02:28:43 (757 MB/s) - 'fixme2.py' saved [1029/1029]

dnightshade-picoctf@webshell:~$ nano fixme2.py

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5>

  
flag = str_xor(flag_enc, 'enkidu')

# Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)

dnightshade-picoctf@webshell:~$ python fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```



## Bandera
picoCTF{}
## Notas Adicionales

## Referencias
