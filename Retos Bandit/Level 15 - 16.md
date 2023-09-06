# Level 15 - 16
---

## Objetivo 

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit15**
Pasword : **jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```

**Después se hace lo siguiente en la consola**

```bash
openssl s_client -connect localhost:30001
## se conecta y pide que ingreses la contarseña del mismo nivel

# read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
# Correct!
# JQttfApK4SeyHwDlI9SXGR50qclOAil1

```

**Resultado final**

```
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| openssl |  Es el comando principal de la utilidad OpenSSL, que es una herramienta de código abierto que proporciona implementaciones de protocolos SSL/TLS y otras herramientas de seguridad relacionadas.
| s_client | Es una subcomando de OpenSSL que se utiliza para actuar como un cliente SSL/TLS. Permite conectarse a servidores SSL/TLS y realizar pruebas de conectividad y seguridad.
| -connect localhost:30001  | especifica el host y el puerto al que se desea conectar utilizando SSL/TLS.

---
## Referencias 

[Transport Layer Security - Wikiwand](https://www.wikiwand.com/en/Secure_Socket_Layer)