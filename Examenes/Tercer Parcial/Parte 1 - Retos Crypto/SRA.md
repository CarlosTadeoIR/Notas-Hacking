## Objetivo 

I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.

---
## Datos de acceso al nivel 

Connect to the program on our server: `nc saturn.picoctf.net 54523` Download the program: [chal.py](https://artifacts.picoctf.net/c/296/chal.py)

---
## Solución 
el archivo chal.py nos sirve para entender la lógica que se usara dentro del servidor por lo que si lo ejecutamos debería darnos valores aleatorios como los siguientes  

``` bash
anger = 76713013770034486156077562084703195972851415788394947104895681975223067493525
envy = 33631673938545730361223886897667419780778866889925704248165407112026713803265
vainglory?

```

analizando el código vemos que cuenta con la gran mayoría de los elementos para RSA pero solo se nos permite interactuar con 3, 2 de ellos que son `anger` que equivale al texto cifrado y `envy` que equivale a `d`. por otra parte el otro valor que podemos llegar a conocer es el de `sloth` ya que corresponde al exponente de la llave publica

cada que se ejecuta el código todos los valores a excepción de la llave publica `sloth` cambian y considerando que no se puede modificar el código fuente ya que al final se ejecutara otro en algún servidor el cual solo permitirá ingresar datos, nuestra mejor opción es crear un script que considere los cambios para las variables `anger` y `envy` 

el Script seria el siguiente
```python
from Crypto.Util.number import isPrime, long_to_bytes
from string import ascii_letters, digits
from itertools import combinations
from sympy import divisors
from math import log2

anger = int(input("anger = "))
envy = int(input("envy = "))
sloth = 65537

ds = divisors(envy * sloth - 1)
primes = [x + 1 for x in ds if isPrime(x + 1)]
correct_size_primes = [x for x in primes if log2(x) // 1 == 127]

valid_plaintexts = []
charset = ascii_letters + digits
for p, q in combinations(correct_size_primes, 2):
    try:
        s = long_to_bytes(pow(anger, envy, p * q)).decode("ascii")
        if all([c in charset for c in s]):
            valid_plaintexts.append(s)
    except Exception:
        continue

print(valid_plaintexts)
```

Teniendo nuestro script listo ahora debemos acceder al servidor 
```bash
nc saturn.picoctf.net 54523
anger = 25003837826821672303468731752327887413611289691187541696185106433509694617569
envy = 28819120976103112382536726978612515275651166107353333317344268144110448358793
vainglory?

```

con los valores que nos dan ahora tenemos que ejecutar nuestro script en Python el cual nos pedirá los valores para `anger` y `envy`

```python
python3 exe.py
anger = 25003837826821672303468731752327887413611289691187541696185106433509694617569
envy = 28819120976103112382536726978612515275651166107353333317344268144110448358793
['uR349NZBGE687Mp9']

```

después de procesar los datos nos dará la respuesta misma que tenemos que ingresar en el servidor 

```bash
nc saturn.picoctf.net 54523
anger = 25003837826821672303468731752327887413611289691187541696185106433509694617569
envy = 28819120976103112382536726978612515275651166107353333317344268144110448358793
vainglory?
> uR349NZBGE687Mp9
uR349NZBGE687Mp9
Conquered!
picoCTF{7h053_51n5_4r3_n0_m0r3_dd808298}

```

al validarse los resultados nos dará la contraseña

**Resultado Final**
```
picoCTF{7h053_51n5_4r3_n0_m0r3_dd808298}
```

---
## Notas Adicionales 
El script no siempre puede llegara a funcionar aparte que dependiendo de los datos hará que tarde mas o que tarde menos 

---
## Referencias 
[PicoCTF 2023 - SRA - stackotter](https://stackotter.dev/blog/picoctf-2023-sra-writeup)

