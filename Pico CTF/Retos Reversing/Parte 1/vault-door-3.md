## Objetivo 

This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java

---
## Solución 


una ves descargamos el archivo tenemos que hacer las siguientes modificaciones en el código fuente 

``` java
String userInput = "picoCTF{jU5t_a_sna_3lpm12g94c_u_4_m7ra41}";
```

Lo que se esta haciendo en este caso es directamente omitir que el usuario escriba lo que podria ser la bandera dejando por default  el valor que se nos da al final del archivo

luego tenemos que cambiar al final de la función checkPassword
```java
    String s = new String(buffer);
	System.out.println(s);
	return true;
    //return s.equals("jU5t_a_sna_3lpm12g94c_u_4_m7ra41");
    }
```

De esta forma al guardar y compilar el archivo para ejecutarlo mostrara lo siguiente
```
Enter vault password: jU5t_a_s1mpl3_an4gr4m_4_u_c79a21
Access granted.
```

de esta forma solo seria completar la bandera 

**Resultado Final**
```
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_c79a21}
```


---
## Notas Adicionales 


---
## Referencias 