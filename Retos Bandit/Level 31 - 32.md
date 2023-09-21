# Level 31 - 32 
---
## Objetivo 
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit31**
Pasword : **OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```

**Después se hace lo siguiente en la consola**

```bash
mktemp -d
# /tmp/tmp.osSkxLMyKJ
cd /tmp/tmp.osSkxLMyKJ

git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
## pide autenticacion y la contraseña del nivel
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
cd repo
cat README.md
#This time your task is to push a file to the remote repository.

# Details:
#    File name: key.txt
#    Content: 'May I come in?'
#    Branch: master

touch key.txt
echo "May I come in?" >> key.txt
cat key.txt
# May I come in?

git add -f key.txt
git commit -m 'add key'
# [master 4de0938] add key
#  1 file changed, 1 insertion(+)
# create mode 100644 key.txt
git push origin master

## pide autenticacion y la contraseña del nivel

# bandit31-git@localhost's password:
# Enumerating objects: 4, done.
# Counting objects: 100% (4/4), done.
# Delta compression using up to 2 threads
# Compressing objects: 100% (2/2), done.
# Writing objects: 100% (3/3), 321 bytes | 321.00 KiB/s, done.
# Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
# remote: ### Attempting to validate files... ####
# remote:
# remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
# remote:



# remote: Well done! Here is the password for the next level:
# remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y


# remote:
# remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
# remote:
# To ssh://localhost:2220/home/bandit31-git/repo
#  ! [remote rejected] master -> master (pre-receive hook declined)
# error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'

```

**Resultado final**

```
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| git add -f | se utiliza para forzar (force) la adición de archivos al área de preparación (staging area) de Git, incluso si los archivos están enlistados en el archivo `.gitignore`.
| git commit -m | se utiliza para confirmar (commit) los cambios realizados en el área de preparación (staging area) en Git, junto con un mensaje de confirmación (commit message) que proporcionas utilizando la opción `-m`.
|git push origin master|se utiliza para enviar los cambios confirmados en la rama local llamada "master" a la rama remota llamada "master" en el repositorio remoto llamado "origin".



---
## Referencias 
[Git - git-add Documentación (git-scm.com)](https://git-scm.com/docs/git-add)
[¿Qué significa "-m" en "git commit -m"? - Stack Overflow en español](https://es.stackoverflow.com/questions/155122/qu%c3%a9-significa-m-en-git-commit-m)
[Cual es la diferencia entre $git push -u origin master y $git push origin master? - Stack Overflow en español](https://es.stackoverflow.com/questions/111253/cual-es-la-diferencia-entre-git-push-u-origin-master-y-git-push-origin-master)
