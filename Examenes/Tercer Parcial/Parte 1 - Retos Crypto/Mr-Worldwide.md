## Objetivo 

A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt

---
## Solución 

Al momento de analizar el mensaje veremos lo siguiente 
``` bash
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}
```

Como podemos ver la parte interna de la bandera se encuentra repleta de coordenadas por lo que tocara buscar cada una de ellas en https://maps.google.com.mx o bien en la barra de búsqueda de cualquier navegador 

```
(35.028309, 135.753082)  = Kioto         = K
(46.469391, 30.740883)   = Odesa         = O
(39.758949, -84.191605)  = Dayton        = D
(41.015137, 28.979530)   = Istanbul      = I
(24.466667, 54.366669)   = Abu Dhabi     = A
(3.140853, 101.693207)   = Kuala Lumpur  = K
__
(9.005401, 38.763611)    = Adís Abeb     = A
(-3.989038, -79.203560)  = Loja          = L
(52.377956, 4.897070)    = Ámsterdam     = A
(41.085651, -73.858467)  = Sleepy Hollow = S
(57.790001, -152.407227) = Kodiak        = K
(31.205753, 29.924526)   = Alejandría    = A
```

Ahora solo queda completar la bandera 

**Resultado Final**
```
picoCTF{KODIAK_ALASKA}
```


---
## Notas Adicionales 


---
## Referencias 
https://maps.google.com.mx/