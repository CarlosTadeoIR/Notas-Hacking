# Level 4 - 5
---

## Objetivo 

The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit4**
Pasword : **2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

**Después se hace lo siguiente en la consola**

``` bash
ls
# inhere
cd inhere/
ls
# -file00  -file02  -file04  -file06  -file08
# -file01  -file03  -file05  -file07  -file09
cat ./-file00
'ŰBηb<QȠ+ViO1[5{bandit4@bandit:~/inhere$' file ./-file00
# ./-file00: data

file ./*

# ./-file00: data
# ./-file01: data
# ./-file02: data
# ./-file03: data
# ./-file04: data
# ./-file05: data
# ./-file06: data
# ./-file07: ASCII text
# ./-file08: data
# ./-file09: Non-ISO extended-ASCII text, with no line terminators

cat ./-file07
# lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

```

**Resultado final**

```
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

---
## Notas Adicionales 
cuando se muestra el contenido del archivo (-file00 ) este parece estar mal, pero en verdad se accede a ver lo que tiene aunque el documento sea tipo (data). Por eso usado el comando <span style="color:blue">file</span> permite ver el tipo de archivo, para no hacer esto de forma manual se usa el ( * ) para que el comando se efectué para todos los archivos, de esta forma podremos ver cual es el archivo que nos interesa.

---
## Referencias 

[file(1) - Linux manual page (man7.org)](https://man7.org/linux/man-pages/man1/file.1.html)

