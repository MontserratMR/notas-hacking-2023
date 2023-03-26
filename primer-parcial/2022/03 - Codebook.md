## Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

## Pistas 
1. On the webshell, use `ls` to see if both files are in the directory you are in
2. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
```
dnightshade-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2023-03-26 02:07:09--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.42, 108.156.172.6, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                      100%[=============================================>]   1.25K  --.-KB/s    in 0s      

2023-03-26 02:07:09 (610 MB/s) - 'code.py' saved [1278/1278]

dnightshade-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2023-03-26 02:07:21--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.156.172.74, 108.156.172.42, 108.156.172.120, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.156.172.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                 100%[=============================================>]      27  --.-KB/s    in 0s      

2023-03-26 02:07:22 (13.5 MB/s) - 'codebook.txt' saved [27/27]

dnightshade-picoctf@webshell:~$ ls
Addadshashanammu      README.txt  code.py       convertme.py  flag      static   warm
Addadshashanammu.zip  bandera.py  codebook.txt  file          runme.py  strings
dnightshade-picoctf@webshell:~$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
```

## Bandera
picoCTF{c0d3b00k_455157_197a982c}

## Notas Adicionales

## Referencias
