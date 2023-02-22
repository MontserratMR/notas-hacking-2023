# Level X
## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

## Datos Acceso
bandit10 
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
```
bandit10@bandit:~$ ls 
data.txt 
bandit10@bandit:~$ cat data.txt VGhlIHBhc3N3b3JkIGlzIElGdWt3S0dzRlc4TU9xM0lSRnFyeEUxaHhUTkViVVBSCg== 
bandit10@bandit:~$ echo "hola mundo" 
hola mundo 
bandit10@bandit:~$ echo "hola mundo" | base64 aG9sYSBtdW5kbwo= 
bandit10@bandit:~$ echo -n aG9sYSBtdW5kbwo= | base64 -d hola mundo 
bandit10@bandit:~$ base64 -d data.txt 
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR bandit10@bandit:~$ bandit10@bandit:~$ cat data.txt VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg== 
bandit10@bandit:~$ cat data.txt | base64 -d 
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

## Notas Adicionales
|comando|descripción|opciones|man|
|---|---|---|---|
|base64|es un grupo de esquemas de codificación de binario a texto que representan datos binarios en secuencias de 24 bits que se pueden representar mediante cuatro dígitos Base64 de 6 bits|-d Decodificar información| [base64](https://linux.die.net/man/1/base64)

## Referencias
[Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)