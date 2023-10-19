## Objetivo 

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c00c449c3b08daaccacca6f9d5c55d49/Forensics is fun.pptm)

---
## Datos de acceso al nivel 

https://mercury.picoctf.net/static/c00c449c3b08daaccacca6f9d5c55d49/Forensics

---
## Solución 

una ves descargamos el archivo pptm lo que tenemos que hacer es extraerlo con unzip  

``` bash
unzip Forensics\ is\ fun.pptm 

ls    
# '[Content_Types].xml'   docProps  'Forensics is fun.pptm'   ppt   _rels
```

lo que sigue es buscar el archivo con la contraseña, se recomienda el uso de visual studio code pero por este caso lo vamos a omitir

teniendo el archivo ya descomprimido se hace lo siguiente  
```bash
cd ppt/slideMasters        
ls
# hidden  _rels  slideMaster1.xml
cat hidden                 
# Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                            

cat hidden | tr -d ' ' | base64 -d

# flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input
```

**Resultado Final**
```
picoCTF{D1d_u_kn0w_ppts_r_z1p5}
```

---
## Notas Adicionales 
también se puede copiar el texto del archivo hidden y pegarlo en [CyberChef](https://gchq.github.io/CyberChef/) solo se especifica que es en base64 y dará la repuesta 


respuesta del CyberChef
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=WiBtIHggaCBaIHogbyBnIGMgRyBsIGogYiAwIE4gVSBSIG4gdCBFIE0gVyBSIGYgZCBWIDkgciBiIGogQiAzIFggMyBCIHcgZCBIIE4gZiBjIGwgOSA2IE0gWCBBIDEgZiBR

---
## Referencias 
https://www.reviversoft.com/es/file-extensions/pptm
