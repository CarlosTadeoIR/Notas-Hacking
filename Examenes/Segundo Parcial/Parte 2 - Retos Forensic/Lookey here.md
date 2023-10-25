## Objetivo 

Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/125/anthem.flag.txt).

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/125/anthem.flag.txt

---
## Solución 

cuando descarguemos el archivo tenemos que abrirlo para ver su contendió y buscar la llave, la mejor forma de buscar y encontrar la llave es ir a la linea de comando y ejecutar el siguiente comando 

``` bash
cat anthem.flag.txt | grep pico
# we think that the men of picoCTF{gr3p_15_@w3s0m3_58f5c024}
```

**Resultado Final**
```
picoCTF{gr3p_15_@w3s0m3_58f5c024}
```

---
## Notas Adicionales 

por alguna razón esperaba algo mas complicado

---
## Referencias 