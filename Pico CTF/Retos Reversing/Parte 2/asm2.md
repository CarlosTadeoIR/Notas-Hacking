## Objetivo 

What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S

mis datos de acceso 
```
0xb
0x2e
```


---
## Solución 

cuando descarguemos el archivo esto es lo que tendrá 

``` bash
asm2:
---------------------------------Prologo_de_la_funcion---------------------------------
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
---------------------------------Prologo_de_la_funcion---------------------------------

	<+3>:	sub    esp,0x10
	
	<+6>:	mov    eax,DWORD PTR [ebp+0xc]
	<+9>:	mov    DWORD PTR [ebp-0x4],eax
	<+12>:	mov    eax,DWORD PTR [ebp+0x8]
	<+15>:	mov    DWORD PTR [ebp-0x8],eax
	<+18>:	jmp    0x509 <asm2+28>

	<+20>:	add    DWORD PTR [ebp-0x4],0x1
	<+24>:	sub    DWORD PTR [ebp-0x8],0xffffff80
	
	<+28>:	cmp    DWORD PTR [ebp-0x8],0x63f3
	<+35>:	jle    0x501 <asm2+20>
	<+37>:	mov    eax,DWORD PTR [ebp-0x4]


---------------------------------Epilogo_de_la_funcion---------------------------------
	<+40>:	leave  
	<+41>:	ret
---------------------------------Epilogo_de_la_funcion---------------------------------
```

Para dar Solución a este problema lo ideal es hacer un script en Python para ello se tomara como base el código del archivo que descargamos   

```python 
'''
Stack:
[  local4 ]  <--- ebp-0x10
[  local3 ]  <--- ebp-0xc
[  local2 ]  <--- ebp-0x8
[  local1 ]  <--- ebp-0x4    esta es la extructira que se crea al seguir todos los pasos
[   ebp   ]
[   ret   ]  <--- ebp+0x4
[   arg1  ]  <--- ebp+0x8
[   arg2  ]  <--- ebp+0xc
'''
#los argumnetos que recibe asm2
def asm2(arg1, arg2):
#asm2:              aqui empieza el codigo ensamblador 
    #<+0>:  push   ebp
    #<+1>:  mov    ebp,esp
    #<+3>:  sub    esp,0x10

    #<+6>:  mov    eax,DWORD PTR [ebp+0xc]
    eax = arg2

    #<+9>:  mov    DWORD PTR [ebp-0x4],eax
    local1 = eax

    #<+12>: mov    eax,DWORD PTR [ebp+0x8]
    eax = arg1

    #<+15>: mov    DWORD PTR [ebp-0x8],eax
    local2 = eax

    #<+18>: jmp    0x509 <asm2+28>
    #<+20>: add    DWORD PTR [ebp-0x4],0x1
    #<+24>: sub    DWORD PTR [ebp-0x8],0xffffff80
    #<+28>: cmp    DWORD PTR [ebp-0x8],0x63f3
    #<+35>: jle    0x501 <asm2+20>
    while(local2 <= 0x63f3):
        local1 = (local1 + 1) & 0xffffffff              #Esto trunca el resultado a 32 bits. 32 bits.
        local2 = (local2 - 0xffffff80)  & 0xffffffff    #Esto trunca el resultado a 32 bits. 32 bits.           
    '''
    Es necesario truncar los restultados porque en python no tiene
    desbordamiento de búfer pero 0x86 puede tener por lo que tenemos que truncarlo
       '''

    #<+37>: mov    eax,DWORD PTR [ebp-0x4]
    #<+40>: leave
    #<+41>: ret
    return hex(local1)

print(asm2(0xb, 0x2e)) #aqui van los valores que nos da el reto

```

una ves que tengamos esto solo necesitamos correr el programa y nos dará la bandera 


**Resultado Final**
```
0xf6
```

---
## Notas Adicionales 


---
## Referencias 
[Guide to x86 Assembly (virginia.edu)](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html)