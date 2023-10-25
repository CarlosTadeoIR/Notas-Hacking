## Objetivo 

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static)? This [BASH script](https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh) might help!

---
## Datos de acceso al nivel 

Se tienen que descargar lo siguientes archivos pero en este caso para dar soluciona solo usaremos uno, `static`

static
https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/static

script (ltdis.sh)
https://mercury.picoctf.net/static/e9dd71b5d11023873b8abe99cdb45551/ltdis.sh

---
## Solución

dentro de la ruta donde tenemos los archivos descargados 

``` bash
chmod +x static
Strings static

strings static | grep pico
picoCTF{d15a5m_t34s3r_ae0b3ef2}
```

**resultado Final**
```
picoCTF{d15a5m_t34s3r_ae0b3ef2}
```

---
## Notas Adicionales 

para esta solución se omitió el uso del segundo archivo ya que no es necesario para la solución, en su lugar se opto por el uso de  `grep` visto en los retos bandit  

---
## Referencias 