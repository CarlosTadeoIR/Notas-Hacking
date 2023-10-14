## Objetivo 

Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
---
## Solución 

después de descargar la imagen solo tenemos que ejecutar el siguiente comando en la terminal Linux  

``` bash
exiftool pico_img.png | grep pico
# File Name                       : pico_img.png
# Artist                          : picoCTF{s0_m3ta_d8944929}         

```

**Resultado Final**
```
picoCTF{s0_m3ta_d8944929}
```

---
## Notas Adicionales 

ExifTool es un programa gratuito y de código abierto para leer, escribir y manipular metadatos de imagen, audio, vídeo y PDF. Es independiente de la plataforma y está disponible como biblioteca Perl (Image::ExifTool) y como aplicación de línea de comandos.

---
## Referencias 
[ExifTool - Wikiwand](https://www.wikiwand.com/en/ExifTool)
