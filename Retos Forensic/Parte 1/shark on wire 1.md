## Objetivo 

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap

uso de la herramienta Wireshark

---
## Solución 

lo primero que debemos hacer después de descargar el archivo es abrir la herramienta Wireshark en Kali Linux para posteriormente indicar que abra el archivo descargado 

después nos posicionamos sobre algún paquete con el protocolo UDP para dar click derecho>>Follow>>UDP Stream 

![[Pasted image 20231013235201.png]]

![[Pasted image 20231013235329.png]]

estado dentro de esa ventana tenemos que moveremos entre los diferentes Stream hasta poder localizar la bandera 

![[Pasted image 20231013235505.png]]

**Resultado Final**
```
picoCTF{StaT31355_636f6e6e}
```


---
## Notas Adicionales 

esto me trae recuerdos oscuros del concurso  

---
## Referencias 

[PCAP: Packet Capture, what it is & what you need to know (comparitech.com)](https://www.comparitech.com/net-admin/pcap-guide/)
