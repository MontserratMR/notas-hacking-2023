## Objetivo
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

## Datos Acceso
bandit0 
bandit0

## Solución
```
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

## Notas Adicionales

| comando | descripción| 
| --- | ---| 
| ls | Muestra los archivos  
| cat | Lee el contenido de un archivo 

## Referencias
[ls](https://man7.org/linux/man-pages/man1/ls.1.html) , [cat](https://man7.org/linux/man-pages/man1/cat.1.html)
