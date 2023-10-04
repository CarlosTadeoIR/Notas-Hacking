## Objetivo 

The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/problem/44573/

---
## Solución 

Primero se accede a la pagina https://jupiter.challenges.picoctf.org/problem/44573/

![[Pasted image 20231003215219.png]]

una ves dentro lo siguiente que se hace es poner un nombre de usuario que no sea joe y una contraseña aleatoria 
![[Pasted image 20231004001554.png]]

accedemos 

![[Pasted image 20231004001615.png]]

como podemos ver la llave no esta disponible esto se debe a que un parámetro de las cookies esta en falso, para solucionar esto se pude descargar una extensión  de edición  de cookies 

![[Pasted image 20231004002617.png]]

una ves instalado volvemos a la pagina, activamos la extensión y hacemos lo siguiente 
![[Pasted image 20231004002851.png]]

dentro del apartado admin cambiamos el valor False por True y guardamos los cambios 
![[Pasted image 20231004003009.png]]

al final solo refrescamos la pagina y aparece la contraseña 

![[Pasted image 20231004003050.png]]

**Resultado Final**
```
picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}
```


---
## Notas Adicionales 

Use Microsoft Edge desde el mismo Windows ya que la maquina virtual me va un poco mal, eso hasta que le ponga mas RAM 

---
## Referencias 
[HTTP | MDN (mozilla.org)](https://developer.mozilla.org/en-US/docs/Web/HTTP)
[HTTP headers - HTTP | MDN (mozilla.org)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
[HTTP cookie - Wikiwand](https://www.wikiwand.com/en/HTTP_cookie)
[Cookie-Editor - Microsoft Edge Addons](https://microsoftedge.microsoft.com/addons/detail/cookieeditor/neaplmfkghagebokkhpjpoebhdledlfi)

