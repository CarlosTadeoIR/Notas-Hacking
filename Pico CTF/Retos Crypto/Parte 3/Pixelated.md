## Objetivo 

I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)

---
## Datos de acceso al nivel 

https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png

https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png

---
## Solución 

existen 2 formas de hacer esto, la mas sencilla es creando un script de Python el cual tendrá lo siguiente  

``` python
from PIL import Image 
import numpy as np 

imagen1 = np.asarray( Image.open('scrambled1.png'))
imagen2 = np.asarray( Image.open('scrambled2.png'))

print(imagen1)
print(imagen2)

datos = imagen1.copy() + imagen2.copy()

nueva = Image.fromarray(datos)

nueva.save('nueva.png','PNG')
```

Después de importar las librerías lo siguiente a hacer es guardar las imágenes para después mostrarlas como matrices, gracias a esto podemos usar una herramienta de la misma librería para juntar las 2 matrices resultantes en una sola.

cuando tengamos nuestro script listo solo tenemos que ejecutarlo 
```bash
python3 pixel.py 

[[[154  35 148]
  [178 114 134]
  [ 63  77 225]
  ...
  [212  21 244]
  [ 31 223 118]
  [ 54  89  60]]

 [[ 15 148 201]
  [186  40  68]
  [233 222 246]
  ...
  [ 58  83  71]
  [121 159  43]
  [183 190 214]]

 [[162 157 135]
  [ 15  26 156]
  [202 176 190]
  ...
  [241 111 100]
  [ 61 102  25]
  [ 76 115 212]]

 ...

 [[116 140  23]
  [134 156 221]
  [123 244  76]
  ...
  [ 23  37 162]
  [ 48 191 142]
  [ 97 254 142]]

 [[150 158 232]
  [240 212 155]
  [215  34 166]
  ...
  [112 222 163]
  [242 172 109]
  [157 201  74]]

 [[100  32 237]
  [ 99  72 194]
  [234 106  78]
  ...
  [ 14 152 111]
  [ 98   1 240]
  [180 133  47]]]
[[[101 220 107]
  [ 77 141 121]
  [192 178  30]
  ...
  [ 43 234  11]
  [224  32 137]
  [201 166 195]]

 [[240 107  54]
  [ 69 215 187]
  [ 22  33   9]
  ...
  [197 172 184]
  [134  96 212]
  [ 72  65  41]]

 [[ 93  98 120]
  [240 229  99]
  [ 53  79  65]
  ...
  [ 14 144 155]
  [194 153 230]
  [179 140  43]]

 ...

 [[139 115 232]
  [121  99  34]
  [132  11 179]
  ...
  [232 218  93]
  [207  64 113]
  [158   1 113]]

 [[105  97  23]
  [ 15  43 100]
  [ 40 221  89]
  ...
  [143  33  92]
  [ 13  83 146]
  [ 98  54 181]]

 [[155 223  18]
  [156 183  61]
  [ 21 149 177]
  ...
  [241 103 144]
  [157 254  15]
  [ 75 122 208]]]

```

Cuando hagamos esto se creara una imagen nueva, bastara solo con abrirla y ver lo que dice, en este caso la bandera 

**Resultado Final**
```
picoCTF{d562333d}
```


---
## Notas Adicionales 


---
## Referencias 
https://en.wikipedia.org/wiki/Visual_cryptography
