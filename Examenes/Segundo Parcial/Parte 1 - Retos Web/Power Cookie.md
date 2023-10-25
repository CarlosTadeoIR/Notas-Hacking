## Objetivo 

Can you get the flag? Go to this [website](http://saturn.picoctf.net:57741/) and see what you can discover.

---
## Datos de acceso al nivel 

http://saturn.picoctf.net:57741/

---
## Solución 

para este reto se necesita una extensión que permita la edición de las cookies, en este caso use la extensión  https://addons.mozilla.org/es/firefox/addon/etc2/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search 

cuando tengamos la extensión lo primero que tenemos que hacer es ingresar a la pagina en ella aparecerá un mensaje y un botón con la inscripción `Continue as guest` en el cual tendremos que dar click para acceder 

una ves accedemos nos muestra el siguiente mensaje de error 
```
We apologize, but we have no guest services at the moment.
```

Para solucionar esto debemos hacer uso de nuestro editor de cookies, en la misma pagina donde nos sale el mensaje de error debemos abrir la extensión y buscar un valor que diga 0, este valor tendrá que ser cambiado a 1 

![[Pasted image 20231021023017.png]]

Después de haber realizado el cambio se tiene que guardar dicho cambio y refrescar la pagina, al hacer esto la bandera aparecerá 

**Resultado Final**
```
picoCTF{gr4d3_A_c00k13_5d2505be}
```

---
## Notas Adicionales 

---
## Referencias 
https://addons.mozilla.org/es/firefox/addon/etc2/?utm_source=addons.mozilla.org&utm_medium=referral&utm_content=search
