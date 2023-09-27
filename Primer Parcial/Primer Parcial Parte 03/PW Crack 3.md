## Objetivo 

Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

---
## Datos de acceso al nivel 

se descargan los siguientes archivos 
https://artifacts.picoctf.net/c/16/level3.py

https://artifacts.picoctf.net/c/16/level3.flag.txt.enc

https://artifacts.picoctf.net/c/16/level3.hash.bin

---
## Solución 

``` bash
## primero se analiza el codigo 
cat level3.py 
# The strings below are 7 possibilities for the correct password. 
# (Only 1 is correct)
# pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]

## como se puede ver en el archivo apaarecen las 7 posibles llaves asi que solo queda probar de una en una 
python3 level3.py
#Please enter correct password for flag: 
865e              
#Welcome back... your flag, user:
# picoCTF{m45h_fl1ng1ng_2b072a90}
```

**Resultado Final**
```
picoCTF{m45h_fl1ng1ng_2b072a90}
```

---
## Notas Adicionales 
Se puede modificar el Archivo para que se validen en automático todas las posibles contraseñas, solo que es mas tardado hacerlo 

---
## Referencias 