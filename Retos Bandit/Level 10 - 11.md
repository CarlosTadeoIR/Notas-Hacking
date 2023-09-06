# Level 10 - 11
---

## Objetivo 

The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit10**
Pasword : **G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```

**Después se hace lo siguiente en la consola**

```bash
ls
# data.txt
cat data.txt
# VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
echo "hola mundo"
# hola mundo
echo "hola mundo" | base64
# aG9sYSBtdW5kbwo=
echo -n aG9sYSBtdW5kbwo= | base64 -d
# hola mundo

## Forma 1 de llegar a la llave
base64 -d data.txt
# The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Forma 2 de llegar a la llave
cat data.txt | base64 -d
# The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Forma 3 de llegar a la llave
python3
# Python 3.10.6 (main, Mar 10 2023, 10:55:28) [GCC 11.3.0] on linux
# Type "help", "copyright", "credits" or "license" for more information.
import base64
base64.b64decode('VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==')
# 'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'


```

**Resultado final**

```
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| echo | Es una herramienta útil para imprimir texto en la pantalla, almacenarlo en variables o redirigirlo a archivos en un entorno de línea de comandos |
| base64 | Se utiliza para realizar codificación y decodificación en Base64. Utilizado para representar datos binarios como texto ASCII legible  |
| -d <br> **o** <br> --decode |Usado en base64 decodifica en lugar de codificar|
| \| | Se usa para conectar comandos y crear tuberías que redirigen la salida de uno hacia la entrada de otro, lo que facilita la combinación de comandos para realizar tareas más complejas| 


---
## Referencias 

[▷ Cómo usar el comando Echo en Linux - ResponTodo](https://respontodo.com/como-usar-el-comando-echo-en-linux/#:~:text=C%C3%B3mo%20usar%20el%20comando%20Echo%20en%20Linux%201,la%20cadena%20que%20desea%20que%20se%20muestre%3A%20)

[Codificación y decodificación de Base64 desde la línea de comandos - Sugerencia de Linux (ciksiti.com)](https://ciksiti.com/es/chapters/658-base64-encode-and-decode-from-command-line--linux-hint#:~:text=Codificaci%C3%B3n%20y%20decodificaci%C3%B3n%20de%20Base64%20desde%20la%20l%C3%ADnea,8%20Validaci%C3%B3n%20de%20la%20clave%20de%20usuario%20)

[Tuberías en Linux: hazte todo un "fontanero" profesional (architecnologia.es)](https://architecnologia.es/pipes-especial-tuberias-linux#:~:text=Para%20poder%20insertar%20tuber%C3%ADas%20y%20enlazar%20procesos%2C%20tan,de%20un%20proceso%20hacia%20la%20entrada%20de%20otro.)


