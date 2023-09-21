# Level 29 - 30
---
## Objetivo 
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit29**
Pasword : **tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit29@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```

**Después se hace lo siguiente en la consola**

```bash
mktemp -d
# /tmp/tmp.5PAdU8fUJP
cd /tmp/tmp.5PAdU8fUJP

git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
## pide confirmacion y luego la contraseña 
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S


ls
# repo
cd repo
ls
# README.md
cat README.md
# # Bandit Notes
# Some notes for bandit30 of bandit.
#
## credentials
#
# - username: bandit30
# - password: <no passwords in production!>


git branch -a
# * master
#  remotes/origin/HEAD -> origin/master
#  remotes/origin/dev
#  remotes/origin/master
#  remotes/origin/sploits-dev

git checkout dev
# Branch 'dev' set up to track remote branch 'dev' from 'origin'.
# Switched to a new branch 'dev'

git log
# commit 13e735685c73e5e396252074f2dca2e415fbcc98 (HEAD -> dev, origin/dev)
# Author: Morla Porla <morla@overthewire.org>
# Date:   Sun Apr 23 18:04:40 2023 +0000
#
#    add data needed for development
#
# commit 8caf551dba9f9e39bc8ea4163de7902e6fa85f3a
# Author: Ben Dover <noone@overthewire.org>
# Date:   Sun Apr 23 18:04:40 2023 +0000
#
#    add gif2ascii
#
# commit 4bd5389f9f2b9e96ba517aa751ee58d051905761 (origin/master, origin/HEAD, master)
# Author: Ben Dover <noone@overthewire.org>
# Date:   Sun Apr 23 18:04:40 2023 +0000
#
#    fix username
#
# commit 1a57cf10158f133c4f40ff82251f605a7618631d
# Author: Ben Dover <noone@overthewire.org>
# Date:   Sun Apr 23 18:04:40 2023 +0000
#
#    initial commit of README.md

git diff 13e735685c73e5e396252074f2dca2e415fbcc98 4bd5389f9f2b9e96ba517aa751ee58d051905761
# diff --git a/README.md b/README.md
# index a4b1cf1..1af21d3 100644
# --- a/README.md
# +++ b/README.md
# @@ -4,5 +4,5 @@ Some notes for bandit30 of bandit.
#  ## credentials

#  - username: bandit30
# -- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
# +- password: <no passwords in production!>

# diff --git a/code/gif2ascii.py b/code/gif2ascii.py
# deleted file mode 100644
# index 8b13789..0000000
# --- a/code/gif2ascii.py
# +++ /dev/null
# @@ -1 +0,0 @@

```

**Resultado final**

```
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| git checkout | se utiliza para cambiar entre ramas (branches), crear nuevas ramas, o deshacer cambios en tu directorio de trabajo.
| git branch -a | se utiliza para listar todas las ramas (branches) disponibles en un repositorio, tanto las locales como las remotas. La opción "-a" en este comando significa "all" (todo),

---
## Referencias 
[Comandos de GIT Básicos - Guía Completa (hostinger.es)](https://www.hostinger.es/tutoriales/comandos-de-git)