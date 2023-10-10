## Objetivo 

Can you break into this super secure portal?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/problem/60786/

---
## Solución 
la forma mas rápida de solucionar esto es accediendo primero a la pagina https://jupiter.challenges.picoctf.org/problem/60786/ 

![[Pasted image 20231004010123.png]]

después de ingresar debemos ver su código fuente al cual podemos acceder con Ctrl + U 

![[Pasted image 20231004010234.png]]

como podemos notar esa cosa es ilegible ya que esta ofuscada, para ello copeamos la parte del codigo y la pegamos en la siguiente pagina  [JS NICE: Statistical renaming, Type inference and Deobfuscation](http://jsnice.org/)

![[Pasted image 20231004010354.png]]

![[Pasted image 20231004010426.png]]

posteriormente solo debemos procesar los datos 

![[Pasted image 20231004010520.png]]

aun así el código esta hecho un caos por lo que la forma mas sencilla de llegar a la llave es copiar el arreglo principal 

```
var _0x5a46 = ["f49bf}", "_again_e", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
```

y  pegarlo en la consola que podemos desplegar en la pagina principal con la función de inspeccionar 

![[Pasted image 20231004011012.png]]

![[Pasted image 20231004010959.png]]


después de esto lo único que queda es armar la llave manualmente guiándonos con el formato de las otras llaves 

![[Pasted image 20231004011206.png]]

**Resultado Final**
```
picoCTF{not_this_again_ef49bf}
```

---
## Notas Adicionales 

---
## Referencias 
[What is obfuscation and how does it work? (techtarget.com)](https://www.techtarget.com/searchsecurity/definition/obfuscation)
[JS NICE: Statistical renaming, Type inference and Deobfuscation](http://jsnice.org/)

