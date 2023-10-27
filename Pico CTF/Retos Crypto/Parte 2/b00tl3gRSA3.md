## Objetivo 

Why use p and q when I can use more? Connect with `nc jupiter.challenges.picoctf.org 3726`.

---
## Datos de acceso al nivel 

```bash
nc jupiter.challenges.picoctf.org 3726
```

---
## Solución 

cuando nos conectemos al servidor se nos darán los siguientes datos, estos datos son aleatorios pero el proceso es el mismo

``` bash
nc jupiter.challenges.picoctf.org 3726
c: 980490351013226276475864370614301811693952638285510029152651801588977736472079378256337779237230318880142044015486052947240929445444286008849423685853793286804883680587943251518523373653787107742297207813403600087746289797499009267243846938620146172000479757653708816823441445949906525574520644884565765346566740894557410581784886130812494693
n: 1453102352755737413791230516520290871167567070241277091833118148817233970588431181229073406283305486781435739564761883203051264972096431363886759999748708558732219147172276339208616354425519948619127374732940189760940986035399032003029384261646022739820907199113362528957048089488546320597843760642721072836322740794308750765744440194050255661
e: 65537

```

Antes de seguir con la solución en Python tenemos que verificar que tengamos la siguiente librería en nuestro sistema 

```python
pip install pycryptodome
```

para continuar con la solución recomiendo  crear un script en Python ya que será mas fácil su edición y ejecución 

en el script importaremos las librerías necesarias y guardaremos nuestras variables 
```python
from Crypto.Util.number import inverse, long_to_bytes

c=980490351013226276475864370614301811693952638285510029152651801588977736472079378256337779237230318880142044015486052947240929445444286008849423685853793286804883680587943251518523373653787107742297207813403600087746289797499009267243846938620146172000479757653708816823441445949906525574520644884565765346566740894557410581784886130812494693
n=1453102352755737413791230516520290871167567070241277091833118148817233970588431181229073406283305486781435739564761883203051264972096431363886759999748708558732219147172276339208616354425519948619127374732940189760940986035399032003029384261646022739820907199113362528957048089488546320597843760642721072836322740794308750765744440194050255661
e=65537
```

