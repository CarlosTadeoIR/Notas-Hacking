## Objetivo 

Now you DON’T see me. This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf

---
## Solución 

una ves descargamos el archivo PDF lo abrimos con el nuestro navegador, se puede ver que ahí partes censuradas que no se pueden leer pero si usamos la opción de inspeccionar podemos ver lo siguiente 

``` html 
<span style="left: 120px; top: 490.667px; font-size: 20px; font-family: sans-serif; transform: scaleX(0.761871);" role="presentation" dir="ltr">picoCTF{C</span>
<span style="left: 200.654px; top: 490.667px; font-size: 20px; font-family: sans-serif; transform: scaleX(0.812441);" role="presentation" dir="ltr">4n</span>
<span style="left: 221.299px; top: 490.667px; font-size: 20px; font-family: sans-serif; transform: scaleX(0.84412);" role="presentation" dir="ltr">_Y0u_S33_m</span>
<span style="left: 327.012px; top: 490.667px; font-size: 20px; font-family: sans-serif; transform: scaleX(0.784034);" role="presentation" dir="ltr">3_fully}</span>
```

una ves tengamos ubicada las partes de la llave bastara con unirlas manualmente 

**Resultado Final**
```
picoCTF{C4n_Y0u_S33_m3_fully}
```

---
## Notas Adicionales 

---
## Referencias 