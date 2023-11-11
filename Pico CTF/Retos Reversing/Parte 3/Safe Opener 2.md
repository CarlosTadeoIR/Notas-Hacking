## Objetivo 

What can you do with this file? I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/291/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/291/SafeOpener.class

---
## Solución 

cuando descarguemos el archivo solo tenemos que ejecutar el siguiente comando 
```shell
strings SafeOpener.class | grep  pico
```

**Resultado Final**
```
picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_198203f7}
```

---
## Notas Adicionales 
grep, de los mejores comandos 

---
## Referencias 