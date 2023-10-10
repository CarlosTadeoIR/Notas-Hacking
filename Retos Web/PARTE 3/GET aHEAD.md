## Objetivo 

Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:28916/](http://mercury.picoctf.net:28916/)

---
## Datos de acceso al nivel 

http://mercury.picoctf.net:28916/

---
## Solución 

si accedemos a la pagina http://mercury.picoctf.net:28916/ veremos lo siguiente

![[Pasted image 20231010004535.png]]

la forma mas sencilla de llegar a la llave es conectándonos a la pagina mediante la linea de comando con el siguiente comando  

``` bash
curl -I http://mercury.picoctf.net:28916/index.php
```

donde el parámetro `-I`  sólo recupere las cabeceras

**Resultado Final**
```
picoCTF{r3j3ct_th3_du4l1ty_70bc61c4}
```

---
## Notas Adicionales 

---
## Referencias 
[cURL: ejemplos de GET requests - Marc Nuri](https://blog.marcnuri.com/curl-get-request-ejemplos#:~:text=Puedes%20utilizar%20la%20opci%C3%B3n%20-I%2C%20--head%20para%20indicarle,realice%20una%20petici%C3%B3n%20HTTP%20HEAD.%20curl%20-I%20https%3A%2F%2Fblog.marcnuri.com)
