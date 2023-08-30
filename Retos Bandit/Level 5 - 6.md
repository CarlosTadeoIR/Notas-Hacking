# Level 5 - 6
---
## Objetivo 
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit5**
Pasword : **lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR**
Puerto  : 2220 
```
---
## Solución 
**Primero se accede al servidor**
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

**Después se hace lo siguiente en la consola**

``` bash
ls
# inhere
cd inhere/
ls
# maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
# maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
# maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
# maybehere03  maybehere07  maybehere11  maybehere15  maybehere19

find . -readable -type f -size 1033c
# ./maybehere07/.file2
cat ./maybehere07/.file2
# P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

**Resultado final**

```
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

---
## Notas Adicionales 

|**Parámetro de búsqueda para "find"** | **Descripción** |
|:---------:|:-------------|
|-name, -iname | Filtrar por nombre de archivo
|-type | Filtrar por tipo de archivo
|-size, -empty | Filtrar por tamaño de archivo
|-ctime, -mtime, -atime | Filtrar por marca de tiempo
|-user, -group | Filtrar por propietario y grupo
|-perm | Filtrar por derechos de archivo
|-and | Los resultados de la búsqueda deben cumplir ambas condiciones
|-or | Los resultados de la búsqueda deben cumplir al menos una de las dos condiciones
|-not | Negar la condición posterior



---
## Referencias 

[Linux find | Cómo usar el comando find de Linux - IONOS](https://www.ionos.es/digitalguide/servidores/configuracion/comando-linux-find/)


