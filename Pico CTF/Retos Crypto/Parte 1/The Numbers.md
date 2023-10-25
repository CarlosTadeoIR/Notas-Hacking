## Objetivo 

The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png

---
## Solución 

cuando descarguemos el archivo tenemos que abrirlo para ver su contenido, en este caso el contenido es el siguiente 

``` bash
16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }
```

cada numero representa una letra del abecedario por lo que solo tenemos que hacer la conversión o bien usar la pagina [CyberChef](https://gchq.github.io/CyberChef/) con el parámetro `A1Z26 cipher  decode` y obtendremos la bandera 

**Resultado Final**
```
picoCTF{thenumbersmason}
```

---
## Notas Adicionales 

---
## Referencias 