# Level 2 - 3
---
## Objetivo 
The password for the next level is stored in a file called **spaces in this filename** located in the home directory

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit2**
Pasword : **rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

**Después se hace lo siguiente en la consola**

```bash
ls 
# spaces in this filename
cat spaces in this filename 
# cat: spaces: No such file or directory
# cat: in: No such file or directory
# cat: this: No such file or directory
# cat: filename: No such file or directory 

## Forma 1 de llegar a la llave
cat spaces\ in\ this\ filename 
# aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG 

## Forma 1 de llegar a la llave
cat "spaces in this filename" 
# aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

**Resultado final**

```
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

---
## Notas Adicionales 

los espacios en blanco en el nombre de un archivo no suelen usarse mucho ya que se crea incompatibilidad con algunos comandos, sin embargo ahí forma de solucionar ese detalles, la primera forma consiste en colocar (\ ) después de cada palabra de nuestro archivo y la segunda opción es encerrar en comillas (" ") el nombre de nuestro documento 

---
## Referencias 
[Tratar con espacios en nombres de archivo en Linux (linuxhandbook.com)](https://linuxhandbook.com/filename-spaces-linux/)
