## Objetivo 

The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt

---
## Solución 

la forma mas facil de hacer esto es ir a [CyberChef](https://gchq.github.io/CyberChef/) pegar en `input` la palabra `UFJKXQZQUNB`, seleccionar en `operations` el parámetro `Vigenere Decode` el cual nos pedirá ingresar una llave que en este caso seria `SOLVECRYPTO`, una ves terminemos esto aparecerá la siguiente palabra en la salida  

``` bash
CRYPTOISFUN
```

por lo que ahora solo queda darle formato a la bandera 

**Resultado Final**
```
picoCTF{CRYPTOISFUN}
```

---
## Notas Adicionales 

---
## Referencias 
https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkI

