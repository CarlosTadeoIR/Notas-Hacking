## Objetivo 

Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg)

---
## Datos de acceso al nivel 

https://mercury.picoctf.net/static/149ab4b27d16922142a1e8381677d76f/cat.jpg

---
## Solución 
cuando tengamos la imagen descargada tenemos que dirigirnos a su ubicacion desde la linea de comando y aplicar el siguiente comando

``` bash
exiftool cat.jpg

# ExifTool Version Number         : 12.57
# File Name                       : cat.jpg
# Directory                       : .
# File Size                       : 878 kB
# File Modification Date/Time     : 2023:10:21 14:30:06-04:00
# File Access Date/Time           : 2023:10:21 14:30:13-04:00
# File Inode Change Date/Time     : 2023:10:21 14:30:06-04:00
# File Permissions                : -rw-r--r--
# File Type                       : JPEG
# File Type Extension             : jpg
# MIME Type                       : image/jpeg
# JFIF Version                    : 1.02
# Resolution Unit                 : None
# X Resolution                    : 1
# Y Resolution                    : 1
# Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
# Copyright Notice                : PicoCTF
# Application Record Version      : 4
# XMP Toolkit                     : Image::ExifTool 10.80
# License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
# Rights                          : PicoCTF
# Image Width                     : 2560
# Image Height                    : 1598
# Encoding Process                : Baseline DCT, Huffman coding
# Bits Per Sample                 : 8
# Color Components                : 3
# Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
# Image Size                      : 2560x1598
# Megapixels                      : 4.1

```

lo que nos interesa de esta parte es la descripción de `License`

```
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
```

ya que su atributo esta codificado en base64 por lo que haciendo uso de la herramienta [CyberChef](https://gchq.github.io/CyberChef/) decodificamos el mensaje  

**Resultado Final**
```
picoCTF{the_m3tadata_1s_modified}
```

---
## Notas Adicionales 

---
## Referencias 
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQwYUdWZmJUTjBZV1JoZEdGZk1YTmZiVzlrYVdacFpXUjk