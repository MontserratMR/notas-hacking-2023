## Objetivo
The password for the next level is stored in a file called **-** located in the home directory
## Datos Acceso
bandit1 
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
## Solución
```
bandit1@bandit:~$ ls - 
bandit1@bandit:~$ cat - ^C 
bandit1@bandit:~$ cat ./- 
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi 
bandit1@bandit:~$ pwd 
/home/bandit1 
bandit1@bandit:~$ cat /home/bandit1/- rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi 
```
## Notas Adicionales
|comando|descripción|opciones|
|---|---|---|
|cat | concatena archivos e imprime en salida estandar
|file| determina el tipo de archivo
|du| estima el uso de espacio del archivo
|find| Busca archivos en una jerarquía de directorios

## Referencias
[Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)