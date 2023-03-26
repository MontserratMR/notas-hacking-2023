## Descripción
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag).

## Pistas 
1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag`
3. $ man cat

## Solución

```
dnightshade-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag  100%[=============>]      34  --.-KB/s    in 0s      

2023-03-26 00:31:22 (18.2 MB/s) - 'flag' saved [34/34]

dnightshade-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}

```

## Bandera
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}

## Notas Adicionales

## Referencias
