## Objetivo 

We have several pages hidden. Can you find the one with the flag? The website is running [here](http://saturn.picoctf.net:64727/).

---
## Datos de acceso al nivel 

http://saturn.picoctf.net:64727/

---
## Solución 

este reto va de modificar la URL por lo que un ves ingresemos a la pagina debemo ver su codigo fuente, para ello usamos el comando `ctrl`+`u`

dentro de la pagina tenemos que acceder al archivo [secret/assets/index.css](view-source:http://saturn.picoctf.net:64727/secret/assets/index.css) 
cuando estemos dentro tendremos que modificar la dirección borrando la parte de `assets/index.css` 

Antes
``` bash
http://saturn.picoctf.net:64727/secret/assets/index.css
```

Después
```
http://saturn.picoctf.net:64727/secret/
```

cuando estemos dentro de esa ruta veremos el siguiente archivo [hidden/file.css](view-source:http://saturn.picoctf.net:64727/secret/hidden/file.css) al cual tema bien tenemos que acceder 

una ves dentro no aparecerá nada y tendremos que seguir modificando la ruta borrando la parte de `file.css`

Antes 
```
http://saturn.picoctf.net:64727/secret/hidden/file.css
```

Después
```
http://saturn.picoctf.net:64727/secret/hidden/
```

cuando ingresemos aparecerá algo de información pero lo que nos interesa es acceder al archivo 
[superhidden/login.css](view-source:http://saturn.picoctf.net:64727/secret/hidden/superhidden/login.css) 

dentro de este archivo tenemos que volver a modificar la ruta o dirección eliminado la parte de `login.css` por lo que la ruta quedaría de esta forma 

```
http://saturn.picoctf.net:64727/secret/hidden/superhidden/
```

por ultimo cuando ingresemos al ultimo sitio aparecerá la contraseña 

**Resultado Final**
```
picoCTF{succ3ss_@h3n1c@10n_790d2615}
```


---
## Notas Adicionales 


---
## Referencias 