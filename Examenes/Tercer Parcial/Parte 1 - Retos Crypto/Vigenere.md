## Objetivo 

Can you decrypt this message? Decrypt this [message](https://artifacts.picoctf.net/c/159/cipher.txt) using this key "CYLAB".

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/159/cipher.txt

---
## Solución 
Para solucionar este problema usaremos [CyberChef](https://gchq.github.io/CyberChef/), lo primero es analizar lo que dice el mensaje el cual es el siguiente:

``` bash
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_f85729e7}
```

Después de esto tenemos que ir a [CyberChef](https://gchq.github.io/CyberChef/) y seleccionar la opción `Vigenere Decode` la cual pedirá una llave, en este caso la llave es `CYLAB` y con el mensaje puesto en la parte de entrada la salida seria 

**Resultado Final**
```
picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_d85729g7}
```

---
## Notas Adicionales 

---
## Referencias 
https://gchq.github.io/CyberChef/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfZjg1NzI5ZTd9
