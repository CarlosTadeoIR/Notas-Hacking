# Level 1 - 2
---
## Objetivo 
The password for the next level is stored in a file called **-** located in the home directory

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit1**
Pasword : **NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

**Después se hace lo siguiente en la consola**
``` bash
ls 
# - 
cat - 
# ^C 

## Forma 1 de llegar a la llave 
cat ./- 
# rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi 

## Forma 2 de llegar a la llave 
pwd 
# /home/bandit1 
cat /home/bandit1/- 
# rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi 
```

**Resultado final**

```
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

---
## Notas Adicionales 

El (-) es considerado como un carácter especial por eso la forma de poder acceder, crear o eliminar algún archivo que empiece con (-) es mediante ciertos parámetros que se deben definir antes de ejecutar la acción, una de las soluciones era pasar el parámetro de la dirección del directorio para poder acceder al archivo llamado (-)

---
## Referencias 

[Nombre de archivo discontinuo: aprenda a crear/eliminar/listar/leer/copiar (webservertalk.com)](https://www.webservertalk.com/dashed-filename)
[Special Characters (tldp.org)](https://tldp.org/LDP/abs/html/special-chars.html)
