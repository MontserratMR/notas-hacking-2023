## Descripción
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)

## Pistas 
1. Indentation is very meaningful in Python
2. To view the file in the webshell, do: `$ nano fixme1.py`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución

```
dnightshade-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/27/fixme1.py
--2023-03-26 02:14:23--  https://artifacts.picoctf.net/c/27/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.42, 108.156.172.6, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py.1'

fixme1.py.1                  100%[=======================>]     837  --.-KB/s    in 0s      

2023-03-26 02:14:23 (39.7 MB/s) - 'fixme1.py.1' saved [837/837]
dnightshade-picoctf@webshell:~$ nano fixme1.py 
```
En la última línea del código hay un tabulador de más, lo eliminamos y guardamos el archivo.
```
dnightshade-picoctf@webshell:~$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
```
## Bandera
picoCTF{1nd3nt1ty_cr1515_182342f7}
## Notas Adicionales

## Referencias
