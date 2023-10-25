## Objetivo 

There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png

---
## Solución 

una ves que descargamos la imagen podemos acceder al siguiente sitio https://stylesuxx.github.io/steganography/ para encontrar el mensaje, para ello debemos colocarnos en la parte de decode y seleccionar el archivo  

![[Pasted image 20231014003256.png]]


otra forma de hacer esto mediante la terminal es descargar el paquete `zsteg ` para ello se usa el siguiente comando 

``` bash
sudo gem install zsteg 
```

**Después se hace lo siguiente**

``` bash
zsteg -a buildings.png | grep pico
# b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```

**Resultado Final**
```
picoCTF{h1d1ng_1n_th3_b1t5}
```

---
## Notas Adicionales 

---
## Referencias 
[What is Steganography? A Complete Guide with Types & Examples (simplilearn.com)](https://www.simplilearn.com/what-is-steganography-article)

https://stylesuxx.github.io/steganography/

