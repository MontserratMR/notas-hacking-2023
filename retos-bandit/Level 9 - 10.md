## Objetivo
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

## Datos Acceso
bandit9 
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Solución
```
bandit9@bandit:~$ ls data.txt 
bandit9@bandit:~$ file data.txt 
data.txt: data 
bandit9@bandit:~$ strings data.txt | grep == 
c========== the 
h;========== password ========== isT 
n.E========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

## Notas Adicionales
|comando|descripción|
|---|---|
|grep|sirve para buscar algún patrón en un archivo

## Referencias
[grep](https://man7.org/linux/man-pages/man1/grep.1.html)