## Objetivo 

Kishor Balan tipped us off that the following code may need inspection:

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/problem/9670/

---
## Solución 

La solución a este problema es fácil 
primero se accede a la pagina https://jupiter.challenges.picoctf.org/problem/9670/ 

![[Pasted image 20231003232349.png]]

después se tiene que oprimir la tecla Ctrl + U lo cual nos llevara a ver el código fuente de la pagina 

![[Pasted image 20231003212839.png]]

Dentro de la pagina podemos encontrar al final una parte de la llave, las otras 2 partes se encuentran en los archivos https://jupiter.challenges.picoctf.org/problem/9670/mycss.css y https://jupiter.challenges.picoctf.org/problem/9670/myjs.js por lo cual solo bastara con abrir los enlaces dentro de la pagina 

Primer enlace mycss.css
podemos encontrar la parte de la llave al final del archivo 
![[Pasted image 20231003213129.png]]

Segundo enlace myjs.js 
de igual forma podemos encontrar la ultima parte de la llave al final del archivo
![[Pasted image 20231003213225.png]]

**Resultado Final**
```
picoCTF{tru3_d3t3ct1ve_0r_ju5t_lucky?2e7b23e3}
```

---
## Notas Adicionales 

---
## Referencias 