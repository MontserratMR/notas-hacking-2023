## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**

## Datos Acceso
bandit7 
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Solución
```
bandit7@bandit:~$ ls 
data.txt 
bandit7@bandit:~$ wc data.txt 
98567 197133 4184396 data.txt 
bandit7@bandit:~$ grep millionth data.txt 
millionth TESKZC0XvTetK0S9xNwm25STk5iWrBvP bandit7@bandit:~$ cat data.txt | grep millionth 
millionth TESKZC0XvTetK0S9xNwm25STk5iWrBvP 
```

## Notas Adicionales
|comando|descripción|
|---|---|
|grep| sirve para buscar algún patrón en un archivo|
| wc | word count
| pipe* | Permite usar do so más comandos de modo que la salida un comando sirva como entrada para el siguiente. La salida de cada proceso directamente como entrada al siguiente

## Referencias
[grep](https://man7.org/linux/man-pages/man1/grep.1.html)
[Pipe, Grep and Sort Command in Linux/Unix with Examples](https://www.guru99.com/linux-pipe-grep.html#:~:text=is%20a%20Filter%3F-,What%20is%20a%20Pipe%20in%20Linux%3F,'%7C'%20denotes%20a%20pipe.)