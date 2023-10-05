## Objetivo 

You have the file 2023Metared.jpg Can you find the flag?

---
## Datos de acceso al nivel 

https://ctfd.anuies.mx/files/bc8e90261d26030d76237cba0791d30b/2023Metared.jpg?token=eyJ1c2VyX2lkIjoyNDIsInRlYW1faWQiOjk5LCJmaWxlX2lkIjoxNX0.ZR4KLQ.dTYXsW2oM37MpnqI_DozkxOW6p8

---
## Solución 

Una ves descargado el archivo la imagen lo siguiente que tenemos que hacer es verificar que nuestros paquetes estén actualizados  con el siguiente comando 

``` bash
┌──(kali㉿kali)-[~]
└─$ sudo apt update
```

Una ves que estén actualizados debemos descargar el siguiente paquete 
```
┌──(kali㉿kali)-[~]
└─$ sudo apt-get install foremost 
```


ya teniendo esto podemos continuar con la solución, lo primero es ejecutar el siguiente comando para analizar lo que contiene la imagen 

```
┌──(kali㉿kali)-[~/Downloads]
└─$ binwalk 2023Metared.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
30            0x1E            TIFF image data, little-endian offset of first image directory: 8
534           0x216           JPEG image data, JFIF standard 1.01
484909        0x7662D         PDF document, version: "1.6"

```

como podemos ver el archivo de imagen contiene un documento PDF 
por lo que ahora toca sacar los archivos de la imagen para ello usamos el siguiente comando

```
┌──(kali㉿kali)-[~/Downloads]
└─$ foremost 2023Metared.jpg                      
Processing: 2023Metared.jpg
|*|

```

esto nos genera una carpeta llamada output a la cual debemos de acceder 
```
┌──(kali㉿kali)-[~/Downloads]
└─$ cd output 

┌──(kali㉿kali)-[~/Downloads/output]
└─$ ls
audit.txt  jpg  pdf

```

como podemos ver ya tenemos el archivo pdf por lo que ahora toca abrirlo, de preferencia en algún navegador que lo permita, unas ves abierto en el navegador pedirá una contraseña la cual es **UniversidadVeracruzana**

la forma de obtener esta contraseña es mediante el uso del siguiente comando el cual despliega mucha información pero la mas importante es la de las coordenadas 

```bash 
exiftool 2023Metared.jpg

# ExifTool Version Number         : 12.57
# File Name                       : 2023Metared.jpg
# File Permissions                : -rw-r--r--
# File Type                       : JPEG
# File Type Extension             : jpg
# GPS Latitude                    : 0 deg 0' 0.00"
# GPS Longitude                   : 0 deg 0' 0.00"
# GPS Altitude                    : 0 m
# Metadata Date                   : 2023:08:03T08:35:29:06:00
# Description                     : What's in geographic coordinates?
# Comment                         : 19.51968889010359, -96.91733510943115

```

teniendo las coordenadas solo es pegarlas en google maps para que nos mande a la ubicación la cual es la de la universidad veracruzana así que solo lo usamos de contraseña para el pdf 

una ves accedemos al pdf nos topamos con que este esta totalmente en blanco aparentemente, ahora toca inspeccionar la pagina para ver que es lo que se oculta 

![[Pasted image 20231004202157.png]]

como podemos ver solo queda juntar las partes de la llave

**Resultado Final**
```
flagMX{Always use two-step authentication (2FA)}
```

---
## Notas Adicionales 
Foremost es un programa de datos que ha sido desarrollado con el fin exclusivo de recuperar archivos eliminados en Linux. Una de sus grandes ventajas es que podemos usarlo sin problema alguno para recuperar archivos en diferentes formatos, lo cual es ideal gracias a su alcance. Al ser una utilidad de Linux, la encontramos en todos los repositorios actuales simplificando su instalación. Debes saber que Foremost ejecuta una búsqueda de tipo forense en el disco duro para recuperar rescatar al máximo los archivos disponibles.


Binwalk  es una herramienta rápida y fácil de usar para: analizar en busca de codigo malicioso, realizar ingeniería inversa y extraer imágenes de firmware. Binwalk hace un buen trabajo analizando posibles firmas de archivos y filtrando falsos positivos obvios, pero no es perfecto. Algunas firmas son más difíciles de validar que otras y binwalk siempre va a pecar de cauteloso, es decir, informara antes de un posible falso positivo para que pueda validarlo o invalidarlo de forma independiente, en lugar de no informar de un resultado cuestionablemente válido.


---
## Referencias 
https://www.solvetic.com/tutoriales/article/7900-como-usar-foremost-linux-y-recuperar-archivos-borrados/

https://blog.segu-info.com.ar/2018/01/binwalk-herramienta-de-analisis-de.html

