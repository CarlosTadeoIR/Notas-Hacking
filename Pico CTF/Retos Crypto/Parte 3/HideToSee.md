## Objetivo 

How about some hide and seek heh? Look at this image [here](https://artifacts.picoctf.net/c/238/atbash.jpg).

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/238/atbash.jpg

---
## Solución 

cuando descarguemos la imagen tenemos que acceder a la pagina https://futureboy.us/stegano/decinput.html donde tendremos que ingresar el archivo de la imagen, esto nos dara de resultado la siguiente cadena 

```
krxlXGU{zgyzhs_xizxp_8z0uvwwx}
```

Después tenemos que acceder a la pagina  https://www.dcode.fr/atbash-cipher en la cual pegaremos la cadena anterior, esto nos dará de resultado la bandera 

``` bash
picoCTF{atbash_crack_8a0feddc}
```

**Resultado Final**
```
picoCTF{atbash_crack_8a0feddc}
```

---
## Notas Adicionales 

---
## Referencias 
https://futureboy.us/stegano/decinput.html

https://www.dcode.fr/atbash-cipher