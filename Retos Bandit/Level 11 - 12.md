# Level 11 - 12
---

## Objetivo 

The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit11**
Pasword : **6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

**Después se hace lo siguiente en la consola**

**Forma 1 de llegar a la llave**

```bash
ls
# data.txt
cat data.txt
# Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
# The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

**Forma 2 de llegar a la llave**

```bash
ls
# data.txt
cat data.txt
# Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
python3
# Python 3.10.6 (main, Mar 10 2023, 10:55:28) [GCC 11.3.0] on linux
# Type "help", "copyright", "credits" or "license" for more information.
import codecs
codec.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi','rot13')
# 'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'
```

**Resultado final**

```
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| [a-zA-Z]| Es una expresión regular ( regex ) que se utiliza para representar un rango de letras del alfabeto, tanto en mayúscula como en minúscula |
| tr | Se utiliza para transformar cadenas o eliminar caracteres de la cadena. Se pueden realizar varios tipos de transformación utilizando este comando, como buscar y reemplazar texto, transformar una cadena de mayúsculas a minúsculas o viceversa, eliminar caracteres repetidos de la cadena, etc.  |
| [n-za-mN-ZA-M] |Es una expresión regular que se utiliza para hacer coincidir letras en minúscula y mayúscula dentro de los rangos específicos de "a" a "n" o "b" a "o" (en ambos casos) y "A" a "N" o "B" a "O" (en mayúscula) en un flujo de texto. Lo cual se puede interpretar como avanzar 13 lugares por cada letra|
| codecs | Librería de Python que define las clases base para los códecs estándar de Python (codificadores y decodificadores) y proporciona acceso al registro interno de códecs de Python, que administra el códec y el proceso de búsqueda del manejo de errores
|codecs.decode| Decodifica obj utilizando el códec registrado para encoding.|

Por lo tanto el comando 

```bash
cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
```

Muestra el contenido del archivo data.txt ( cat data.txt ) para después redirigir la salida ( | ) como entrada del próximo comando ( tr ) donde primero se consideran todas las letras del alfabeto ya sean minúsculas o mayúsculas  ( [a-zA-Z] ) para posteriormente cambiar cada letra avanzado 13 lugares en el alfabeto ([n-za-mN-ZA-M]) por lo que la letra " a " pasa a ser "n"

---
## Referencias 

[Expresiones Regulares - JavaScript | MDN (mozilla.org)](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Regular_Expressions)

[Preguntaste: ¿Qué es TR Linux? - CompuHoy.com](https://www.compuhoy.com/preguntaste-que-es-tr-linux/#:~:text=El%20comando%20tr%20en%20UNIX%20es%20una%20utilidad,con%20tuber%C3%ADas%20UNIX%20para%20admitir%20traducciones%20m%C3%A1s%20complejas.)

[codecs — Registro de códec y clases base — documentación de Python - 3.11.5](https://docs.python.org/es/3/library/codecs.html#module-codecs)
