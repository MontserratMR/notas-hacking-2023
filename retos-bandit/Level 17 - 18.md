## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

## Datos Acceso
bandit17 - {llave privada} o VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

## Solución
```
bandit17@bandit:~$ ls -la
total 36
drwxr-xr-x 3 root root 4096 Sep 1 06:30 .
drwxr-xr-x 49 root root 4096 Sep 1 06:30 ..
-rw-r----- 1 bandit17 bandit17 33 Sep 1 06:30 .bandit16.password
-rw-r--r-- 1 root root 220 Jan 6 2022 .bash_logout
-rw-r--r-- 1 root root 3771 Jan 6 2022 .bashrc
-rw-r----- 1 bandit18 bandit17 3300 Sep 1 06:30 passwords.new
-rw-r----- 1 bandit18 bandit17 3300 Sep 1 06:30 passwords.old
-rw-r--r-- 1 root root 807 Jan 6 2022 .profile
drwxr-xr-x 2 root root 4096 Sep 1 06:30 .ssh
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ exit
```

## Notas Adicionales
**diff** es una utilidad de línea de comandos que le permite comparar dos archivos línea por línea.
La utilidad diff --color compara dos archivos e imprime líneas únicas para cada archivo. Al igual que diff, la herramienta brinda instrucciones sobre cómo hacer que los archivos sean idénticos. Las instrucciones son más intuitivas y fáciles de entender porque diff --color resalta las líneas que el usuario debe agregar o eliminar para obtener dos archivos idénticos.

## Referencias
 [How to Use diff --color to Change the Color of the Output](https://phoenixnap.com/kb/diff-color)