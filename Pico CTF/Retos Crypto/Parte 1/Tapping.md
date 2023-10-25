## Objetivo 

Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 48247`.

---
## Datos de acceso al nivel 

`nc jupiter.challenges.picoctf.org 48247`.

---
## Solución 

primero accedemos al servidor 

``` bash
nc jupiter.challenges.picoctf.org 48247
```

una ves dentro nos mostrara un mensaje y nos sacara en automático, este es el mensaje 

```bash
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. .---- ..--- -.... .---- ....- ...-- ---.. .---- ---.. .---- } 
``` 

es claro que con la descripción del problema y viendo el formato deducimos que se trata de código morse por lo que usando algún decodificador de morse que en este caso es [CyberChef](https://gchq.github.io/CyberChef/)
descubriremos la bandera 

```
PICOCTFM0RS3C0D31SFUN1261438181
```

solo faltaría apegarla al formato de las banderas 

**Resultado Final**
```
picoCTF{M0RS3C0D31SFUN1261438181}
```

---
## Notas Adicionales 

---
## Referencias 
https://gchq.github.io/CyberChef/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4tLS0tIC4uLS0tIC0uLi4uIC4tLS0tIC4uLi4tIC4uLi0tIC0tLS4uIC4tLS0tIC0tLS4uIC4tLS0tIH0g