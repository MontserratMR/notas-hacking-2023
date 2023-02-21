## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

## Datos Acceso
bandit8 
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
## Solución
```
bandit8@bandit:~$ ls 
data.txt 
bandit8@bandit:~$ wc data.txt 
1001 1001 33033 data.txt 
bandit8@bandit:~$ cat data.txt | sort | uniq -u EN632PlfYiZbn3PhVK3XOGSlNInNE00t 
```
## Notas Adicionales
|comando|descripción|man|
|---|---|--|
|sort|ordena líneas de archivos de texto| [sort](https://man7.org/linux/man-pages/man1/sort.1.html)|
|uniq|reportar u omitir líneas repetidas| [uniq](https://man7.org/linux/man-pages/man1/uniq.1.html)
uniq -u, --unique solo imprime líneas únicas

## Referencias
[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)