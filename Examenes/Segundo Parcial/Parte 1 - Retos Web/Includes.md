## Objetivo 

Can you get the flag? Go to this [website](http://saturn.picoctf.net:58519/) and see what you can discover.

---
## Datos de acceso al nivel 

http://saturn.picoctf.net:58519/

---
## Solución 
lo primero que tenemos que hacer dentro de la pagina web es inspeccionar el código fuente para ello usamos el comando `ctrl` + `u` 

dentro del código fuente tenemos que dar click sobre el archivo [style.css](view-source:http://saturn.picoctf.net:58519/style.css) el cual contiene la primera parte de la bandera

``` bash
picoCTF{1nclu51v17y_1of2_
```

después regresamos al código fuente y accedemos al archivo [script.js](view-source:http://saturn.picoctf.net:58519/script.js) el cual contendrá la ultima parte de la llave 

```
f7w_2of2_b8f4b022}
```

por ultimo solo queda unir las partes

**Resultado Final**
```
picoCTF{1nclu51v17y_1of2_f7w_2of2_b8f4b022}
```

---
## Notas Adicionales 

---
## Referencias 