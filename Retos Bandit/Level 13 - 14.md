# Level 13 - 14
---

## Objetivo 

The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit13**
Pasword : **wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw**
Puerto  : 2220 
la llave esta en : /etc/bandit_pass/bandit14
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
```

**Después se hace lo siguiente en la consola**

```bash
ls
# sshkey.private
ssh -i sshkey.private bandit14@localhost -p 2220

## Aqui se pide que verifiquemo si nos queremos conectar
# pasamos a bandit14

cat /etc/bandit_pass/bandit14
# fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

# bandit14@bandit:~$ exit
# logout
# Connection to localhost closed.
# bandit13@bandit:~$ exit
# logout
# Connection to bandit.labs.overthewire.org closed.
```

**Resultado final**

```
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```

---
## Notas Adicionales 



---
## Referencias 

[SSH/OpenSSH/Keys - Community Help Wiki (ubuntu.com)](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)