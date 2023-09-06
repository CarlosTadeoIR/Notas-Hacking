# Level 12 - 13
---

## Objetivo 

The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit12**
Pasword : **JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

**Después se hace lo siguiente en la consola**

```bash
xxd -r data.txt | file -
# /dev/stdin: gzip compressed data, was "data2.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix

xxd -r data.txt | zcat |file -
# /dev/stdin: bzip2 compressed data, block size = 900k

xxd -r data.txt | zcat | bzcat |file -
# /dev/stdin: gzip compressed data, was "data4.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix

xxd -r data.txt | zcat | bzcat | zcat |file -
# /dev/stdin: POSIX tar archive (GNU)

xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
# /dev/stdin: POSIX tar archive (GNU)

xxd -r data.txt | zcat | bzcat | zcat | tar xO | file -
# /dev/stdin: POSIX tar archive (GNU)

xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat |file -
# /dev/stdin: POSIX tar archive (GNU)

xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
# /dev/stdin: gzip compressed data, was "data9.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix

xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
# /dev/stdin: ASCII text

xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
# The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

**Resultado final**

```
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| xxd| Permite crear un volcado hexadecimal o incluso hacer lo contrario
| zcat |Mostrar el contenido de archivos comprimidos en formato gzip (.gz) sin necesidad de descomprimirlos explícitamente  |
| bzcat |Se utiliza para mostrar el contenido de archivos comprimidos en formato bzip2 (.bz2) sin necesidad de descomprimirlos explícitamente.|
| tar | Se utiliza para crear, manipular y extraer archivos comprimidos en un formato conocido como "tarball". La palabra "tar" se deriva de "tape archive" porque originalmente se utilizaba para crear copias de seguridad de archivos en cintas magnéticas
|tar xO| Se utiliza para extraer archivos de un archivo tar y mostrar su contenido en la pantalla estándar en lugar de extraerlos en el sistema de archivos|
| -r | De hexadecimal a binario |

---
## Referencias 

[-🔥 Tutorial de comandos Linux xxd para principiantes (con ejemplos) 🔥- (linuxpasion.com)](https://linuxpasion.com/tutorial-de-comandos-linux-xxd-para-principiantes-con-ejemplos)

[Comando Linux / Unix: zcat | TecnoNautas](https://tecnonautas.net/comando-linux-unix-zcat/#:~:text=Comando%20Linux%20%2F%20Unix%3A%20zcat%201%20Nombre%20gzip%2C,extraer%C3%A1%20todos%20los%20miembros%20a%20la%20vez.%20)

[Cómo usar el comando Tar en Linux (hostinger.es)](https://www.hostinger.es/tutoriales/como-usar-comando-tar-linux)
