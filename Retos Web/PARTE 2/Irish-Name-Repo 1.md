## Objetivo 

There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!

---
## Datos de acceso al nivel 

http://jupiter.challenges.picoctf.org:39720/

---
## Solución 

Lo primero que se debe de hacer es ira al apartado de login para registrarnos 
![[Pasted image 20231009200801.png]]

una ves dentro veremos lo siguiente

![[Pasted image 20231009200827.png]]

antes de continuar debemos inspeccionar la pagina ya que oculta algo interesante 

![[Pasted image 20231009201011.png]]

como podemos ver cuenta con un campo oculto el cual tendremos que modificar para que sea visible de la siguiente forma 
![[Pasted image 20231009201138.png]]

una ves echo esto podemos poner en username el valor que nosotros queramos pero en password la contraseña debe ser la siguiente 

``` 
'or 1 = 1;
```

así mimos el valor del ultimo recuadro debe de ser 1 en lugar de 0 ya que esto habilitara el registro de depuración 

![[Pasted image 20231009201450.png]]

![[Pasted image 20231009201510.png]]

**Resultado Final**
```
picoCTF{s0m3_SQL_c218b685}
```

---
## Notas Adicionales 

La cadena de caracteres 'or 1 = 1; es una condición de búsqueda que se utiliza en el lenguaje SQL para filtrar los resultados de una consulta. La condición '1 = 1' es una expresión booleana que siempre devuelve True. Por lo tanto, la cadena completa 'or 1 = 1;' se utiliza para devolver todos los resultados de una consulta, sin importar las condiciones de búsqueda que se hayan especificado originalmente 1.

Otra forma de acceder a la llave es mediante la linea de comando con el siguiente:

```bash 
curl https://jupiter.challenges.picoctf.org/problem/39720/login.php -d "username=admin&password='or 1=1;&debug=1"
```


---
## Referencias 
[SQL Injection (w3schools.com)](https://www.w3schools.com/sql/sql_injection.asp)
