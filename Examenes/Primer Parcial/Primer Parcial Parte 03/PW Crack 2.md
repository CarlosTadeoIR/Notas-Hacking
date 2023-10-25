## Objetivo 

Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/15/level2.py

https://artifacts.picoctf.net/c/15/level2.flag.txt.enc


---
## Solución 

``` bash
# analizamos el prgrama con cat 
cat level2.py
# if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):
#        print("Welcome back... your flag, user:")

## Como se puede ver la cotraseña esta encriptada para ello se hace lo siguinte 
python3
# Python 3.11.2 (main, Mar 13 2023, 12:18:29) [GCC 12.2.0] on linux
# Type "help", "copyright", "credits" or "license" for more information.
# >>> print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))
# 39ce


python3 level2.py
# Please enter correct password for flag: 
39ce
# Welcome back... your flag, user:
# picoCTF{tr45h_51ng1ng_502ec42e}

```

**Resultado Final**
```
picoCTF{tr45h_51ng1ng_502ec42e}
```


---
## Notas Adicionales 

una forma para ahorrar tiempo es hacer lo siguiente 
```
python3 -c "print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))"
39ce
```

---
## Referencias 