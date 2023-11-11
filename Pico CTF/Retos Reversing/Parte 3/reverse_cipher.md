## Objetivo 

We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev
https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this

---
## Solución 

antes de empezar debemos verificar que tengamos la herramienta `ghidra` instalada en nuestro sistema Linux
```bash
sudo apt install ghidra 
```

Esta herramienta nos permitirá analizar la lógica que se uso para encriptar la bandera ya que si analizamos el documento  `rev_this` encontraremos lo siguiente 

``` bash
picoCTF{w1{1wq8/7376j.:}
```

una ves tengamos instalada la herramienta `ghidra` tendemos que abrir un nuevo proyecto y cargar el archivo `rev` buscando el apartado de la clase `mine`

Analizando el método de cifrado podemos crear un script de Python que descifre la bandera , dicho script seria el siguiente

```python
cifrado = open ('rev_this','r').read()
# print(cifrado)

flag = ''

for i in range(8,len(cifrado) -1):
	if i & 1 == 0:
		flag += chr( ord(cifrado[i]) - 5 )
	else:
		flag += chr( ord(cifrado[i]) + 2 )
print(f"picoCTF{{{flag}}}")
```

Ahora solo quedaría ejecutarlo y podremos ver la bandera 

```bash
python3 exe.py
# picoCTF{r3v3rs312528e05}

```

**Resultado Final**
```
picoCTF{r3v3rs312528e05}
```

---
## Notas Adicionales 


---
## Referencias 