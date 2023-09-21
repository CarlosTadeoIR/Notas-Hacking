# Level 32 - 33
---
## Objetivo 
After all this `git` stuff its time for another escape. Good luck!

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit32**
Pasword : **rmCBvG56y58BXzv98yZGdO7ATVL5dW8y**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```

**Después se hace lo siguiente en la consola**

```bash
# WELCOME TO THE UPPERCASE SHELL
>> $0
$ pwd
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy

## no supe como salir asi que solo cerre la ventana 
```

**Resultado final**

```
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
```

---
## Notas Adicionales 

Se accede a un tipo de Shell que cambia todos los comando escritos a mayúsculas, la única forma de poder escribir es si se usa la variable de parámetros posicionales  $0 

---
## Referencias 
