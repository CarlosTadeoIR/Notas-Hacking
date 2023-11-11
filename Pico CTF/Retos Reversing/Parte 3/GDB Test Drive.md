## Objetivo 

Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/86/gdbme).Here's the test drive instructions:

---
## Datos de acceso al nivel 

```bash
$ chmod +x gdbme
$ gdb gdbme
(gdb) layout asm
(gdb) break *(main+99)
(gdb) run
(gdb) jump *(main+104)
```

https://artifacts.picoctf.net/c/86/gdbme

---
## Solución 

para resolver este reto, después de haber descargado el archivo tenemos que verificar que tengamos la librería gdb instalada 

si ya la tenemos instalada nos colocamos en el directorio donde esta nuestro archivo e introducimos los siguientes comandos 

``` bash
chmod +x gdbme
gdb gdbme
layout asm
```

Después de ingresar los comandos anteriores aparecerá una nueva ventana que nos muestra instrucciones del lenguaje ensamblador  por lo que a continuación solo tenemos que aplicar estos comandos 

```
break *(main+99)
run
jump *(main+104)
```

cuando ingresemos el ultimo comando nos cargara la bandera

**Resultado Final**
```
picoCTF{d3bugg3r_dr1v3_72bd8355}
```

---
## Notas Adicionales 
no pude instalar gdb en mi maquina virtual por lo que use https://webshell.picoctf.org/ la cual si lo tiene instalado 

---
## Referencias 