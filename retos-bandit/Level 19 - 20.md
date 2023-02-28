## Objetivo
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Datos Acceso
bandit19
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Solución
```
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x 2 root root 4096 Sep 1 06:30 .
drwxr-xr-x 49 root root 4096 Sep 1 06:30 ..
-rwsr-x--- 1 bandit20 bandit19 14872 Sep 1 06:30 bandit20-do
-rw-r--r-- 1 root root 220 Jan 6 2022 .bash_logout
-rw-r--r-- 1 root root 3771 Jan 6 2022 .bashrc
-rw-r--r-- 1 root root 807 Jan 6 2022 .profile
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$ exit
```

## Notas Adicionales
Setuid y Setgid son términos de Unix, abreviaturas para "Set User ID" y "Set Group ID", respectivamente. Setuid, también llamado a veces "suid", y "setgid" son permisos de acceso que pueden asignarse a archivos o directorios en un sistema operativo basado en Unix. Se utilizan principalmente para permitir a los usuarios del sistema ejecutar binarios con privilegios elevados temporalmente para realizar una tarea específica.

## Referencias
[setuid on Wikipedia](https://en.wikipedia.org/wiki/Setuid)