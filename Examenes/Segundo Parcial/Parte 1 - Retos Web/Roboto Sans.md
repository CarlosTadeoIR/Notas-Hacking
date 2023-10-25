## Objetivo 

The flag is somewhere on this web application not necessarily on the website. Find it. Check [this](http://saturn.picoctf.net:56615/) out.

---
## Datos de acceso al nivel 

http://saturn.picoctf.net:56615/

---
## Solución 

una ves accedemos a la pagina debemos cambiar su ruta agregado `/robots.txt` al final por lo que la ruta completa seria la siguiente 

``` bash
http://saturn.picoctf.net:56615/robots.txt
```

una ves dentro del sitio aparece la siguiente información
```
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```

como podemos ver, la cadena `anMvbXlmaWxlLnR4dA==` parecer estar cifrada en base64 por lo que con ayuda de [CyberChef](https://gchq.github.io/CyberChef/) descubriremos que lo que dice es `js/myfile.txt`, teniendo esto en cuenta volveremos a editar la ruta o dirección de la pagina por la siguiente 

```
http://saturn.picoctf.net:56615/js/myfile.txt
```

al hacer esto y acceder a esa dirección aparecerá la bandera 

**Resultado Final**
```
picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}
```

---
## Notas Adicionales 

---
## Referencias 
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YW5NdmJYbG1hV3hsTG5SNGRBPT0
