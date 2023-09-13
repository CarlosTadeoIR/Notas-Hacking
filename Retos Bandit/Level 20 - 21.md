# Level 20 - 21
---

## Objetivo 
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit20**
Pasword : **VxCazJaVykI6W36BkBU0mJTCM8rR95XT**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

**Después se hace lo siguiente en la consola**

```bash
ls -la
# total 36
# drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
# drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
# -rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
# -rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
# -rw-r--r--  1 root     root       807 Jan  6  2022 .profile
# -rwsr-x---  1 bandit21 bandit20 15600 Apr 23 18:04 suconnect

nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
# [1] 2294117
# bandit20@bandit:~$ Listening on 0.0.0.0 2020
./suconnect 2020
# Connection received on 127.0.0.1 47546
# Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
# Password matches, sending next password
# NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
# [1]+  Done                    nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```

**Resultado final**

```
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| nc|comando principal de la utilidad Netcat, que se utiliza para crear conexiones de red y transferir datos a través de la red.
| -l | Indica que nc debe entrar en modo de escucha (listener), lo que significa que esperará conexiones entrantes en lugar de intentar conectarse a un host remoto.
| -n |Desactiva la resolución DNS, lo que significa que no intentará resolver nombres de host en direcciones IP
| -v |Habilita la salida detallada o verbosa, que mostrará información sobre las conexiones entrantes.
| -p 2020 | Especifica el puerto en el que nc debe escuchar, en este caso, el puerto 2020
| & |al final del comando se utiliza para ejecutar el comando en segundo plano, lo que significa que el comando se ejecutará en el fondo y el control del terminal se devolverá al usuario para que puedas seguir trabajando en el mismo terminal.


---
## Referencias 

[Comando nc (netcat): Qué es y cómo se usa | Neoguias](https://www.neoguias.com/comando-nc/)
