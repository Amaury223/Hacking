## Descripción
Connect to this PostgreSQL server and find the flag! `psql -h chatelaine.cylabacademy.net -p 20815 -U postgres pico`

Password is `postgres`
## Solución
```
Dark23-academy@webshell:~$ psql -h chatelaine.cylabacademy.net -p 20815 -U postgres pico
Password for user postgres: 

pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres


pico=# \d flags
                        Table "public.flags"
  Column   |          Type          | Collation | Nullable | Default 
-----------+------------------------+-----------+----------+---------
 id        | integer                |           | not null | 
 firstname | character varying(255) |           |          | 
 lastname  | character varying(255) |           |          | 
 address   | character varying(255) |           |          | 
Indexes:
    "flags_pkey" PRIMARY KEY, btree (id)
    
  pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | academy{L3arN_S0m3_5qL_t0d4Y_412c85d9}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia  
    
    

 academy{L3arN_S0m3_5qL_t0d4Y_412c85d9}
```
## Notas Adicionales
\dt Muestra las tablas de la base de datos. \d tabla Muestra las columnas y estructura de una tabla. SELECT * FROM tabla; Muestra todos los datos de una tabla. \l Muestra las bases de datos disponibles.
## Referencias
 `psql -h chatelaine.cylabacademy.net -p 20815 -U postgres pico`