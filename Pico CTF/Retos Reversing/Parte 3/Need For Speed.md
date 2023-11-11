## Objetivo 

The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed

---
## Solución 

Si analizamos el archivo que descargamos veremos que es un archivo ejecutable por lo que tenemos que asignarle los permisos correspondientes 

```bash
file need-for-speed 
# need-for-speed: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b4b1e824082c140091043151ab990149efa44806, not stripped

chmod +x need-for-speed 

```

Si ejecutamos el archivo veremos que al iniciar dirá que se esta creando la llave pero antes de eso se acaba el tiempo y termina la ejecución del programa 

```bash
./need-for-speed  
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
```

lo que podemos hacer es utilizar la herramienta `gdb`

``` bash
gdb need-for-speed 
# GNU gdb (Debian 13.2-1) 13.2
# Copyright (C) 2023 Free Software Foundation, Inc.
# License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
# This is free software: you are free to change and redistribute it.
# There is NO WARRANTY, to the extent permitted by law.
# Type "show copying" and "show warranty" for details.
# This GDB was configured as "x86_64-linux-gnu".
# Type "show configuration" for configuration details.
# For bug reporting instructions, please see:
# <https://www.gnu.org/software/gdb/bugs/>.
# Find the GDB manual and other documentation resources online at:
#     <http://www.gnu.org/software/gdb/documentation/>.

(gdb) set disassembly-flavor intel
(gdb) disassemble main
# Dump of assembler code for function main:
#    0x000000000000091a <+0>:     push   rbp
#    0x000000000000091b <+1>:     mov    rbp,rsp
#    0x000000000000091e <+4>:     sub    rsp,0x10
#    0x0000000000000922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
#    0x0000000000000925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
#    0x0000000000000929 <+15>:    mov    eax,0x0
#    0x000000000000092e <+20>:    call   0x8d8 <header>
#    0x0000000000000933 <+25>:    mov    eax,0x0
#    0x0000000000000938 <+30>:    call   0x82f <set_timer>
#    0x000000000000093d <+35>:    mov    eax,0x0
#    0x0000000000000942 <+40>:    call   0x87d <get_key>
#    0x0000000000000947 <+45>:    mov    eax,0x0
#    0x000000000000094c <+50>:    call   0x8ac <print_flag>
#    0x0000000000000951 <+55>:    mov    eax,0x0
#    0x0000000000000956 <+60>:    leave
#    0x0000000000000957 <+61>:    ret
# End of assembler dump.

(gdb) break main 
# Breakpoint 1 at 0x91e
(gdb) run
# Starting program: /home/kali/Downloads/Reversing/parte3/speed/need-for-speed 
# [Thread debugging using libthread_db enabled]
# Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

# Breakpoint 1, 0x000055555540091e in main ()
(gdb) disassemble main
# Dump of assembler code for function main:
#    0x000055555540091a <+0>:     push   rbp
#    0x000055555540091b <+1>:     mov    rbp,rsp
# => 0x000055555540091e <+4>:     sub    rsp,0x10
#    0x0000555555400922 <+8>:     mov    DWORD PTR [rbp-0x4],edi
#    0x0000555555400925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi
#    0x0000555555400929 <+15>:    mov    eax,0x0
#    0x000055555540092e <+20>:    call   0x5555554008d8 <header>
#    0x0000555555400933 <+25>:    mov    eax,0x0
#    0x0000555555400938 <+30>:    call   0x55555540082f <set_timer>
#    0x000055555540093d <+35>:    mov    eax,0x0
#    0x0000555555400942 <+40>:    call   0x55555540087d <get_key>
#    0x0000555555400947 <+45>:    mov    eax,0x0
#    0x000055555540094c <+50>:    call   0x5555554008ac <print_flag>
#    0x0000555555400951 <+55>:    mov    eax,0x0
#    0x0000555555400956 <+60>:    leave
#    0x0000555555400957 <+61>:    ret
# End of assembler dump.
(gdb) call (int) get_key()
# Creating key...
# Finished
# $1 = 9
(gdb) call (int) print_flag()
# Printing flag:
# PICOCTF{Good job keeping bus #190ca38b speeding along!}
# $2 = 56
```

después de ejecutar los comandos se nos dara la bandera 

**Resultado Final**
```
PICOCTF{Good job keeping bus #190ca38b speeding along!}
```

---
## Notas Adicionales 

---
## Referencias 