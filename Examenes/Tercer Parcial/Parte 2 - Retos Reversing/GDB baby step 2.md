## Objetivo 

Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

---
## Datos de acceso al nivel 

https://artifacts.picoctf.net/c/520/debugger0_b

---
## Solución 
Después de descargar el archivo le damos permisos de ejecución   
``` bash
chmod +x debugger0_b
```

Posterior a eso abrimos el archivo con `gdb` y aplicamos los siguientes comandos, el primero se encargara de mostrar el código en estructura Intel mientras que el segundo nos  mostrara la clase main   
```bash
gdb debugger0_b   
(gdb) set disassembly-flavor intel
(gdb) disassemble main

```

la clase main contiene lo siguiente
``` bash
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   rbp
   0x000000000040110b <+5>:     mov    rbp,rsp
   0x000000000040110e <+8>:     mov    DWORD PTR [rbp-0x14],edi
   0x0000000000401111 <+11>:    mov    QWORD PTR [rbp-0x20],rsi
   0x0000000000401115 <+15>:    mov    DWORD PTR [rbp-0x4],0x1e0da
   0x000000000040111c <+22>:    mov    DWORD PTR [rbp-0xc],0x25f
   0x0000000000401123 <+29>:    mov    DWORD PTR [rbp-0x8],0x0
   0x000000000040112a <+36>:    jmp    0x401136 <main+48>
   0x000000000040112c <+38>:    mov    eax,DWORD PTR [rbp-0x8]
   0x000000000040112f <+41>:    add    DWORD PTR [rbp-0x4],eax
   0x0000000000401132 <+44>:    add    DWORD PTR [rbp-0x8],0x1
   0x0000000000401136 <+48>:    mov    eax,DWORD PTR [rbp-0x8]
   0x0000000000401139 <+51>:    cmp    eax,DWORD PTR [rbp-0xc]
   0x000000000040113c <+54>:    jl     0x40112c <main+38>
   0x000000000040113e <+56>:    mov    eax,DWORD PTR [rbp-0x4]
   0x0000000000401141 <+59>:    pop    rbp
   0x0000000000401142 <+60>:    ret
```

Después de esto tenemos que usar los siguientes comandos  
```
(gdb) break main
(gdb) layout asm
(gdb) run
```

Al aplicar el ultimo comando nos desplegara una ventana nueva en la cual tenemos que ingresar los siguientes comandos 

```
break *0x401142
c
info registers rip
print/d $eax
```

el ultimo comando se encarga de imprimir el valor de la bandera en este caso `307019` con esto solo quedaría darle formato a la bandera

**Resultado Final**
```
picoCTF{307019}
```

---
## Notas Adicionales 

---
## Referencias 