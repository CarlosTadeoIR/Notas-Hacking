## Objetivo 

Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt

---
## Solución 
si analizamos el archivo descargado veremos que es un código pequeño en ensamblador 
``` bash
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
```

Siguiendo las instrucciones del código:
1.  A la dirección de memoria `[rbp-0xc]` se le asigna el valor `0x9fe1a` y a la dirección de memoria `[rbp-0x8]`  se le asigna el valor `0x4`. 
2. Después al registro `eax` se le asigna el valor de la memoria de `[rbp-0xc]` para luego ser multiplicado por el valor de memoria de `[rbp-0x8]`, esto según la indicación `imul`.
3. Por ultimo al resultado se le suma `0x1f5` lo que terminara de darnos la bandera 

**Operación**
```python
>>> int((0x9fe1a*0x4)+0x1f5)
2619997
```

**Resultado Final**
```
picoCTF{2619997}
```

---
## Notas Adicionales 


---
## Referencias 