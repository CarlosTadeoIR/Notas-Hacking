## Objetivo 

What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png

---
## Solución 

Cuando descarguemos el archivo veremos que se trata de una imagen con diferentes banderas, por lo que tendremos que buscar cada bandera, la ventaja es que sabemos que los primeros caracteres corresponden a `picoCTF` por lo que ya solo faltaría buscar los demás 

![[Captura Flags.jpg]]

``` bash
P - Papa
I - India
C - Charlie
O - Oscar
C - Charlie
T - Tango
F - Foxtrot
{
F - Foxtrot
1 - One
A - Alfa
G - Golf
5 - Five
A - Alfa
N - November
D - Delta
5 - Five 
T - Tango
U - Uniform
F - Foxtrot
F - Foxtrot
}
```

Identificadas las banderas ahora solo queda armar la bandera 

**Resultado Final**
```
PICOCTF{F1AG5AND5TUFF}
```


---
## Notas Adicionales 


---
## Referencias 
https://en.wikipedia.org/wiki/International_maritime_signal_flags