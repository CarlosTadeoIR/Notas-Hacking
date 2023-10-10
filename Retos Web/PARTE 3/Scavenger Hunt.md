## Objetivo 

There is some interesting information hidden around this site [http://mercury.picoctf.net:55079/](http://mercury.picoctf.net:55079/). Can you find it?

---
## Datos de acceso al nivel 

http://mercury.picoctf.net:55079/

---
## Solución 

una ves dentro de la pagina solo presionamos Ctrl + u lo cual nos mandara al código fuente de la pagina 

![[Pasted image 20231009233706.png]]

Como se puede ver en el HTML aparece la primera parte, la parte 2 y 3 por lo que dice el HTML aparece en los archivos css y js 

la segunda parte de la bandera se encuentra al final del archivo css

![[Pasted image 20231009234003.png]]

la tercera parte se debería de encontrar en el archivo js pero encontramos lo siguiente
![[Pasted image 20231009234148.png]]
al final nos dice que busquemos eso en Google, en resumen es lo del archivo robots.txt al cual podemos acceder modificando la liga original añadiendo robots.txt de esta forma  

```
http://mercury.picoctf.net:55079/robots.txt
```

una ves dentro aparece lo siguiente
![[Pasted image 20231009234413.png]]

ya tenemos las 3 partes pero ahora dice que existe otra parte y nos da una pista, para llegar a ella por lo que ahora para acceder a la cuarta parte de la llave tenemos que cambiar la liga nuevamente pero ahora de esta forma 

``` bash
http://mercury.picoctf.net:55079/.htaccess
```

accedemos y nos da la cuarta parte pero ahora toca encontrar una quinta parte 

![[Pasted image 20231010000658.png]]

para acceder a la quinta parte ahora debemos cambiar la liga anterior por 

``` bash
http://mercury.picoctf.net:55079/.DS_Store
```

![[Pasted image 20231010001347.png]]

ya teniendo las 5 partes solo queda unirlas

**Resultado final**
```
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_74cceb07}
```
---
## Notas Adicionales 

En el caso de la cuarta parte de la llave que nos habla de un servidor apache. 

Un fichero **.htaccess** (o lo que es lo mismo hypertext access) es un tipo de archivo especial que se utiliza dentro de los alojamientos web que funcionan con servidores Apache. 
El fichero .htaccess permite modificar diferentes variables en la configuración de nuestra cuenta de alojamiento en el servidor.

Para la quinta parte de la llave que nos dice que le encanta como se ve el sitio por tener su MAC  
Los archivos .DS_Store _(Desktop Services Store)_ son ficheros que contienen información de personalización del sistema, como puede ser los iconos, tipo de fondo, fuente, columnas, etc.

---
## Referencias

[¿Qué es y para qué sirve el .htaccess? (hostinet.com)](https://www.hostinet.com/formacion/hosting-alojamiento/que-es-para-que-sirve-htaccess/)
[Qué son los archivos .DS_Store y para qué sirven - Vozidea.com](https://www.vozidea.com/archivos-ds_store)
