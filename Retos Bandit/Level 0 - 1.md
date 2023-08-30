# Level 0 - 1
---
## Objetivo 
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit0**
Pasword : **bandit0**
Puerto  : 2220
```
---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```


**Dentro del servidor se hace lo siguiente**
```bash
ls
#readme 
cat readme
#NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

**resultado final**
```
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| Cat | concatenar archivos e imprimir en la salida estándar |
| file | buscar archivos en una jerarquía de directorios |
| du | estimar el uso del espacio de archivos |
| find | determinar el tipo de archivo|

---
## Referencias 
[cat(1) - Linux manual page (man7.org)](https://man7.org/linux/man-pages/man1/cat.1.html)
[file(1) - Linux manual page (man7.org)](https://man7.org/linux/man-pages/man1/file.1.html)
[du(1) - Linux manual page (man7.org)](https://man7.org/linux/man-pages/man1/du.1.html)
[find(1) - Linux manual page (man7.org)](https://man7.org/linux/man-pages/man1/find.1.html)
