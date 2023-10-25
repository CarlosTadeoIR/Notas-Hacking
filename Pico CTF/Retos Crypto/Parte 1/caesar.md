## Objetivo 

Decrypt this [message](https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext).

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/7d707a443e95054dc4cf30b1d9522ef0/ciphertext

---
## Solución 

si abrimos el archivo notaremos que la cadena que contiene como bandera esta bien al principio pero luego se pone rara. 

Para dar solución a este problema tenemos que usar la siguiente pagina https://cryptii.com/pipes/caesar-cipher donde le pasaremos de parámetro lo que viene en el archivo de texto  

``` bash
picoCTF{gvswwmrkxlivyfmgsrhnrisegl}
```

una ves le pasemos ese parámetro tendremos que seleccionar la opción que cambia `a->w` en este caso el numero 22 lo que nos dará lo siguiente como resultado.

```
leykCTF{crossingtherubicondjneoach}
```

ahora solo es cuestión  de  tomar la parte interna de los `{}` y formar la llave 

**Resultado Final**
```
picoCTF{crossingtherubicondjneoach}
```
---
## Notas Adicionales 

---
## Referencias 