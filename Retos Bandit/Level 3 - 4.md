# Level 3 - 4
---

## Objetivo 
The password for the next level is stored in a hidden file in the **inhere** directory.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit3**
Pasword : **aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

**Después se hace lo siguiente en la consola**

``` bash
ls
# inhere
cd inhere/
ls

ls -la
# total 12
# drwxr-xr-x 2 root    root    4096 Apr 23 18:04 .
# drwxr-xr-x 3 root    root    4096 Apr 23 18:04 ..
# -rw-r----- 1 bandit4 bandit3   33 Apr 23 18:04 .hidden

cat .hidden
# 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

**Resultado final**

```
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```


---
## Notas Adicionales 

|**Opciones ls** | **Descripción** |
|:---------:|:-------------|
|**<span style="color:red">-a</span>**| Lista todas las entradas incluyendo archivos ocultos.
|**-d** |Lista archivos del directorio en vez de contenidos.
|**-h** |Muestra los tamaños de archivo en términos de kilobytes, Megabyte, etc.
|**-i** |Muestra información de inodo.
|**<span style="color:red">-l</span>** |Lista todos los archivos, directorios y su modo, número de enlaces, propietario del archivo, tamaño del archivo, fecha y hora de modificación y nombre de archivo.
|**-ltr**|Ordena archivos por fecha.
|**-lsr**|Ordena archivos por tamaño.
|**-p** |Pone una barra al final de cada directorio.
|**-t** |Ordena por fecha de última modificación.
|**-u** |Ordena por fecha de último acceso.


---
## Referencias 

[Comando ls - EcuRed](https://www.ecured.cu/Comando_ls#Opciones)
