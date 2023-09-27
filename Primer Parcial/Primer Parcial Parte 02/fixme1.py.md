## Objetivo 

Fix the syntax error in this Python script to print the flag.

---
## Datos de acceso al nivel 

Se tiene que descargar el siguiente código python y editarlo para que funcione 
https://artifacts.picoctf.net/c/27/fixme1.py

---
## Solución 

El código presenta una falla de indentación por lo que se hace lo siguiente 

``` python
nano fixme1.py
# se edita el archivo con nano borrando las lineas anteriores a la ultima linea 
# deonde esta "print" para correguir el problema de identacion 
python3 fixme1.py
# That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

```

**resultado Final**
```
picoCTF{1nd3nt1ty_cr1515_182342f7}
```

---
## Notas Adicionales 
Python es GOD pero la indentación es un verdadero dolor de cabeza  

---
## Referencias 