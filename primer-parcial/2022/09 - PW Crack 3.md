## Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas 
1. To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
2. To exit `bvi` type `:q` and press enter.
3. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
Descargamos los archivos y analizamos el código

```
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]
```

Hay 7 posibles contraseñas. Lo que hice fue probar una por una y, para mi buena suerte, era la última opción. 
```
dnightshade-picoctf@webshell:~$ python level3.py
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
```
## Bandera
picoCTF{m45h_fl1ng1ng_2b072a90}

## Notas Adicionales

## Referencias
