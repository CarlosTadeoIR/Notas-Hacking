## Objetivo 

This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/87e103a8db01087de9ccf5a7a022ddf8/VaultDoor1.java

---
## Solución 

una forma de solucionar este problema es que después de descargar el archivo, podemos extraer lo siguiente del código fuente  y guardarlo en un archivo nuevo modificando los numeros de un digito agregándoles un `0` a su izquierda 

```

               password.charAt(00)  == 'd' &&
               password.charAt(29) == 'a' &&
               password.charAt(04)  == 'r' &&
               password.charAt(02)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(03)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(01)  == '3' &&
               password.charAt(07)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(05)  == '4' &&
               password.charAt(09)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(08)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(06)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '6' &&
               password.charAt(30) == 'f' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == 'd' &&
               password.charAt(26) == 'f' &&
               password.charAt(31) == '4';
```


Después de guardar el archivo tenemos que ejecutar el siguiente comando sobre el nuevo archivo 

``` bash
cat flag | sort | awk '{print $3}' | tr -d "'" | tr -d "\n"
# d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4; 
```

**Resultado Final**
```
picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_f6daf4}
```


---
## Notas Adicionales 


---
## Referencias 