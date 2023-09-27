## Objetivo 

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip)

---
## Datos de acceso al nivel 

Se tiene que descargar el siguiente archivo 
https://mercury.picoctf.net/static/a350754a299cb58988d6d47aed5be3ba/Addadshashanammu.zip

---
## Solución 

dentro de la ruta donde tenemos el `.zip` se hace lo siguiente 

``` bash
unzip Addadshashanammu.zip 
# Archive:  Addadshashanammu.zip
#    creating: Addadshashanammu/
#    creating: Addadshashanammu/Almurbalarammi/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
#    creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
#   inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  

cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onni siralis/Ularradallaku 
## despues usamos el siguiente comando 
./fang-of-haynekhtnamet

# *ZAP!* c
  
```

**resultado Final**
```
picoCTF{l3v3l_up!_t4k3_4_r35t!_a00cae70}
```

---
## Notas Adicionales 

Este Problema se enfoca en dar o presionar muchas veces la tecla `TAB` para llegar al final del directorio y así poder ver que se oculta hasta el final 

---
## Referencias 