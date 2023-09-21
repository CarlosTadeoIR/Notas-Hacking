# Level 28 - 29 
---
## Objetivo 
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit28**
Pasword : **AVanL161y9rsbcJIsFHuw35rjaOM19nR**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

**Después se hace lo siguiente en la consola**

```bash
mktemp -d
#/tmp/tmp.1FbjvJe3TL
cd /tmp/tmp.1FbjvJe3TL

git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
## pide confirmacion 
## pide la contraseña del nivel actual
AVanL161y9rsbcJIsFHuw35rjaOM19nR


ls
#repo
cd repo


ls -la .git
# total 52
# drwxrwxr-x 8 bandit28 bandit28 4096 Sep 21 01:30 .
# drwxrwxr-x 3 bandit28 bandit28 4096 Sep 21 01:30 ..
# drwxrwxr-x 2 bandit28 bandit28 4096 Sep 21 01:30 branches
# -rw-rw-r-- 1 bandit28 bandit28  281 Sep 21 01:30 config
# -rw-rw-r-- 1 bandit28 bandit28   73 Sep 21 01:30 description
# -rw-rw-r-- 1 bandit28 bandit28   23 Sep 21 01:30 HEAD
# drwxrwxr-x 2 bandit28 bandit28 4096 Sep 21 01:30 hooks
# -rw-rw-r-- 1 bandit28 bandit28  137 Sep 21 01:30 index
# drwxrwxr-x 2 bandit28 bandit28 4096 Sep 21 01:30 info
# drwxrwxr-x 3 bandit28 bandit28 4096 Sep 21 01:30 logs
# drwxrwxr-x 4 bandit28 bandit28 4096 Sep 21 01:30 objects
# -rw-rw-r-- 1 bandit28 bandit28  114 Sep 21 01:30 packed-refs
# drwxrwxr-x 5 bandit28 bandit28 4096 Sep 21 01:30 refs
git log


# commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
# Author: Morla Porla <morla@overthewire.org>
# Date:   Sun Apr 23 18:04:39 2023 +0000
# 
#   fix info leak
#
# commit abcff758fa6343a0d002a1c0add1ad8c71b88534
# Author: Morla Porla <morla@overthewire.org>
# Date:   Sun Apr 23 18:04:39 2023 +0000
# 
#   add missing data
# 
# commit c0a8c3cf093fba65f4ee0e1fe2a530b799508c78
# Author: Ben Dover <noone@overthewire.org>
# Date:   Sun Apr 23 18:04:39 2023 +0000
# 
#    initial commit of README.md
## los ultimos 2 commits
git diff 899ba88df296331cc01f30d022c006775d467f28 abcff758fa6343a0d00 2a1c0add1ad8c71b88534

# diff --git a/README.md b/README.md
# index 5c6457b..b302105 100644
# --- a/README.md
# +++ b/README.md
# @@ -4,5 +4,5 @@ Some notes for level29 of bandit.
#  ## credentials

#  - username: bandit29
# -- password: xxxxxxxxxx
# +- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

```

**Resultado final**

```
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| git log | Permite enumerar, filtrar y buscar commit según cambios específicos. Mientras que git status sirve para buscar en el directorio de trabajo, git log se centra solo en los commit que se han ejecutado.
| git def | Compara dos estados de commits y te muestra en qué se diferencian el uno del otro.

---
## Referencias 
[Git log: cómo ver las instantáneas de tus commit - IONOS](https://www.ionos.es/digitalguide/paginas-web/desarrollo-web/git-log/#:~:text=Git%20log%20y%20git%20diff%20En%20la%20pr%C3%A1ctica%2C,se%20consigue%20enumerar%20los%20cambios%20entre%20dos%20commit.)
