## Objetivo 

While going through the deleted files of a coworker who was fired for selling information to a competitor recently, I came across an intriguing file. Although I can't decipher its content, I remember that he liked to learn Python in his spare time and once told me that he was interested in learning how to display binary data and compress information.

---
## Datos de acceso al nivel 

https://ctfd.anuies.mx/files/5909281e827600b5d26d3f538961df7a/An_intriguing_file.txt?token=eyJ1c2VyX2lkIjoyNDIsInRlYW1faWQiOjk5LCJmaWxlX2lkIjoyOX0.ZR3vUg.vB-dIVUQDltZ-k9LN6UvdXFQGi4


---
## Solución 

una ves descargado el archivo verificamos que es lo que tiene en su interior para ello podemos usar cat o abrir el archivo 

como podemos ver tiene la siguiente cadena 
``` bash
eJxLy0lM942o9k2syMwtzVUoTk0uLcosqVTILFaozC8tUijNS0ktKi5JzEvJzEtXyE9TKEpNzAEqqAUAgf8WPg==
```

la cual esta codificada en base64 y Zlib Inflate
por facilidad usaremos la herramienta https://gchq.github.io/CyberChef/  

una ves dentro de la herramienta y escoger los parámetros indicados nos dará este resultado 

**Resultado Final**
```
flagMX{Maximum security is your understanding of reality}
```

---
## Notas Adicionales 

---
## Referencias 
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)Zlib_Inflate(0,0,'Adaptive',false,false)&input=ZUp4THkwbE05NDJvOWsyc3lNd3R6VlVvVGswdUxjb3NxVlRJTEZhb3pDOHRVaWpOUzBrdEtpNUp6RXZKekV0WHlFOVRLRXBOekFFcXFBVUFnZjhXUGc9PQ

