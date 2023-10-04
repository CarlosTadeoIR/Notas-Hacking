## Objetivo 

Can you break into this super secure portal?

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/problem/17682/

---
## Solución 

Primero se accede a la pagina https://jupiter.challenges.picoctf.org/problem/17682/

![[Pasted image 20231003213354.png]]

Después de entrar nuevamente aplicamos el comando Ctrl + u lo que nos llevara al código fuente de la pagina 

![[Pasted image 20231003213823.png]]

Como podemos ver, existe una contraseña ya valida para la pagina anterior, lo malo es que viene desordenada en ciclos if por lo que toca ordenarlas manualmente, cosa que no es para nada difcil ya que solo se tiene que seguir la siguiente secuencia en orden 

0, split            == 'pico'
split, split2     == 'CTF{'
split2, split3   == 'no_c'
split3, split4   == 'lien'
split4, split5   == 'ts_p'
split5, split6   == 'lz_b'
split6, split7   == '706c'
split7, split8   == '5}'

ordenando las partes podemos armar la llave 

**Resultado Final**
```
picoCTF{no_clients_plz_b706c5}
```

---
## Notas Adicionales 

---
## Referencias 