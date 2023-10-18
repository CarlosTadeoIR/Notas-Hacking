## Objetivo 

We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap

---
## Solución 

una ves descargado el archivo el cual es una paquete de datos lo analizaremos con el programa Wireshark que viene en Kali con esto podemos ver que la flag se encuentra repartida en todos los paquetes UDP con destino al puerto 22 por lo que ahora usaremos la ayuda de Python y la librería scapy, para ello verificamos su instalación 

``` bash
python3 -m pip install scapy  
```

una ves verificamos esto debemos hacer uso del siguiente script que no ayudara a sacar la flag de los paquetes los cuales se encuentran ocultos en l columna de info en la aplicación 

```python 
from scapy.all import * 

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
	if UDP in p and p[UDP].dport == 22:
		if p[UDP].sport > 5000:
			flag += chr(p[UDP].sport-5000)
			
print(flag)
```


una ves tengamos nuestro script listo solo es cuestión de ejecutarlo 

```shell
python3 exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```

**Resultado Final**
```
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```

---
## Notas Adicionales 

---
## Referencias 
[Scapy](https://scapy.net/)
