## Descripción
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!

## Pistas 
Seems like the password is encrypted.

## Solución
Al inspeccionar el código vemos que el parámetro "debug" tiene un valor de 0. Para acceder a la consulta lo cambiamos a 1. Si ponemos de contraseña: "holamundo" y damos enter, nos aparece en la página de LOGIN FAILED lo siguiente:
```
password: 
SQL query: SELECT * FROM admin where password = 'ubynzhaqb'
```
Lo cual podemos desencriptar usando una herramienta como CyberChef. Ahora sabemos que se está usando ROT13. Para inyectar sql (' or 1=1;)debemos de pasar la sentencia a ROT13 (' be 1=1;).
Una vez hayamos hecho eso, tenemos la bandera.

## Bandera
picoCTF{3v3n_m0r3_SQL_06a9db19}

## Referencias
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=JyBPUiAxPTE7