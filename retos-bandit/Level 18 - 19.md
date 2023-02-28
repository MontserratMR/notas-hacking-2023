## Objetivo
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Datos Acceso
bandit18
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solución
```
ssh bandit18@bandit.labs.overthewire.org -p 2220
...
...
Byebye !
Connection to bandit.labs.overthewire.org closed.
>> Forma 1
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
_ _ _ _
| |__ __ _ _ __ __| (_) |_
| '_ \ / _` | '_ \ / _` | | __|
| |_) | (_| | | | | (_| | | |_
|_.__/ \__,_|_| |_|\__,_|_|\__|
This is an OverTheWire game server.
More information on
http://www.overthewire.org/wargames
bandit18@bandit.labs.overthewire.org's password:
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

>> Forma 2
ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash
_ _ _ _
| |__ __ _ _ __ __| (_) |_
| '_ \ / _` | '_ \ / _` | | __|
| |_) | (_| | | | | (_| | | |_
|_.__/ \__,_|_| |_|\__,_|_|\__|
This is an OverTheWire game server.
More information on
http://www.overthewire.org/wargames
bandit18@bandit.labs.overthewire.org's password:
cat readme
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

## Notas Adicionales
Dado que la contraseña de bandit19 se almacena en el archivo readme, agregue cat readme después de -p 2220 para iniciar sesión y mostrar el contenido del archivo readme antes de desconectarse nuevamente.
En la segunda forma, se está haciendo uso de una  [pseudo-terminal](https://renenyffenegger.ch/notes/development/misc/pseudo-terminal)

## Referencias

