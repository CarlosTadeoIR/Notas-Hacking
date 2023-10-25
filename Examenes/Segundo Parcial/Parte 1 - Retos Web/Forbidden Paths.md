## Objetivo 

Can you get the flag? Here's the [website](http://saturn.picoctf.net:55793/). We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

---
## Datos de acceso al nivel 

http://saturn.picoctf.net:55793/

---
## Solución 

en la descripción del reto se nos dice que una ves ingresemos a la pagina estaremos en la sección `/usr/share/nginx/html/` y que la bandera esta en `/flag.txt` el problema es que la pagina filtra las rutas absolutas 

para ello la solución es ingresar el siguiente mensaje en el cuadro de búsqueda que tiene la pagina, por lo que una ves ingresemos aparecerá la contraseña 

``` bash
../../../../flag.txt
```

**Resultado Final**
```
picoCTF{7h3_p47h_70_5ucc355_e5a6fcbc}
```

---
## Notas Adicionales 

al ser un filtrado de rutas absolutas se debe indicar el camino desde el directorio raíz hasta llegar a al archivo, visto de otra forma seria como poner  `usr/share/nginx/html/flag.txt`  solo que si lo ponemos de esa forma no funcionaria para ello se usa `../../../../flag.txt`

---
## Referencias 
https://denovatoanovato.net/rutas-relativas-y-rutas-absolutas/
