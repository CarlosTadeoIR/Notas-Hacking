## Objetivo 

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

---
## Datos de acceso al nivel 

``` bash
jupiter.challenges.picoctf.org 4427
```

---
## Solución 

``` bash
nc jupiter.challenges.picoctf.org 4427 | grep pico
picoCTF{digital_plumb3r_5ea1fbd7}
```

**Resultado Final**
```
picoCTF{digital_plumb3r_5ea1fbd7}
```


---
## Notas Adicionales 

Nuevamente es necesario el uso del gran y poderos `GREP` salve el poderosamente `GREP` 

---
## Referencias 