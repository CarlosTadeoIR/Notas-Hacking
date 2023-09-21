# Level 30 - 31
---
## Objetivo 
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit30**
Pasword : **xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

**Después se hace lo siguiente en la consola**

```bash
mktemp -d
# /tmp/tmp.uWigXOt34N
cd /tmp/tmp.uWigXOt34N
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
## pide validacion y contraseña 
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS


ls
# repo
cd repo
ls
# README.md
cat README.md
# just an epmty file... muahaha ##NOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOOO

git branch -a
# * master
#   remotes/origin/HEAD -> origin/master
#   remotes/origin/master
  
git show-branch --all
# * [master] initial commit of README.md
#  ! [origin/HEAD] initial commit of README.md
#   ! [origin/master] initial commit of README.md
# ---
# *++ [master] initial commit of README.md


git log
# commit 59530d30d299ff2e3e9719c096ebf46a65cc1424 (HEAD -> master, origin/master, origin/HEAD)
# Author: Ben Dover <noone@overthewire.org>
# Date:   Sun Apr 23 18:04:42 2023 +0000
# 
#     initial commit of README.md

cat .git/packed-ref
# cat: .git/packed-ref: No such file or directory
git show-ref --tags -d
# 831aac2e2341f009e40e46392a4f5dd318483019 refs/tags/secret
git show --name-only secret
# OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

```

**Resultado final**

```
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| git show-branch --all | muestra información sobre las ramas y sus historiales. Las líneas con asteriscos representan la rama actual, las líneas con signos de exclamación (!) indican otras ramas y las líneas con signos más (+) indican puntos de unión entre ramas.
|  git show-ref --tags -d |  muestra información sobre las etiquetas (tags) y sus objetos referenciados en el repositorio. En este caso, muestra una etiqueta llamada "secret" y el SHA-1 del objeto al que apunta.
|git show --name-only secret | muestra el contenido del objeto referenciado por la etiqueta "secret"|

---
## Referencias 
[git branch - How to see and go to local branches in git? - Stack Overflow](https://stackoverflow.com/questions/47469039/how-to-see-and-go-to-local-branches-in-git#:~:text=git%20branch%20will%20show%20you%20your%20local%20branches,the%20leaf%20commit%20of%20a%20chain%20of%20commits.)
[Git - git-show-ref Documentation (git-scm.com)](https://git-scm.com/docs/git-show-ref)
[why "git show --name-only --pretty=format:" could show only names of affected files - Stack Overflow](https://stackoverflow.com/questions/49241633/why-git-show-name-only-pretty-format-could-show-only-names-of-affected-fi)
