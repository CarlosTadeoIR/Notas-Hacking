# Level 25 - 26
---
## Objetivo 
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not **/bin/bash**, but something else. Find out what it is, how it works and how to break out of it.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit25**
Pasword : **p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```

**Después se hace lo siguiente en la consola**

```bash
ls
# bandit26.sshkey
ssh -i bandit26.sshkey bandit26@localhost -p 2220
# Connection to localhost closed.
## de alguna manera al entrar al usario 26 se cierra la conexion en automatico

cat /etc/passwd | grep bandit26
# bandit26:x:11026:11026:bandit level
# 26:/home/bandit26:/usr/bin/showtext

cat /usr/bin/showtext
# #!/bin/sh
# export TERM=linux
# exec more ~/text.txt
# exit 0
```

**Forma correcta de llegar a la llave**

```bash
## visto lo anterior se tiene que ejecuntar el mimos comando para igresar a bandit26 
## pero minimizando la ventana de la consola lo mas que se pueda esto para que entre en 
## funcion el comando more y podamos acceder al vim 
ssh -i bandit26.sshkey bandit26@localhost -p 2220

#--More--(50%)
v 
## se oprime primero : y despues se escirbe lo demas
:e /etc/bandit_pass/bandit26
# c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

## para salir del vim
:qa
# ------------------------
# Connection to localhost closed.

```

**Resultado final**

```
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| vi |Vi es un editor de texto utilizado por muchos desarrolladores para **escribir código,** debido a que carece de interfaz, por lo que se evita cualquier tipo de distracción permitiendo al usuario centrar toda la atención en el código..
| more |El comando more permite mostrar la salida en el terminal una página a la vez. Esto es especialmente útil cuando se ejecuta un comando que causa mucho desplazamiento, como el comando ls o el comando du.

---
## Referencias 
[Vi, editor de textos de terminal para Linux: tutorial completo (softzone.es)](https://www.softzone.es/linux/programas/manual-vi/)
[Todo lo que necesitas saber sobre el comando More | TecnoNautas](https://tecnonautas.net/todo-lo-que-necesitas-saber-sobre-el-comando-more/#:~:text=Todo%20lo%20que%20necesitas%20saber%20sobre%20el%20comando,una%20l%C3%ADnea%20de%20texto%20determinada%20...%20M%C3%A1s%20elementos)
