## Objetivo 

Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt

---
## Solución 
si analizamos el archivo descargado veremos que es un código pequeño en ensamblador 
``` bash
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
```

Siguiendo las instrucciones del código:
1. A la dirección de memoria `[rbp-0x4]` se le asigna el valor `0x9fe1a`
2. Se compara si lo que tiene la dirección de memoria  `[rbp-0x4]` es menor o igual a `0x2710`
3. Al ser falso continuamos con el proceso sin saltarnos a otra parte del código.
4. Se nos pide que al valor de memoria se le reste `0x65`
5. Haciendo las operaciones correspondientes obtendremos la bandera  

```python
>>> 0x9fe1a <= 0x2710
False
>>> int(0x9fe1a-0x65)
654773
```

**Resultado Final**
```
picoCTF{654773}
```

---
## Notas Adicionales 

---
## Referencias 