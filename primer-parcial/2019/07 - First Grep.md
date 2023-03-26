## Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Pistas 
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solución
Primero descargamos el archivo desde la terminal con "wget *archivo*".
Al momento de aplicar el comando "cat" para imprimir su contenido nos topamos con una serie extensa de caracteres, es ahí donde entra el comando "grep".

```
dnightshade-picoctf@webshell:~$ egrep 'picoCTF' file
picoCTF{grep_is_good_to_find_things_5af9d829}
```

## Bandera
picoCTF{grep_is_good_to_find_things_5af9d829}

## Notas Adicionales
egrep es un programa que buscará un conjunto dado de datos e imprimirá cada línea que contenga un patrón dado.
## Referencias
