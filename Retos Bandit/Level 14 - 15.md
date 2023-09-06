# Level 14 - 15
---

## Objetivo 

The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit14**
Pasword : **fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit14@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
```

**Después se hace lo siguiente en la consola**

```bash
nc localhost 30000
## se ingresa la contraseña 
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

# Correct!
# jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

**Resultado final**

```
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| nc | (netcat) se utiliza para establecer una conexión de red a un servidor que se encuentra en el host local (localhost) en el puerto 30000.

---
## Referencias 

[Comando nc (netcat): Qué es y cómo se usa | Neoguias](https://www.neoguias.com/comando-nc/#Que_es_el_comando_nc)

