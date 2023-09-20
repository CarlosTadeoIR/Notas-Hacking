# Level 27 - 28
---
## Objetivo 
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.



---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit27**
Pasword : **YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```

**Después se hace lo siguiente en la consola**

```bash
mktemp -d
# /tmp/tmp.FiFi10HDcE
cd /tmp/tmp.FiFi10HDcE
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
# Cloning into 'repo'...
## pide la contraseña 
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
# remote: Enumerating objects: 3, done.
# remote: Counting objects: 100% (3/3), done.
# remote: Compressing objects: 100% (2/2), done.
# remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
# Receiving objects: 100% (3/3), done.
ls
# repo
cd repo
ls
# README
cat README
# The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19n
```

**Resultado final**

```
AVanL161y9rsbcJIsFHuw35rjaOM19nR
```

---
## Notas Adicionales 

Git es un sistema de control de versiones gratuito y de código abierto, creado originalmente por Linus Torvalds en 2005. A diferencia de los antiguos sistemas centralizados de control de versiones, como SVN y CVS, Git está distribuido: cada desarrollador tiene el historial completo de su repositorio de código de manera local. De este modo, la clonación inicial del repositorio es más lenta, pero las operaciones posteriores, como commit, blame, diff, merge y log son mucho más rápidas.

---
## Referencias 
[Aprende a usar Git: tutoriales, flujos de trabajo y comandos (atlassian.com)](https://www.atlassian.com/es/git#:~:text=Principios%20b%C3%A1sicos%20de%20Git.%20Git%20es%20un%20sistema,de%20su%20repositorio%20de%20c%C3%B3digo%20de%20manera%20)
