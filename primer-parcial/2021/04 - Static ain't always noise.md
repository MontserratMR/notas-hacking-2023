## Descripción
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static)? This [BASH script](https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/ltdis.sh) might help!

## Pistas 

## Solución
El comando strings imprime las cadenas de caracteres imprimibles en los archivos.
```
dnightshade-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
--2023-03-26 01:16:25--  https://mercury.picoctf.net/static/66932732825076cad4ba43e463dae82f/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                       100%[=============================================>]   8.18K  --.-KB/s    in 0s      

2023-03-26 01:16:25 (285 MB/s) - 'static' saved [8376/8376]

dnightshade-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_f5aeda17}
```

## Bandera
picoCTF{d15a5m_t34s3r_f5aeda17}

## Notas Adicionales

## Referencias
