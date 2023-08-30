# Level 7 - 8
---

## Objetivo 

The password for the next level is stored in the file **data.txt** next to the word **millionth**

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit7**
Pasword : **z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

**Después se hace lo siguiente en la consola**

```bash
ls
# data.txt
wc data.txt
#  98567  197133 4184396 data.txt

## Forma 1 de llegar a la llave 
grep millionth data.txt
# millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Forma 2 de llegar a la llave 
cat data.txt | grep millionth
# millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```

**Resultado final**

```
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```


---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| Grep | busca una palabra o patrón que definamos en un archivo de texto y se imprimirá la línea o líneas que la contengan |
| WC | muestra información estadística sobre un archivo, como el número de líneas, palabras y caracteres |

``` bash
wc data.txt
#  98567  197133 4184396 data.txt
```
- 98567 es el número de líneas
- 197133 es el número de palabras
- 4184396 es el número de bytes
---
## Referencias 

[Comando Grep en Linux - Tutorial + Ejemplos Útiles (hostinger.es)](https://www.hostinger.es/tutoriales/comando-grep-linux)
[Comando WC: Contando el número de líneas en Linux (itsfoss.com)](https://itsfoss.com/es/comando-wc-linux/)