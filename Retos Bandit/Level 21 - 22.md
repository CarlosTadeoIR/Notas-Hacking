# Level 21 - 22
---

## Objetivo 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit21**
Pasword : **NvEJF7oVjkddltPSrdKEFOllh9V1IBcq**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit21@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
```

**Después se hace lo siguiente en la consola**

```bash
cat /etc/crontab
#muestra que tan frecuente se van a hacer tareas programadas 

## muestra los procesos counes del usario 
ls -la /etc/cron.d
# total 56
# drwxr-xr-x   2 root root  4096 Apr 23 18:05 .
# drwxr-xr-x 108 root root 12288 Aug 12 08:42 ..
# -rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit15_root
# -rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit17_root
# -rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit22
# -rw-r--r--   1 root root   122 Apr 23 18:04 cronjob_bandit23
# -rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit24
# -rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit25_root
# -rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
# -rwx------   1 root root    52 Apr 23 18:05 otw-tmp-dir
# -rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
# -rw-r--r--   1 root root   396 Feb  2  2021 sysstat

ls /etc/cron.d
# cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
# cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir

cat /etc/cron.d/cronjob_bandit22
# @reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
# * * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null

## cronjob_bandit22.sh es el proceso que se ejecuta irregularmente 
cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
## lectura y escritura para todos los usarios 
# chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
## el resultado del comando para ver la contraseña lo envia al siguiente direcotiro  
# cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

#WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

```

**Resultado final**

```
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| Cron | se encargará de comprobar si existe alguna tarea (job) para ser ejecutada, de acuerdo a la hora configurada en el propio sistema operativo
| Crontab | se trata de un archivo con un contenido especial y específicamente diseñado para que sea leído correctamente por Cron y proceder con la ejecución que nosotros hayamos programado. Crontab posee una lista con todos los scripts a ejecutar, generalmente cada usuario del sistema posee su propio fichero Crontab

---
## Referencias 

[Cómo usar Cron y Crontab en Linux para programar tareas en servidores (redeszone.net)](https://www.redeszone.net/tutoriales/servidores/cron-crontab-linux-programar-tareas/)

