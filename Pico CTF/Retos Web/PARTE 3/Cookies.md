## Objetivo 

Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:64944/](http://mercury.picoctf.net:64944/)

---
## Datos de acceso al nivel 

[Cookies (picoctf.net)](http://mercury.picoctf.net:64944/)

---
## Solución 

lo primero es acceder a la pagina [Cookies (picoctf.net)](http://mercury.picoctf.net:64944/)  
![[Pasted image 20231010002756.png]]

después de eso nos pide que ingresemos el nombre de algún tipo de galleta pero podemos omitir eso haciendo uso de la herramienta [Cookie-Editor - Microsoft Edge Addons](https://microsoftedge.microsoft.com/addons/detail/cookieeditor/neaplmfkghagebokkhpjpoebhdledlfi) donde tendremos que cambiar el valor del campo Name 

![[Pasted image 20231010002951.png]]

en este caso el valor se encuentra en -1 pero si lo cambiamos a 1 por ejemplo, guardamos y refrescamos la pagina aparece lo siguiente 

![[Pasted image 20231010003116.png]]

bien ahora tenemos 2 opciones, la primera es repetir este proceso una y otra ves hasta llegar a la llave 

![[Pasted image 20231010003213.png]]

![[Pasted image 20231010003236.png]]


o bien podemos utilizar el siguiente comando en alguna terminal linux, el cual automatizara el proceso y solo mostrara la contraseña

``` bash
for i in {1..20}; do curl -s http://mercury.picoctf.net:64944/check -H "Cookie: name=$i"; done | grep pico

# <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}</code></p>
```

**Resultado Final**
```
picoCTF{3v3ry1_l0v3s_c00k135_cc9110ba}
```

---
## Notas Adicionales 

Me dio hambre de solo leer los tipos de galletas (Cookies )

---
## Referencias 