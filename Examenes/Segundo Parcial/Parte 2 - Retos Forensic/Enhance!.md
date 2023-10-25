## Objetivo 

Download this image file and find the flag.

- [Download image file](https://artifacts.picoctf.net/c/100/drawing.flag.svg)

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/100/drawing.flag.svg

---
## Solución 

para este reto se puede descargar la imagen y después abrirla con el navegador para ver su código fuente o bien copeando la ruta de descarga de la imagen y ejecutar el siguiente comando en la linea de comando 

``` bash
curl -s https://artifacts.picoctf.net/c/100/drawing.flag.svg      
```

sea cual sea el método usado al final del HTML veremos que la contraseña se encuentra partida en muchas partes como se ve a continuación


```html 
       id="text3723"><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08501"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3748">p </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.08942"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3754">i </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09383"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3756">c </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.09824"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3758">o </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10265"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3760">C </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.10706"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3762">T </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11147"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3764">F { 3 n h 4 n </tspan><tspan
         sodipodi:role="line"
         x="107.43014"
         y="132.11588"
         style="font-size:0.00352781px;line-height:1.25;fill:#ffffff;stroke-width:0.26458332;"
         id="tspan3752">c 3 d _ a a b 7 2 9 d d }</tspan></text>
  </g>
```

|**Parte De La Llave** | **Descripción** |
|:---------:|:-------------|
| 1 | >p <
| 2 | >i <
| 3 | >c <
| 4 | >o <
| 5 | >C <
| 6 | >T <
| 7 | >F { 3 n h 4 n <
| 8 | >c 3 d _ a a b 7 2 9 d d }<

por lo que uniendo todas las partes y quitando espacios en blanco quedaría

**Resultado Final**
```
picoCTF{3nh4nc3d_aab729dd}
```

---
## Notas Adicionales 

---
## Referencias 