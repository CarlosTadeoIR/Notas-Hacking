## Objetivo 

Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/195/network-dump.flag.pcap)
---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/195/network-dump.flag.pcap

---
## Solución 

cuando descarguemos el archivo tenemos que abrirlo con la herramienta Wireshark.

cuando tengamos abierto el paquete de datos basta con dar click derecho sobre alguno que tenga el protocolo TCP  después a la opción follow y por ultimo a la opción TCP Stream

cuando estemos dentro la bandera aparecerá en el Stream numero 0, el único problema es que tendremos es que la bandera esta separada por espacios por lo que tendremos que borrarlos manualmente 

**Resultado Final**
```
picoCTF{p4ck37_5h4rk_b9d53765}
```

---
## Notas Adicionales 

otra forma de obtener la bandera de forma mas sencilla y sin la necesidad de abrir Wireshark es mediante el uso del siguiente comando 

```bash
strings  network-dump.flag.pcap | tr -d ' '| grep "pico" 
```

---
## Referencias 