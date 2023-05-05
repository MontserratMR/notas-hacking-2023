## Descripción
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:65352/).

## Pistas 
folders folders folders

## Solución
-  Click derecho > Inspeccionar > Fuentes
- Podemos ver que hay un directorio llamado "secret". Si accedemos a éste con http://saturn.picoctf.net:65352/secret/ después nos encontramos con otro llamado "hidden", repetimos el proceso y tenemos otro "superhidden" (http://saturn.picoctf.net:65352/secret/hidden/superhidden/).
- En el archivo html de índice encontramos la bandera
```
(índice)
<!DOCTYPE html>
<html>
  <head>
    <title></title>
    <link rel="stylesheet" href="mycss.css" />
  </head>

  <body>
    <h1>Finally. You found me. But can you see me</h1>
    <h3 class="flag">picoCTF{succ3ss_@h3n1c@10n_790d2615}</h3>
  </body>
</html>
```

## Bandera
picoCTF{succ3ss_@h3n1c@10n_790d2615}
