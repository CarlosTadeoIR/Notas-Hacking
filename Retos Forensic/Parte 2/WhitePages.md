## Objetivo 

I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt) is all blank!

---
## Datos de acceso al nivel 
https://jupiter.challenges.picoctf.org/static/95be9526e162185c741259a75dffa0ab/whitepages.txt

---
## Solución 

una ves descargado el archivo, si lo intentamos abrir notaremos que aparentemente no tiene nada 
por lo que si usamos la herramienta `xxd` veremos lo siguiente

```bash 
xxd whitepages.txt | head 
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2 8083 e280 83e2 8083 2020 e280  .  .........  ..
00000070: 8320 20e2 8083 2020 2020 e280 8320 e280  .  ...    ... ..
00000080: 83e2 8083 e280 83e2 8083 2020 e280 8320  ..........  ... 
00000090: e280 8320 e280 8320 e280 83e2 8083 e280  ... ... ........

```

entre todos los numero vemos que son 2 secuencias las que se repiten 
`e280 83` y `20` el primero corresponde a un carácter vacío como tal mientras que el segundo es la forma de dar espacio en el formato ASCII 

para dar solución a este problema primero debemos instalar la herramienta `pwntools` de la siguiente manera 

``` bash
sudo python3 -m pip install pwntools
```

una ves instalada, nos ubicamos en el directorio donde se encuentra nuestro archivo y creamos un archivo .py con el siguiente script  

```
from pwn import *

file = open('whitepages.txt','rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)

```

este script se encargara de transformar todos los `e280 83` en 0 y todos los `20` en 1 al final mostrara la traducción completa 

```
python3 exp.py              
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}\n\t\t'
```


**Resultado Final**
```
picoCTF{not_all_spaces_are_created_equal_7100860b0fa779a5bd8ce29f24f586dc}
```

---
## Notas Adicionales 

---
## Referencias 
[Unicode - Wikiwand](https://www.wikiwand.com/en/Unicode)
[UTF-8 - Wikiwand](https://www.wikiwand.com/en/UTF-8)
