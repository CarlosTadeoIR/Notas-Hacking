## Objetivo 

Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng).

---
## Datos de acceso al nivel 

https://mercury.picoctf.net/static/4c996ecfb7fbada15a9799511f24dc99/shark1.pcapng

---
## Solución 

cuando descarguemos el archivo tenemos que abrirlo con la herramienta Wireshark.

cuando tengamos abierto el paquete de datos basta con dar click derecho sobre alguno que tenga el protocolo TCP  después a la opción follow y por ultimo a la opción TCP Stream.

cuando estemos dentro tenemos que ir hasta el Stream numero 5 donde al final aparecerá la siguiente cadena 

``` bash
Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}
```

esta cadena se encuentra codificada usando el método de rotación por lo que con ayuda de [CyberChef](https://gchq.github.io/CyberChef/) rotaremos la cadena con rot13.

```
The flag is picoCTF{p33kab00_1_s33_u_deadbeef}
```

**Resultado Final**
```
picoCTF{p33kab00_1_s33_u_deadbeef}
```

---
## Notas Adicionales 

---
## Referencias 
https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=R3VyIHN5bnQgdmYgY3ZwYlBHU3tjMzN4bm8wMF8xX2YzM19oX3FybnFvcnJzfQ