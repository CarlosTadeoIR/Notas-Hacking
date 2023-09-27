## Objetivo 

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `6dee9772`

Additional details will be available after launching your challenge instance.

---
## Datos de acceso al nivel 

Dentro de la pagina se tiene que crear una instancia para poder seguir con el reto para crearla basta con oprimir el botón que aparece 

``` 
servidor   : ssh ctf-player@venus.picoctf.net -p 58164
contraseña : 6dee9772
``` 

---
## Solución 

``` bash
ssh ctf-player@venus.picoctf.net -p 58164
# ctf-player@venus.picoctf.net's password: 
6dee9772
# Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

ls
# 1of3.flag.txt  instructions-to-2of3.txt
cat 1of3.flag.txt 
# picoCTF{xxsh_
cat instructions-to-2of3.txt
# Next, go to the root of all things, more succinctly `/`
cd ..
ls
# 3of3.flag.txt  drop-in
at 3of3.flag.txt
# 540e4e79}
cd ..
cd ..
ls
# 2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

cat 2of3.flag.txt 
# 0ut_0f_\/\/4t3r_

```

**Resultado Final**

uniendo manualmente todas las partes de la llave tenemos 
``` bash
picoCTF{xxsh_0ut_0f_\/\/4t3r_540e4e79}
```

---
## Notas Adicionales 

---
## Referencias 