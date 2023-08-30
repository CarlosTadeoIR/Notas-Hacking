# Level 8 - 9 
---

## Objetivo 

The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit8**
Pasword : **TESKZC0XvTetK0S9xNwm25STk5iWrBvP**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```

**Después se hace lo siguiente en la consola**

```bash
ls
# data.txt
wc data.txt
# 1001  1001 33033 data.txt
cat data.txt | sort | uniq -u
# EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

**Resultado final**

```
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```


---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| uniq | filtra texto duplicado |
| sort |organiza las líneas de texto de forma útil, en este caso es en orden alfabetico|

---
## Referencias 

[Comando Uniq en Unix y Linux: 7 ejemplos esenciales (linuxhandbook.com)](https://linuxhandbook.com/uniq-command/)
[Ordenar por columna en Bash (linuxhandbook.com)](https://linuxhandbook.com/sort-by-column/)
