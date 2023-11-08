## Objetivo 

This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/834acd392e0964a41f05790655a994b9/VaultDoor4.java

---
## Solución 

Para dar solucionar este problema solo tenemos que comentar esta parte del código 

``` java
  //for (int i=0; i<32; i++) {
	  //if (passBytes[i] != myBytes[i]) {
	  // return false;
	  //}
  // }
```

Después de eso tenemos que agregar las siguientes líneas antes de que se regrese el TRUE

```java
	String flag = new String(myBytes);
	System.out.println(flag);
    return true;
```

cuando ejecutemos el código solo tenemos que agregar una cadena de 32 caracteres, sin importar si son repetidos, igual regresara la bandera 

```
Enter vault password:estaconsks kabdkansdñbabdaesvsds
jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e
Access granted. 

```

De esta forma solo quedaría completar la bandera 

**Resultado Final**
```
picoCTF{jU5t_4_bUnCh_0f_bYt3s_f4a8cd8f7e}
```

---
## Notas Adicionales 

---
## Referencias 