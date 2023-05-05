## Descripción
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.

## Pistas 
What does a SQL database contain?
R= tablas

## Solución
```
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 63548 -U postgres pico
Password for user postgres: 
psql (15.2 (Debian 15.2-1))
Type "help" for help.

pico-# \dt

         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# SELECT * FROM PUBLIC.FLAGS;

 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

```

## Bandera
picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}

## Notas Adicionales
El comando \\dt muestra todas las tablas en una base de datos PostgreSQL.

## Referencias
https://stackoverflow.com/questions/47115227/what-does-run-the-command-dt-mean#:~:text=%5Cdt%20lists%20all%20tables%20in%20a%20PostgreSQL%20database.&text=Access%20psql%20from%20your%20terminal,to%20access%20a%20particular%20database