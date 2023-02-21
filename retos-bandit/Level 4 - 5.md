## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

## Datos Acceso
bandit4 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Solución
```
bandit4@bandit:~$ ls 
inhere 
bandit4@bandit:~$ cd inhere/ 
bandit4@bandit:~/inhere$ ls 
-file00 -file02 -file04 -file06 -file08 -file01 -file03 -file05 -file07 -file09 
bandit4@bandit:~/inhere$ cat ./-file00 
TB#6Kt3 6Xt) bandit4@bandit:~/inhere$ bandit4@bandit:~/inhere$ file ./-file00 
./-file00: data 
bandit4@bandit:~/inhere$ file ./* 
./-file00: data ./-file01: data ./-file02: data ./-file03: data ./-file04: data ./-file05: data ./-file06: data ./-
file07: ASCII text
./-file08: data ./-file09: data 
bandit4@bandit:~/inhere$ cat ./-file07 lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR 
```

## Notas Adicionales

| comando|descripción|
|---|---|
| * | comodín que indica todos, ejemplo: file ./* aplica file a todos |
| File | Indica el tipo de archivo |

## Referencias
[file](https://man7.org/linux/man-pages/man1/file.1.html)