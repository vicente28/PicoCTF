# SQL Direct

## Objetivos
Connect to this PostgreSQL server and find the flag!


## Solución 
```bash
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 60234 -U postgres pico
Password for user postgres: 
psql (14.5 (Debian 14.5-1), server 14.2 (Debian 14.2-1.pgdg110+1))
Type "help" for help.

pico=# show tables;
ERROR:  unrecognized configuration parameter "tables"
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=# 

```

## Notas adicionales 
https://www.postgresqltutorial.com/postgresql-administration/postgresql-show-tables/
