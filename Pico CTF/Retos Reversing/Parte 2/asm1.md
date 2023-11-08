## Objetivo 

What does asm1(0x8be) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S

mi dato de acceso 
```
0x8be
```

---
## Solución 

cuando descarguemos el archivo y lo analicemos para ver su contenido veremos que tiene una serie de instrucciones para el lenguaje ensamblador 
``` bash
asm1:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	cmp    DWORD PTR [ebp+0x8],0x71c
	<+10>:	jg     0x512 <asm1+37>
	<+12>:	cmp    DWORD PTR [ebp+0x8],0x6cf
	<+19>:	jne    0x50a <asm1+29>
	<+21>:	mov    eax,DWORD PTR [ebp+0x8]
	<+24>:	add    eax,0x3
	<+27>:	jmp    0x529 <asm1+60>
	<+29>:	mov    eax,DWORD PTR [ebp+0x8]
	<+32>:	sub    eax,0x3
	<+35>:	jmp    0x529 <asm1+60>
	<+37>:	cmp    DWORD PTR [ebp+0x8],0x8be
	<+44>:	jne    0x523 <asm1+54>
	<+46>:	mov    eax,DWORD PTR [ebp+0x8]
	<+49>:	sub    eax,0x3
	<+52>:	jmp    0x529 <asm1+60>
	<+54>:	mov    eax,DWORD PTR [ebp+0x8]
	<+57>:	add    eax,0x3
	<+60>:	pop    ebp
	<+61>:	ret    

```

Estas instrucciones se encuentran divididas aun que no lo parezcan, esta seria su división y sus funciones  de lo que hacen 

```shell
---------------------------------Prologo_de_la_funcion---------------------------------
<+0>:	push   ebp   # esta parte se encarga de cargar nuestro valor a la pila en este caso nuestro valor es 0x8be
<+1>:	mov    ebp,esp
---------------------------------Prologo_de_la_funcion---------------------------------



---------------------------------comparacion_1---------------------------------------
<+3>:	cmp    DWORD PTR [ebp+0x8],0x71c # compara la direccion de memoria ebp+0x8 que en este caso es nuestro valor 0x8be con el valor 0x71c
<+10>:	jg     0x512 <asm1+37>  # jg nos dara el valor de comparacion, en este caso si nuestra direccion de memoria es mayor que 0x71c saltara hasta la linea 37
---------------------------------comparacion_1---------------------------------------



---------------------------------comparacion_2---------------------------------------
<+12>:	cmp    DWORD PTR [ebp+0x8],0x6cf  # compara la direccion de memoria ebp+0x8 que en este caso es nuestro valor 0x8be con el valor 0x6cf
<+19>:	jne    0x50a <asm1+29># jne nos dara el valor de comparacion, en este caso si nuestra direccion de memoria no es igual a 0x6cf saltara hasta la linea 29
<+21>:	mov    eax,DWORD PTR [ebp+0x8] #Mueve el contenido de la dirección de memoria ebp+0x8 al registro eax
<+24>:	add    eax,0x3 # suma 3 al valor contenido en el registro eax
<+27>:	jmp    0x529 <asm1+60> #redirige con un salto el flujo del programa a la dirección de memoria 0x529 que en este caso se encuentra en la linea 60
<+29>:	mov    eax,DWORD PTR [ebp+0x8] # mueve el contenido de la dirección de memooria ebp+0x8 al registro eax, sobrescribiendo el valor que se había sumado anteriormente.
<+32>:	sub    eax,0x3 #resta 3 al valor contenido en el registro eax
<+35>:	jmp    0x529 <asm1+60> # redirige con un salto el flujo del programa a la dirección de memoria 0x529 que en este caso se encuentra en la linea 60
---------------------------------comparacion_2---------------------------------------



---------------------------------comparacion_3---------------------------------------
<+37>:	cmp    DWORD PTR [ebp+0x8],0x8be # compara la direccion de memoria ebp+0x8 que en este caso es nuestro valor 0x8be con el valor 0x8be
<+44>:	jne    0x523 <asm1+54> # jne nos dara el valor de comparacion, en este caso si nuestra direccion de memoria no es igual a 0x8be saltara hasta la linea 54
<+46>:	mov    eax,DWORD PTR [ebp+0x8] # mueve el contenido de la dirección de memoria ebp+0x8 al registro eax
<+49>:	sub    eax,0x3 #resta 3 al valor contenido en el registro eax
<+52>:	jmp    0x529 <asm1+60> # redirige con un salto el flujo del programa a la dirección de memoria 0x529 que en este caso se encuentra en la linea 60
<+54>:	mov    eax,DWORD PTR [ebp+0x8] # mueve el contenido de la dirección de memoria ebp+0x8 al registro eax, sobrescribiendo el valor que se había restado en la línea 49.
<+57>:	add    eax,0x3 #Suma 3 al valor contenido en el registro eax. Esto aumenta el valor almacenado en eax en 3 unidades.
---------------------------------comparacion_3----------------------------------------




---------------------------------Epilogo_de_la_funcion---------------------------------
<+60>:	pop    ebp #retira el valor del registro de base ebp en este caso lo que estaria en eax
<+61>:	ret  #se utiliza para finalizar la ejecución de la función y volver al punto de retorno en la función que la llamó
---------------------------------Epilogo_de_la_funcion---------------------------------
```


ya Explicado lo anterior vamos a ver como se comportaría aplicando las instrucciones del programa sobre nuestro valor `0x8be


```java
1. Se guarda nuestro valor 0x8be.
2. Se compara nuestro valor 0x8be con 0x71c para ver si 0x8be es mayor.
3. Como nuestro valor 0x8be es mayor nos desplazamos a la linea 37.
4. Se compara nuestro valor 0x8be con 0x8be para ver si no es igual 
5. Como nuestro valor 0x8be es igual a 0x8be no se aplica el salto de linea y seguoimos con la linea 46
6. tomamos nuestro valor 0x8be y lo guardamos en el registro eax
7. a nuestro registro eax le restamos 3 unidades lo que nos dara 0x8bb como nuevo valor para eax 
8. saltamos a la linea 60
9. sacamos el valor de eax
```

realizado lo anterior tenemos que nuestra bandera es la que se encuentra en eax por lo que el resultado para nuestra bandera seria 

**Resultado Final**
```
0x8bb
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
|je | jump when equal
|jne|  jump when not equal
|jz| jump when last result was zero
|jg|  jump when greater than
|jge|  jump when greater than or equal to
|jl|  jump when less than
|jle|   jump when less than or equal to


---
## Referencias 
[Guide to x86 Assembly (virginia.edu)](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html)
