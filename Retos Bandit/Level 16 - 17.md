# Level 16 - 17
---

## Objetivo 
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.


---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit16**
Pasword : **JQttfApK4SeyHwDlI9SXGR50qclOAil1**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```

**Después se hace lo siguiente en la consola**

```bash
nmap -p 31000-32000 localhost
## muestra una lista de servidores 
# PORT      STATE SERVICE
# 31046/tcp open  unknown
# 31518/tcp open  unknown
# 31691/tcp open  unknown
# 31790/tcp open  unknown
# 31960/tcp open  unknown
openssl s_client -connect localhost:31790
## muestra mucha info hasta pedir la contraseña del nivel actual
# read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
## Muestra la llave privada
```

**La Llave Privada**

```
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
```

después de tener la llave privada se hace lo siguiente

```bash 
exit
# logout
# Connection to bandit.labs.overthewire.org closed.
## En la ruta donde ejecutamos el CMD se crea un archivo de texto
notepad llave.txt
## despues de guardar la llave privada en el archivo llave.txt 
## se accede a bandit17 con la llave que guardamos en el archivo llave.txt
ssh -i llave.txt bandit17@bandit.labs.overthewire.org -p 2220
## dentro de bandit17
cat /etc/bandit_pass/bandit17
# VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
```

**Resultado Final**
```
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
```


---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| nmap |  Se usa para determinar los hosts que se están ejecutando y los servicios que estos están ejecutando
| -p | Se utiliza para especificar el rango de puertos
| -p 31000-32000 | delimita que se buscaran todos los puertos que estén en el rango 31000-32000
| -i llave.txt | Se utiliza para especificar el archivo de clave privada que se utilizará para la autenticación
 


---
## Referencias 

[Comando NMAP: Como administrar redes en linux desde el terminal (ayudalinux.com)](https://ayudalinux.com/comando-nmap/#:~:text=Comando%20NMAP%3A%20Como%20administrar%20redes%20en%20linux%20desde,los%20puertos%20TCP%20y%20UDP%20...%20M%C3%A1s%20elementos)