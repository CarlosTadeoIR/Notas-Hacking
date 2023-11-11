## Objetivo 

Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/512/debugger0_a

---
## Solución 
Después de descargar el archivo le damos permisos de ejecución   
``` bash
chmod +x debugger0_a 
```

Posterior a eso abrimos el archivo con `gdb` y aplicamos los siguientes comandos, el primero se encargara de mostrar el código en estructura Intel mientras que el segundo nos  mostrara la clase main   
```bash
gdb debugger0_a   
(gdb) set disassembly-flavor intel
(gdb) disassemble main

```

la clase main contiene lo siguiente
```bash
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   rbp
   0x000000000000112e <+5>:     mov    rbp,rsp
   0x0000000000001131 <+8>:     mov    DWORD PTR [rbp-0x4],edi
   0x0000000000001134 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
   0x0000000000001138 <+15>:    mov    eax,0x86342
   0x000000000000113d <+20>:    pop    rbp
   0x000000000000113e <+21>:    ret

```

Se puede ver que el valor que se le asigna a `eax` es `0x86342` por lo que solo queda convertirlo a decimal y tendremos la bandera 

```python
>>>int(0x86342)
549698
```

**Resultado Final**
```
picoCTF{549698}
```

---
## Notas Adicionales 

---
## Referencias 