# Level 6 - 7 
---

## Objetivo 

The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit6**
Pasword : **P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU**
Puerto  : 2220 
```


---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```

**Después se hace lo siguiente en la consola**

``` bash
ls

ls -la
# total 20
# drwxr-xr-x  2 root root 4096 Apr 23 18:04 .
# drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
# -rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
# -rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
# -rw-r--r--  1 root root  807 Jan  6  2022 .profile

find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
# /var/lib/dpkg/info/bandit7.password

cat /var/lib/dpkg/info/bandit7.password
# z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

**Resultado final**

```
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

---
## Notas Adicionales 

|**Parámetro de búsqueda para "find"** | **Descripción** |
|:---------:|:-------------|
|-user | Filtrar por propietario
|-group | Filtrar por grupo
|-perm | Filtrar por derechos de acceso

---
## Referencias 

[Linux find | Cómo usar el comando find de Linux - IONOS](https://www.ionos.es/digitalguide/servidores/configuracion/comando-linux-find/)