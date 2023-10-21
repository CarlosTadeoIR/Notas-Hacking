## Objetivo 

The developer of this website mistakenly left an important artifact in the website source, can you find it? The website is [here](http://saturn.picoctf.net:65086/)

---
## Datos de acceso al nivel 

http://saturn.picoctf.net:65086/

---
## Solución 

cuando ingresemos al sitio web tenemos que inspeccionar su código fuente para ello usaremos el comando `ctrl`+`u`. 

Dentro del código fuente tenemos que acceder al archivo [css/style.css](view-source:http://saturn.picoctf.net:65086/css/style.css) el cual se encuentra en la linea 21, dentro del archivo podemos usar el comando `ctrl`+`f` para facilitarnos la búsqueda de la llave ya que se abrirá un buscador de palabras en el cual debemos escribir la palabra `pico` y nos llevara directo a la bandera 

``` 
/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/
```

**Resultado Final**
```
picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8}
```

---
## Notas Adicionales 

---
## Referencias 