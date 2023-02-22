## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

## Datos Acceso
bandit14 
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

## Solución
```
bandit14@bandit:~$ 
bandit14@bandit:~$ nc localhost 30000 fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq 
Correct! 
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt 

^C 
bandit14@bandit:~$
```

## Notas Adicionales
|comando|descripción|opciones|man|
|---|---|---|---|
	|nc| se utiliza para leer y escribir datos entre dos redes informática| en Connect mode, netcat funciona como un cliente. Requiere host y port.|[nc](https://linux.die.net/man/1/nc)

## Referencias
-   [How the Internet works in 5 minutes (YouTube)](https://www.youtube.com/watch?v=7_LPdttKXPc) 
-   [IP Addresses](http://computer.howstuffworks.com/web-server5.htm)
-   [IP Address on Wikipedia](https://en.wikipedia.org/wiki/IP_address)
-   [Localhost on Wikipedia](https://en.wikipedia.org/wiki/Localhost)
-   [Ports](http://computer.howstuffworks.com/web-server8.htm)
-   [Port (computer networking) on Wikipedia](https://en.wikipedia.org/wiki/Port_(computer_networking))