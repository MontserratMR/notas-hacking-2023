## Descripción
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm) has extraordinarily helpful information...

## Pistas 
1. This program will only work in the webshell or another Linux computer.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm`
3. Run this program by entering the following in the Terminal prompt: `$ ./warm`, but you'll first have to make it executable with `$ chmod +x warm`
4. -h and --help are the most common arguments to give to programs to get more information from them!
5. Not every program implements help features like -h and --help.

## Solución

```
dnightshade-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm
--2023-03-26 00:38:19--  https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                                       100%[=======================================================================================================================================>]  10.68K  --.-KB/s    in 0s      

2023-03-26 00:38:19 (467 MB/s) - 'warm' saved [10936/10936]

dnightshade-picoctf@webshell:~$ chmod +x warm
dnightshade-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
dnightshade-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}
```

## Bandera
picoCTF{b1scu1ts_4nd_gr4vy_616f7182}

## Notas Adicionales

## Referencias
