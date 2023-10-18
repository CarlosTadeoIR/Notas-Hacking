## Objetivo 

Decode this [message](https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav) from the moon.

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/fc1edf07742e98a480c6aff7d2546107/message.wav

---
## Solución 

Lo primero que tenemos que hacer después de descargar el archivo es ir hasta l carpeta `opt` y descargar el siguiente repositorio 

``` bash
cd /opt  
sudo  git clone https://github.com/colaclanth/sstv.git
```

una ves clonemos el repositorio debemos movernos de carpeta 
```bash 
ls
microsoft  sstv

cd sstv     
```

dentro de la carpeta usamos el siguiente comando
```bash
sudo python3 setup.py install
```

una ves finalice el proceso de instalación debemos ir a la carpeta donde tengamos el archivo descargado y aplicar el siguiente comando 

```bash 
sstv -d message.wav -o result.png
```

una ves finalice el proceso ya podemos abrir la imagen png ya que la bandera estará en su interior solo es cuestion de rotar la imagen para tener una mejor comprensión de lo que dice 

**Resultado Final**
```
picoCTF{beep_boop_im_in_space}
```

---
## Notas Adicionales 

---
## Referencias 
[colaclanth/sstv: SSTV Decoder (github.com)](https://github.com/colaclanth/sstv)
