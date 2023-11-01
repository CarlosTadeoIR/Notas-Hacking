## Objetivo 

In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values)

---
## Datos de acceso al nivel 

https://mercury.picoctf.net/static/bf5e2c8811afb4669f4a6850e097e8aa/values

---
## Solución 

cuando descarguemos el archivo veremos que contiene los siguientes datos 
```bash
cat values 
# Decrypt my super sick RSA:
# c: 421345306292040663864066688931456845278496274597031632020995583473619804626233684
# n: 631371953793368771804570727896887140714495090919073481680274581226742748040342637
# e: 65537

```

a continuación tomaremos el valor de n para factorizarlo, ya que ese al ser pequeño no resultara una tarea complicada, para ello usaremos la siguiente pagina [factordb.com](http://factordb.com/)

Cuando le pasemos el valor de n nos arrojara el siguiente resultado 

``` bash
= [1461849912200000206276283741896701133693]<40 [431899300006243611356963607089521499045809]<42>
```

Estos valores corresponden a `p` y a `q` por lo que ahora pasaremos a usar Python para poder procesar los datos 

antes de iniciar con Python tenemos que verificar que este instalada la siguiente librería 
```python
pip install pycryptodome
```

si ya tenemos esta librería lo siguiente es ejecutar Python para importar las siguientes librerías y registrar los datos que ya tenemos 

```python
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c =421345306292040663864066688931456845278496274597031632020995583473619804626233684
>>> e =65537
>>> p =1461849912200000206276283741896701133693
>>> q =431899300006243611356963607089521499045809
```

Después de registrar los datos vamos a hacer las siguientes operaciones 

```python
>>> n=p*q
>>> n
631371953793368771804570727896887140714495090919073481680274581226742748040342637
>>> tn = (p-1)*(q-1)
>>> tn
631371953793368771804570727896887140714061729769155038068711341335911329840163136
>>> d=inverse(e,tn)
>>> d
86820026055294556838164569629472617179839240561509150603097892917271661878321409
>>> m=pow(c,d,n)
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_55304594}'
```

**Resultado Final**
```
picoCTF{sma11_N_n0_g0od_55304594}
```

---
## Notas Adicionales 


---
## Referencias 
[factordb.com](http://factordb.com/)