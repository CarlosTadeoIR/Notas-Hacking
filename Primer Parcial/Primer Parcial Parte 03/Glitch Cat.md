## Objetivo 

Our flag printing service has started glitching! `$ nc saturn.picoctf.net 52682`

---
## Datos de acceso al nivel 

``` bash
 nc saturn.picoctf.net 52682
```

---
## Solución 

``` bash
nc saturn.picoctf.net 52682
# 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
```

Para solucionar esto abrimos Python 

```Python
python3
>>> print ('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')

picoCTF{gl17ch_m3_n07_bda68f75}

```

**Resultado Final**

```
picoCTF{gl17ch_m3_n07_bda68f75}
```
---
## Notas Adicionales 

internamente Python es capas de manejar chr()  

---
## Referencias 