## Descripción
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).

## Pistas 
caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

## Solución

```
dnightshade-picoctf@webshell:~$ cat ciphertext
picoCTF{gvswwmrkxlivyfmgsrhnrisegl}
```

Utilizando una herramienta como cyberchef rotamos tantas veces sea necesario hasta llegar a una cadena que tenga sentido. En mi caso fue 22 veces.

## Bandera
picoCTF{crossingtherubicondjneoach}

## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,22)&input=e2d2c3d3bXJreGxpdnlmbWdzcmhucmlzZWdsfQ