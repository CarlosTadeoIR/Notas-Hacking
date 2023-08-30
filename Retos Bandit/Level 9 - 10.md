# Level 9 - 10 
---

## Objetivo 

The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit9**
Pasword : **EN632PlfYiZbn3PhVK3XOGSlNInNE00t**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```

**Después se hace lo siguiente en la consola**

```bash
ls
# data.txt
file data.txt
# data.txt: data
strings data.txt | grep ==
# 4========== the#
# ========== password
# ========== is
# ========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

**Resultado final**

```
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```


---
## Notas Adicionales 
|**Comando** | **Descripción** |
|:---------:|:-------------|
| strings | muestra las secuencias de caracteres imprimibles que sean de al menos 4 caracteres de largo|
| Grep | busca una palabra o patrón que definamos en un archivo de texto y se imprimirá la línea o líneas que la contengan |

en este caso la secuencia para encontrar la respuesta era mediante el uso de (= =)

---
## Referencias 

[▷ Cómo usar el comando strings en Linux - ResponTodo](https://respontodo.com/como-usar-el-comando-strings-en-linux/#Usando_el_comando_strings)

