# Level 19 - 20
---

## Objetivo 
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit19**
Pasword : **awhqfNnAbc1naukrpqDYcF95h7HoMTrC**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

**Después se hace lo siguiente en la consola**

```bash
ls -la
# total 36
# drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
# drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
# -rwsr-x---  1 bandit20 bandit19 14876 Apr 23 18:04 bandit20-do
# -rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
# -rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
# -rw-r--r--  1 root     root       807 Jan  6  2022 .profile

./bandit20-do cat /etc/bandit_pass/bandit20

# VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

**Resultado final**

```
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| setuid | como tal no es un comando es un atributo especial que se puede aplicar a archivos ejecutables en sistemas Unix y sistemas operativos basados en Unix, como Linux 

en la linea 
-rwsr-x---  1 bandit20 bandit19 14876 Apr 23 18:04 bandit20-do

se sabe que cumple con el atributo setuid por que en -rwsr-x---  aparece una "S"

Por lo cual al final se esta ejecutando el programa bandit20-do con el atributo setuid activado. Esto significa que, aunque lo estemos ejecutando con bandit19, el programa se ejecutará con los privilegios del propietario del archivo bandit20-do, que es el usuario bandit20.

---
## Referencias 

[Setuid - Wikiwand](https://www.wikiwand.com/en/Setuid)

