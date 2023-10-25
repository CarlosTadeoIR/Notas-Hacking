## Objetivo 

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

---
## Datos de acceso al nivel 

se necesita descargar el  siguiente archivo 
https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings

---
## Solución 

``` bash
strings strings | grep pico
#picoCTF{5tRIng5_1T_7f766a23}

```

**Resultado Final**
```
picoCTF{5tRIng5_1T_7f766a23}
```


---
## Notas Adicionales 
nuevamente se vuelve a usar grep, tal ves debería de poner un contador de cuantas veces se usa para llegar a la solución 

---
## Referencias 