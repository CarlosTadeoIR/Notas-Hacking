## Objetivo 

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

---
## Datos de acceso al nivel 

``` bash
nc jupiter.challenges.picoctf.org 29956
```

---
## Solución 

``` bash
# antes que nada prepararse con una pagina para convertir los datos 
# el orden es binario, octal y hexa 
nc jupiter.challenges.picoctf.org 29956
# Let us see how data is stored
# Please give the 01101100 01101001 01100111 01101000 01110100 as a word.
# ...
# you have 45 seconds.....

# Input:
light
# Please give me the  160 151 145 as a word.
# Input:
pie
# Please give me the 70656172 as a word.
# Input:
pear
# You've beaten the challenge
# Flag: picoCTF{learning_about_converting_values_b375bb16}
```

**Resultado Final**
```
picoCTF{learning_about_converting_values_b375bb16}
```


---
## Notas Adicionales 

¿Era necesario que fuesen 45 segundos para esto? 

---
## Referencias 

https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDExMDAgMDExMDEwMDEgMDExMDAxMTEgMDExMDEwMDAgMDExMTAxMDA

https://gchq.github.io/CyberChef/#recipe=From_Octal('Space')&input=MTYwIDE1MSAxNDU

https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=NzA2NTYxNzI

