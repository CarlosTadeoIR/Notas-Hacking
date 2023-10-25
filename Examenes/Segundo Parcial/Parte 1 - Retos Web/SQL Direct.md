## Objetivo 

Connect to this PostgreSQL server and find the flag!
Additional details will be available after launching your challenge instance.

---
## Datos de acceso al nivel 

```
server   : psql -h saturn.picoctf.net -p 53170 -U postgres pico 
password : postgres
```

---
## Solución 

**Primero se accede al servidor**
```
psql -h saturn.picoctf.net -p 53170 -U postgres pico
```

**Contraseña de usuario**
```
postgres
```

**Después se hace lo siguiente en la consola**

lo primero que se hace es listar la base de datos para eso se usa el comando `\l` 

```sql

pico=# \l

List of databases
   Name    |  Owner   | Encoding |  Collate   |   Ctype    | ICU Locale | Locale Provider |   Access privileges   
-----------+----------+----------+------------+------------+------------+-----------------+-----------------------
 pico      | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
(4 rows)

```

para acceder a la base de datos pico se usa el comando `\c` + `Nombre de la base` en este caso el comando completo seria  `\c pico`

```sql
pico=# \c pico
psql (15.3 (Debian 15.3-0+deb12u1), server 15.2 (Debian 15.2-1.pgdg110+1))
You are now connected to database "pico" as user "postgres".

```

cuando accedemos a la base de datos pico lo siguiente es ver las tablas que tenga la base de datos para ello usamos el comando `\dt`

```sql 
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)
```

por ultimo usamos una consulta sencilla sobre la base de datos para consultar toda la información de la tabla flags 

```sql 
pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)
```

**Resultado Final**
```
picoCTF{L3arN_S0m3_5qL_t0d4Y_73b0678f}
```

---
## Notas Adicionales 

---
## Referencias 
https://www.commandprompt.com/education/postgresql-basic-psql-commands/

