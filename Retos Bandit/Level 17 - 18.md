# Level 17 - 18
---

## Objetivo 
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit17**
Pasword 1 : **VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e**
Pasword 2 : **la llave privada que se guardo en llave.txt**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**

**Forma 1 de acceder**
```bash
ssh -i llave.txt bandit17@bandit.labs.overthewire.org -p 2220
```


**Forma 2 de acceder**

```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
```

**Después se hace lo siguiente en la consola**

```bash
ls -la
# drwxr-xr-x  3 root     root     4096 Apr 23 18:04 .
# drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
# -rw-r-----  1 bandit17 bandit17   33 Apr 23 18:04 .bandit16.password
# -rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
# -rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
# -rw-r-----  1 bandit18 bandit17 3300 Apr 23 18:04 passwords.new
# -rw-r-----  1 bandit18 bandit17 3300 Apr 23 18:04 passwords.old
# -rw-r--r--  1 root     root      807 Jan  6  2022 .profile
# drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .ssh

##Forma 1 de llegar a la llave 
diff passwords.old passwords.new --color
# 42c42
# < glZreTEH1V3cGKL6g4conYqZqaEj0mte
# ---
# > hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Forma 2 de llegar a la llave 
## es lo mismo pero sin cambiar los colores en el bash 
diff passwords.old passwords.new
# 42c42
# < glZreTEH1V3cGKL6g4conYqZqaEj0mte
# ---
# > hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

**Resultado final**

```
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```


---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| diff |  Compara las diferencias entre ficheros línea a línea mostrando las diferencias entre ellos en la salida estándar
| --color | se utiliza para habilitar la resaltación de las diferencias con colores en la salida 

---
## Referencias 

[diff Linux | Comparar las diferencias entre ficheros - El Taller del Bit](https://eltallerdelbit.com/comando-diff-ejemplos/)

