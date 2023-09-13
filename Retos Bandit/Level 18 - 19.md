# Level 18 - 19
---

## Objetivo 
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit18**
Pasword : **hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220
```

**Contraseña de usuario**
```
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

**Acceder de esta forma hará que al momento de entrar salgamos automáticamente del usuario**

**Forma 1 de  acceder al servidor**
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

**Contraseña de usuario**
```
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

**Después se hace lo siguiente en la consola**

```bash
## se pega la contraseña del nivel cuando la pide para acceder al server 
# bandit18@bandit.labs.overthewire.org's password:
## despues se vuelve a colocar la contraseña 
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
# awhqfNnAbc1naukrpqDYcF95h7HoMTrC
## automaticamente sale del servidor 
```


**Forma 2 de  acceder al servidor**
```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 /bin/bash
```

**Contraseña de usuario**
```
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
```

**Después se hace lo siguiente en la consola**

```bash
## se pega la contraseña del nivel cuando la pide para acceder al server 
# bandit18@bandit.labs.overthewire.org's password:
cat readme 
# awhqfNnAbc1naukrpqDYcF95h7HoMTrC
## automaticamente sale del servidor 
```

**Resultado final para ambas formas de acceder al nivel**

```
awhqfNnAbc1naukrpqDYcF95h7HoMTrC
```

---
## Notas Adicionales 

antes de siquiera entrar a un servidor podemos definir comandos que se ejecuten automáticamente al momento de ingresar, eso desde la misma linea donde realizamos la conexión  

---
## Referencias 

[Cómo ejecutar comandos automáticamente al conectarnos por SSH (redeszone.net)](https://www.redeszone.net/2015/06/06/como-ejecutar-comandos-automaticamente-al-conectarnos-por-ssh/)

