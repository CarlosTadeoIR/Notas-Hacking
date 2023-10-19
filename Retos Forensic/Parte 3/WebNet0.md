## Objetivo 

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap

https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key

---
## Solución 

una ves tengamos los archivos descargados debemos abrir la herramienta Wireshark, antes de abrir nuestro paquete de datos primero debemos ingresar la llave que nos permitirá ver lo archivos 

Edit>>preferencias>>protocolos >>TLS>>RSA keys list

![[Pasted image 20231018225736.png]]

después de decirle la ubicación del archivo de llave, debemos cargar nuestro paquete de datos y dar click derecho sobre algún protocolo TLSv1.2, darle a la opción de  follow y por ultimo a la de TLS Stream y aparecerá la llave 

![[Pasted image 20231018230313.png]]


**Resultado Final**
```
picoCTF{nongshim.shrimp.crackers}
```

---
## Notas Adicionales 

---
## Referencias 