el siguiente paso es factorizar `n` para ello recomiendo la pagina [Integer factorization calculator (alpertron.com.ar)](https://www.alpertron.com.ar/ECM.HTM) la cual nos ayudara en este proceso 

cuando factoricemos nos debería de dar el siguiente resultado 
```bash
1 453102 352755 737413 791230 516520 290871 167567 070241 277091 833118 148817 233970 588431 181229 073406 283305 486781 435739 564761 883203 051264 972096 431363 886759 999748 708558 732219 147172 276339 208616 354425 519948 619127 374732 940189 760940 986035 399032 003029 384261 646022 739820 907199 113362 528957 048089 488546 320597 843760 642721 072836 322740 794308 750765 744440 194050 255661 (343 digits) = 8899 562179 × 8945 490343 × 9217 541461 × 9258 898249 × 9590 337443 × 9633 628261 × 9737 090347 × 9751 350299 × 9781 739743 × 9856 871863 × 9970 660613 × 10092 762289 × 10170 451829 × 10170 731573 × 10321 293313 × 10831 351463 × 11022 133547 × 11112 317747 × 11199 652661 × 11589 897323 × 12577 890319 × 12705 788461 × 12870 647651 × 12936 519503 × 13474 341019 × 13983 928297 × 14255 432117 × 14342 504543 × 14483 740301 × 14989 271131 × 15213 486859 × 15573 040229 × 15983 189303 × 16217 435287
```

ya que tenemos esto debemos remplazar todas las  × por x  y crear la siguiente variable en nuestro script 

```python
a="resultado de factoizar ".split("=")[1].replace(" ", "").split("x")
```

en mi caso esta seria la variable completa 
```python
a="1 453102 352755 737413 791230 516520 290871 167567 070241 277091 833118 148817 233970 588431 181229 073406 283305 486781 435739 564761 883203 051264 972096 431363 886759 999748 708558 732219 147172 276339 208616 354425 519948 619127 374732 940189 760940 986035 399032 003029 384261 646022 739820 907199 113362 528957 048089 488546 320597 843760 642721 072836 322740 794308 750765 744440 194050 255661 (343 digits) = 8899 562179 x 8945 490343 x 9217 541461 x 9258 898249 x 9590 337443 x 9633 628261 x 9737 090347 x 9751 350299 x 9781 739743 x 9856 871863 x 9970 660613 x 10092 762289 x 10170 451829 x 10170 731573 x 10321 293313 x 10831 351463 x 11022 133547 x 11112 317747 x 11199 652661 x 11589 897323 x 12577 890319 x 12705 788461 x 12870 647651 x 12936 519503 x 13474 341019 x 13983 928297 x 14255 432117 x 14342 504543 x 14483 740301 x 14989 271131 x 15213 486859 x 15573 040229 x 15983 189303 x 16217 435287".split("=")[1].replace(" ", "").split("x")
```

después de esto, en nuestro script hacemos lo siguiente
```python
# 1
factors = []

for i in a:
	factors.append(int(i))
# 2

phi = 1;
for i in factors:
	phi *= (i-1)
	
# 3
d = inverse(e, phi)
# 4
print (long_to_bytes(pow(c,d,n)).decode())

```

1. Los factores primos se almacenan en la variable factors 
2. Después se calcula el totient con `phi` el cual esta establecido en 1 para después  recorrer todos los factores primos en la lista factors, y para cada uno de ellos, se multiplica `phi` por (i-1). Esto es parte del cálculo de la función totient, que se utiliza en RSA.
3. Después de esto calculamos la clave privada `d` 
4. Finalmente, se descifra el mensaje cifrado `c` utilizando la clave privada `d` y el módulo `n`
   eso en la formula de `pow(c,d,n)` para después convertir el resultado en bytes con `long_to_bytes` y por ultimo utilizando `.decode()` para convertir los bytes en una cadena de texto legible 

**El script completo en mi caso seria el siguiente**

```python
from Crypto.Util.number import inverse, long_to_bytes

c=980490351013226276475864370614301811693952638285510029152651801588977736472079378256337779237230318880142044015486052947240929445444286008849423685853793286804883680587943251518523373653787107742297207813403600087746289797499009267243846938620146172000479757653708816823441445949906525574520644884565765346566740894557410581784886130812494693
n=1453102352755737413791230516520290871167567070241277091833118148817233970588431181229073406283305486781435739564761883203051264972096431363886759999748708558732219147172276339208616354425519948619127374732940189760940986035399032003029384261646022739820907199113362528957048089488546320597843760642721072836322740794308750765744440194050255661
e=65537

a="1 453102 352755 737413 791230 516520 290871 167567 070241 277091 833118 148817 233970 588431 181229 073406 283305 486781 435739 564761 883203 051264 972096 431363 886759 999748 708558 732219 147172 276339 208616 354425 519948 619127 374732 940189 760940 986035 399032 003029 384261 646022 739820 907199 113362 528957 048089 488546 320597 843760 642721 072836 322740 794308 750765 744440 194050 255661 (343 digits) = 8899 562179 x 8945 490343 x 9217 541461 x 9258 898249 x 9590 337443 x 9633 628261 x 9737 090347 x 9751 350299 x 9781 739743 x 9856 871863 x 9970 660613 x 10092 762289 x 10170 451829 x 10170 731573 x 10321 293313 x 10831 351463 x 11022 133547 x 11112 317747 x 11199 652661 x 11589 897323 x 12577 890319 x 12705 788461 x 12870 647651 x 12936 519503 x 13474 341019 x 13983 928297 x 14255 432117 x 14342 504543 x 14483 740301 x 14989 271131 x 15213 486859 x 15573 040229 x 15983 189303 x 16217 435287".split("=")[1].replace(" ", "").split("x")

factors = []

for i in a:
	factors.append(int(i))
	
phi = 1;
for i in factors:
	phi *= (i-1)
	
d = inverse(e, phi)

print (long_to_bytes(pow(c,d,n)).decode())
```

ahora solo tenemos que guardar y ejecutar 
```bash
python3 exe.py 
# picoCTF{too_many_fact0rs_8606199}

```

**Resultado Final**
```
picoCTF{too_many_fact0rs_8606199}
```

---
## Notas Adicionales 

---
## Referencias 
https://www.alpertron.com.ar/ECM.HTM