## Objetivo 

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 49039`, but it doesn't speak English...

---
## Datos de acceso al nivel 

se tiene que usar el comando `nc mercury.picoctf.net 49039`

---
## Solución 

``` bash
nc mercury.picoctf.net 49039
# 112 
# 105 
# 99 
# 111 
# 67 
# 84 
# 70 
# 123 
# 103 
# 48 
# 48 
# 100 
# 95 
# 107 
# 49 
# 116 
# 116 
# 121 
# 33 
# 95 
# 110 
# 49 
# 99 
# 51 
# 95 
# 107 
# 49 
# 116 
# 116 
# 121 
# 33 
# 95 
# 51 
# 100 
# 56 
# 52 
# 101 
# 100 
# 99 
# 56 
# 125 
# 10 
```

**Después**

por facilidad usamos la pagina https://gchq.github.io/CyberChef/ para desencriptar el mensaje que se encuentra codificado en ASCII con el parámetro de from decimal 

**Resultado Final**

``` bash
picoCTF{g00d_k1tty!_n1c3_k1tty!_3d84edc8}
```

---
## Notas Adicionales 
existen mas formas de llegar a la llave, en este caso se opto por la mas simple de todas

pagina con la solucion
https://gchq.github.io/CyberChef/#recipe=From_Decimal('Space',false)&input=MTEyIAoxMDUgCjk5IAoxMTEgCjY3IAo4NCAKNzAgCjEyMyAKMTAzIAo0OCAKNDggCjEwMCAKOTUgCjEwNyAKNDkgCjExNiAKMTE2IAoxMjEgCjMzIAo5NSAKMTEwIAo0OSAKOTkgCjUxIAo5NSAKMTA3IAo0OSAKMTE2IAoxMTYgCjEyMSAKMzMgCjk1IAo1MSAKMTAwIAo1NiAKNTIgCjEwMSAKMTAwIAo5OSAKNTYgCjEyNSAKMTAg

---
## Referencias 
https://gchq.github.io/CyberChef/

