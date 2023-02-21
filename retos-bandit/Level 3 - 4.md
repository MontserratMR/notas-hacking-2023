## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

## Datos Acceso
bandit3 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Solución
```
bandit3@bandit:~$ ls 
inhere 
bandit3@bandit:~$ cd inhere/ 
bandit3@bandit:~/inhere$ ls 
bandit3@bandit:~/inhere$ ls -la 
total 12 
drwxr-xr-x 2 root root 4096 Jan 11 19:19 . 
drwxr-xr-x 3 root root 4096 Jan 11 19:19 .. 
-rw-r----- 1 bandit4 bandit3 33 Jan 11 19:19 .hidden bandit3@bandit:~/inhere$ cat .hidden 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe bandit3@bandit:~/inhere$
```

## Notas Adicionales
Para ver los archivos ocultos, ejecuta el comando **ls** con la opción  **-a**, que permite ver todos los archivos en un directorio o el indicador **-la** para obtener una lista larga de archivos.

## Referencias
[“An easy way to hide files and  directories in Linux”](https://www.tecmint.com/hide-files-and-directories-in-linux/#:~:text=How%20to%20View%20Hidden%20Files,a%20long%20listing%20of%20files.&text=From%20a%20GUI%20file%20manager,view%20hidden%20files%20or%20directories).