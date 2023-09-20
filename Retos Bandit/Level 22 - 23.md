# Level 22 - 23
---

## Objetivo 

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit22**
Pasword : **WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit22@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

**Después se hace lo siguiente en la consola**

```bash
ls /etc/cron.d
# cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
# cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir

cat /etc/cron.d/cronjob_bandit23
# @reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
# * * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null

cat /usr/bin/cronjob_bandit23.sh
## #!/bin/bash

## myname=$(whoami)
## mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
## echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"
## cat /etc/bandit_pass/$myname > /tmp/$mytarget


myname=bandit23
echo $(echo I am user $myname | md5sum | cut -d ' ' -f 1)
# 8ca319486bfbbc3663ea0fbe81326349
cat /tmp/8ca319486bfbbc3663ea0fbe81326349
# QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

**Resultado final**

```
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| Cron | se encargará de comprobar si existe alguna tarea (job) para ser ejecutada, de acuerdo a la hora configurada en el propio sistema operativo

---
## Referencias 
[Cómo usar Cron y Crontab en Linux para programar tareas en servidores (redeszone.net)](https://www.redeszone.net/tutoriales/servidores/cron-crontab-linux-programar-tareas/)
