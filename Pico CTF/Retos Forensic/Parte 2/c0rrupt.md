## Objetivo 

We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery

---
## Solución 

una ves descargamos el archivo verificamos que tipo es 
```
file mystery                 
mystery: data
```

realmente esto no nos dice mucho por lo que tendremos que hacer uso de la herramienta integrada `hexeditor`  y de la herramienta `xxd`

primero usamos `xxd` para ver el encabezado 

```bash
xxd mystery | head

00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
```

como podemos ver existen algunas cosas que no cuadran por lo que ahora toca usar `hexeditor` y cambiar los siguientes valores por los siguientes en la primera fila 

```bash 
hexeditor mystery 
00000000: 89 50 4E 47 0D 0A 1A 0A 00 00 00 0D 49 48 44 52     .PNG........IHDR
```

Una ves guardemos los cambios realizados, ya se puede identificar que el archivo es un png pero todavía faltan cambios por hacer, para ello con ayuda de la herramienta  `pngcheck` que se instala de la siguiente forma 

```
sudo apt-get install pngcheck
```

podremos consultar cuales son los detalles que tiene nuestro archivo 

```bash
pngcheck -v mystery

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
     rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery

```

una ves ubicamos los errores del archivo debemos volver a editar con `hexeditor` para ello solo se cambiaran las siguientes líneas por las siguientes

Antes 
```
00000040: 00 09 70 48 59 73 AA 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
00000050: 52 24 F0 AA AA FF A5 AB 44 45 54 78 5E EC BD 3F  R$......DETx^..?
```

Después
```
hexeditor mystery 
00000040: 00 09 70 48 59 73 00 00 16 25 00 00 16 25 01 49  ..pHYs...%...%.I
00000050: 52 24 F0 00 00 FF A5 49 44 41 54 78 5E EC BD 3F  R$.....IDATx^..?

```


después de guardar los cambios así es como debería de verse el encabezado usado el comando `xxd`

```bash 
xxd mystery | head

00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 0000 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f000 00ff a549 4441 5478 5eec bd3f  R$.....IDATx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..

```


si comprobamos el archivo con el comando `pngcheck` nos dirá lo siguiente

```bash 
pngcheck -v mystery
File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).

```

ya para finalizar solo quedaría abrir la imagen ya que la flag esta en su interior 

**Resultado Final**
```
picoCTF{c0rrupt10n_1847995}
```

---
## Notas Adicionales 


---
## Referencias 
[List of file signatures - Wikiwand](https://www.wikiwand.com/en/List_of_file_signatures)
