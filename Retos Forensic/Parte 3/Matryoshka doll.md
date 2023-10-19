## Objetivo 

Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg)

---
## Datos de acceso al nivel 

https://mercury.picoctf.net/static/1b70cffdd2f05427fff97d13c496963f/dolls.jpg

---
## Solución 
una ves descargado el archivo lo tenemos que poner en una carpeta aparte ya que se crearan muchas cosas 

lo primero que tenemos que hacer es ver que se encuentra dentro de la imagen 
``` bash
binwalk dolls.jpg 

# DECIMAL       HEXADECIMAL     DESCRIPTION
# --------------------------------------------------------------------------------
# 0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
# 3226          0xC9A           TIFF image data, big-endian, offset of first image # directory: 8
# 272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378954, uncompressed size: 383938, name: base_images/2_c.jpg
# 651612        0x9F15C         End of Zip archive, footer length: 22

```

como podemos ver dentro se encuentra una imagen por lo que la forma de secarla es la siguiente 

```bash
foremost dolls.jpg 
# Processing: dolls.jpg
# |foundat=base_images/2_c.jpgUT
# *|
````

después de extraer el contendido de la imagen se creara en automático una carpeta llamada `output`, la forma de acceder al contenido es la siguiente:

```bash 
ls
# dolls.jpg  output
cd output                                                                               
ls
# audit.txt  png  zip
cd zip   
ls
# 00000532.zip
unzip 00000532.zip      
# Archive:  00000532.zip
#  inflating: base_images/2_c.jpg     
ls
# 00000532.zip  base_images
cd base_images 
ls
# 2_c.jpg

```


llegado a este punto se debe repetir el proceso anterior aplicando primero el comando `binwalk` para ver el contendió de la nueva imagen y después el comando `foremost` para extraer el resultado, esto hasta que lleguemos a la llave 

**El procedimiento completo retomando desde lo anterior seria el siguiente**
verificamos si la imagen tiene archivos adjuntos
```bash
binwalk 2_c.jpg  

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196043, uncompressed size: 201445, name: base_images/3_c.jpg
383805        0x5DB3D         End of Zip archive, footer length: 22
383916        0x5DBAC         End of Zip archive, footer length: 22

```

sacamos los archivos 
```
foremost 2_c.jpg  
Processing: 2_c.jpg
|foundat=base_images/3_c.jpgUT
*|
```

accedemos a los archivos
```bash
ls
# 2_c.jpg  output
cd output     
ls
# audit.txt  png  zip
cd zip   
la
# 00000366.zip
unzip 00000366.zip 
# Archive:  00000366.zip
#  inflating: base_images/3_c.jpg     
ls
# 00000366.zip  base_images
cd base_images 
ls
# 3_c.jpg

```

**volvemos a repetir los paso anterior**
verificamos si existen archivos dentro de la imagen 
```bash
binwalk 3_c.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77651, uncompressed size: 79807, name: base_images/4_c.jpg
201423        0x312CF         End of Zip archive, footer length: 22

```

extraemos los archivos 

```bash
foremost 3_c.jpg     
Processing: 3_c.jpg
|foundat=base_images/4_c.jpgUT
*|
```

accedemos a los archivos

```bash
ls
# 3_c.jpg  output
cd output     
ls
# audit.txt  png  zip
cd zip   
ls
# 00000241.zip
unzip 00000241.zip
# Archive:  00000241.zip
#  inflating: base_images/4_c.jpg     
ls
# 00000241.zip  base_images
cd base_images 
ls
# 4_c.jpg

```

**volvemos a repetir los pasos otra ves**

verificamos si la imagen tiene archivos adjuntos 
```bash
binwalk 4_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 63, uncompressed size: 81, name: flag.txt
79785         0x137A9         End of Zip archive, footer length: 22

```

como se puede ver ya encontramos la bandera por lo que ahora solo queda acceder a ella de la misma forma que hemos estado trabajando 

extraemos los archivos de la imagen 

```bash
foremost 4_c.jpg
Processing: 4_c.jpg
|foundat=flag.txtUT
*|
```

accedemos a los archivos

```bash
ls
# 4_c.jpg  output
cd output     
ls
# audit.txt  png  zip
cd zip   
ls
# 00000155.zip
unzip 00000155.zip
# Archive:  00000155.zip
#  inflating: flag.txt                
ls
#00000155.zip  flag.txt

```

ya tenemos el archivo de la bandera por lo que ahora solo queda ver su contenido 

```bash
cat flag.txt 
# picoCTF{bf6acf878dcbd752f4721e41b1b1b66b}
```

**Resultado Final**
```
picoCTF{bf6acf878dcbd752f4721e41b1b1b66b} 
```

---
## Notas Adicionales 

---
## Referencias 