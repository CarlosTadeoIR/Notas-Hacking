## Objetivo 

Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message. Download the corrupted message [here](https://artifacts.picoctf.net/c/192/message.txt).

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/192/message.txt

---
## Solución 

si analizamos el mensaje corrupto veremos que este es su contenido 
``` bash
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V091B0AE}2
```

para resolver este reto nos ayudaremos de la siguiente pagina https://tholman.com/other/transposition/  donde ingresaremos nuestra cadena de mensaje, posterior a eso nos pedirá un numero de llave el cual según la pista proporcionada por el reto es 3 

Cuando le demos al boton de `(re)load table` en la parte de abajo aparecerá una secuencia del 0 al 2 
```
0 1 2 
```

lo que tenemos que hacer es arrastrar el 2 a la primera posición de tal forma que quede así 
```
2 0 1
```

esto nos dará como resultado lo siguiente 
```
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}
```

**Resultado Final**
```
picoCTF{7R4N5P051N6_15_3XP3N51V3_109AB02E}
```

---
## Notas Adicionales 

---
## Referencias 
https://tholman.com/other/transposition/