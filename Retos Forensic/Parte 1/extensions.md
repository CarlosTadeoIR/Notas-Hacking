## Objetivo 

This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt

---
## Solución 

después de descargar el archivo que supuestamente es un .txt debemos usar el siguiente comando para saber que tipo de archivo es 

``` bash
file flag.txt
#flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
```

como podemos ver el archivo no es mas que un PNG por lo que solo le cambiamos la extensión y abrimos el PNG de forma normal ya que dentro esta la bandera 

![[flagg.png]]

**Resultado Final**
```
picoCTF{now_you_know_about_extensions}
```

---
## Notas Adicionales 

---
## Referencias 