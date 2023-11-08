## Objetivo 

What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S

```
0xba6c5a02
0xd101e3dd
0xbb86a173
```

---
## Solución 

cuando abramos el archivo veremos lo siguiente
 
``` bash
asm3:
	<+0>:	push   ebp
	<+1>:	mov    ebp,esp
	<+3>:	xor    eax,eax
	<+5>:	mov    ah,BYTE PTR [ebp+0xb]
	<+8>:	shl    ax,0x10
	<+12>:	sub    al,BYTE PTR [ebp+0xd]
	<+15>:	add    ah,BYTE PTR [ebp+0xc]
	<+18>:	xor    ax,WORD PTR [ebp+0x12]
	<+22>:	nop
	<+23>:	pop    ebp
	<+24>:	ret  
```

después de esto tenemos que ingresar a la siguiente pagina [Assembly x86 Emulator (carlosrafaelgn.com.br)](https://carlosrafaelgn.com.br/Asm86/) para procesar los datos, dentro de la pagina tenemos que pegar lo siguiente 

```
start:
	push 0xbb86a173
	push 0xd101e3dd
	push 0xba6c5a02
	call asm3

asm3:
	push   ebp
	mov    ebp,esp
	xor    eax,eax
	mov    ah,BYTE PTR [ebp+0xb]
	shl    ax,0x10
	sub    al,BYTE PTR [ebp+0xd]
	add    ah,BYTE PTR [ebp+0xc]
	xor    ax,WORD PTR [ebp+0x12]
	nop
	pop    ebp
	ret  
```

después de hacer esto tenemos que activar en el menú de arriba a la derecha los registros y después ejecutar el programa paso por paso, esto nos dará la bandera en el apartado de EAX solo es cuestión de quitar los 0 que estén de mas.

![[asm3_imagen.png]]

**Resultado Final**
```
0x669B
```

---
## Notas Adicionales 

---
## Referencias 