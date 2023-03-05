## Objetivo
After all this `git` stuff its time for another escape. Good luck!

## Datos Acceso
bandit32
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

## Solución
```
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: not found
>> 0
sh: 1: 0: not found
>> $0
$ whoami
bandit33
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
$
```

## Notas Adicionales
El shell convierte cada comando en mayúsculas. Necesitamos arreglarlo y recuperar el shell normal de nuevo. Dado que este es un shell interactivo, tenemos la oportunidad de ejecutarlo nuevamente usando la variable $0.

Con el comando whoami nos damos cuenta que somos bandit 33 (no solo 32), por lo que podemos leer el archivo con las contraseña.

## Referencias
[# OverTheWire Bandit Level 32 - Level 33](https://www.youtube.com/watch?v=_z8JI2Dw800&list=PLG44s1Oo_jbTzrJ4kI24LwAyjFtTSDNlq&index=34)