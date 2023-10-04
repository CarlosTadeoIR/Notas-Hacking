## Objetivo 

This website can be rendered only by **picobrowser**, go and catch the flag!

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/problem/28921/

---
## Solución 
lo primero es ingresar a la pagina https://jupiter.challenges.picoctf.org/problem/28921/

![[Pasted image 20231004011643.png]]

después oprimimos en obtener bandera   

![[Pasted image 20231004013315.png]]

como podemos ver tenemos un error por el navegador ya que se ocupa el navegador picobrowser 
el cual no existe entonces la forma mas eficaz de hacer esto es abrir la linea de comando y aplicar el siguiente comando 

```
curl -S https://jupiter.challenges.picoctf.org/problem/28921/flag -H "User-Agent:picobrowser " | grep pico
```

el cual nos permitirá conectarnos a la pagina como si entráramos desde el navegador picobrowser

![[Pasted image 20231004013614.png]]

**Resultado Final**
```
picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}
```

---
## Notas Adicionales 


---
## Referencias 
[User-Agent - HTTP | MDN (mozilla.org)](https://developer.mozilla.org/es/docs/Web/HTTP/Headers/User-Agent)
