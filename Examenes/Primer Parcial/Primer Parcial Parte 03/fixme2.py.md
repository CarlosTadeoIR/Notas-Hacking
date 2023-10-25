## Objetivo 

Fix the syntax error in the Python script to print the flag.

---
## Datos de acceso al nivel 

se necesita descargar el siguiente script de Python 

https://artifacts.picoctf.net/c/4/fixme2.py

---
## Solución 

``` python
python3 fixme2.py
#  File "/home/kali/Downloads/fixme2.py", line 22
#    if flag = "":
#       ^^^^^^^^^

nano fixme2.py
# se abre nano y se modifica el ultimo if 
# if flag = "" ---->  if flag == "":
# despues se guarda y se ejecuta 

python3 fixme2.py
# That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}

```

**Resultado Final**
```
picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```

---
## Notas Adicionales 

Cuando abrí nano me aparecieron unos rectángulos azules, no supe que eran pero los borre por si acaso  

---
## Referencias 