## Objetivo 

Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

---
## Datos de acceso al nivel 

Se descargan los siguientes archivos 
https://artifacts.picoctf.net/c/10/level1.py

https://artifacts.picoctf.net/c/10/level1.flag.txt.enc

---
## Solución 

``` bash
## antes de ejecutar el script analizamos el script 
cat level.py
# def level_1_pw_check():
#     user_pw = input("Please enter correct password for flag: ")
#     if( user_pw == "691d"):
#         print("Welcome back... your flag, user:")
#         decryption = str_xor(flag_enc.decode(), user_pw)
#         print(decryption)
#         return
#     print("That password is incorrect")

## Como se puede ver existe una condicion el la que si se pone la contraseña 691d dara la llave

python3 level1.py
#Please enter correct password for flag: 
691d
# Welcome back... your flag, user:
# picoCTF{545h_r1ng1ng_56891419}

```

**Resultado Final**
```
picoCTF{545h_r1ng1ng_56891419}
```

---
## Notas Adicionales 

Es mas común de lo que parce xd

---
## Referencias 