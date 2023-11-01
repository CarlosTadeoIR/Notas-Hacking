## Objetivo 

We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/129/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/129/message.txt

---
## Solución 

Por comodidad la mejor forma de dar solución a este problema es crear un script de Python el cual tendrá lo siguiente  

``` bash
datos = open('message.txt').read().split()

print (datos)

flag = ''   # en esta parte se guarda la bandera

for n in datos:
     c = int(n) % 37
     if c>=0 and c <=25:  # en este rango es una letra 
        s = chr(c+65)
     elif c >= 25 and c <= 35: # en este rago es un valor decimal
        s = chr(c+22)
     else:                    # es un '_'
        s = '_'
        
     flag += s        # se guarda el valor el la variable flag 
print(f"picoCTF{{{flag}}}")  #se ponen 3 "{" y 3 "}" para que se complete el formato de salida 
```

cuando tengamos nuestro script lo siguiente es ejecutarlo 
```bash
python3 exp.py
# ['350', '63', '353', '198', '114', '369', '346', '184', '202', '322', '94', '235', '114', '110', '185', '188', '225', '212', '366', '374', '261', '213']

#picoCTF{R0UND_N_R0UND_ADD17EC2}

```

**Resultado Final**
```
picoCTF{R0UND_N_R0UND_ADD17EC2}
```

---
## Notas Adicionales 

---
## Referencias 