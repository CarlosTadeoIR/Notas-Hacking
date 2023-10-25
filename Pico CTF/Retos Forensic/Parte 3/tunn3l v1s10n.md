## Objetivo 

We found this [file](https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n). Recover the flag.

---
## Datos de acceso al nivel 

https://mercury.picoctf.net/static/21c07c9dd20cd9f2459a0ae75d99af6e/tunn3l_v1s10n

---
## Solución 
una ves descargado el archivo lo primero que tenemos que hacer es analizar que tipo de archivo para ver que método es factible de usar 

``` bash
file tunn3l_v1s10n 
#tunn3l_v1s10n: data
```

esto realmente no nos dice nada entonces con ayuda del siguiente comando podemos ver su información 

```bash
xxd tunn3l_v1s10n | head

00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333 2a26 382c 2836 2b27 392d 2b2f  0'#3*&8,(6+'9-+/
00000070: 2623 1d12 0e23 1711 2916 0e55 3d31 9776  &#...#..)..U=1.v
00000080: 668b 6652 996d 569e 7058 9e6f 549c 6f54  f.fR.mV.pX.oT.oT
00000090: ab7e 63ba 8c6d bd8a 69c8 9771 c193 71c1  .~c..m..i..q..q.

```

ya sabemos que el archivo es un BM pero tiene sus detalles por lo que tocara modificarlo para ello usaremos `hexeditor`  y solo modificaremos la primera fila 

```shell
hexeditor tunn3l_v1s10n 

#Antes del cambio 
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........


#Despues del cambio 
00000000: 424d 8e26 2c00 0000 0000 2800 0000 2800  BM.&,.....(...(.


```

una ves guardamos los cambios ya se puede abrir la imagen pero aun no es visible la contraseña por lo que tenemos que cambiar algunos otros valores, esto de la misma forma, con ayuda de `hexeditor` 

```bash
hexeditor tunn3l_v1s10n

# antes del cambio
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........

# despues del cambio 
00000010: 0000 6e04 0000 4004 0000 0100 1800 0000  ..n...@.........

```

lo anterior fue para aumentar el tamaño de la imagen, con esto la contraseña ya es totalmente visible por lo que ahora solo queda abrir la imagen 

```bash
open tunn3l_v1s10n 
```


**Resultado Final**
```
picoCTF{qu1t3_a_v13w_2020}
```

---
## Notas Adicionales 

---
## Referencias 
[BMP file format - Wikiwand](https://www.wikiwand.com/en/BMP_file_format)
