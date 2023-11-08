## Objetivo 

In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/9505cca05dc00fecead41106370ee619/VaultDoor5.java)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/9505cca05dc00fecead41106370ee619/VaultDoor5.java

---
## Solución 

la forma mas fácil de dar solución a este problema es con ayuda de la pagina [CyberChef (gchq.github.io)](https://gchq.github.io/CyberChef/)  donde tenemos que pegar la siguiente cadena extraída del código fuente 

``` bash
JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTM4JTM0JTY2JTY0JTM1JTMwJTM5JTM1
```

en el https://gchq.github.io/CyberChef/ primero tenemos que decodificar de base54 y después  con el URL decoder , esto nos dará el siguiente resultado  

```
c0nv3rt1ng_fr0m_ba5e_64_84fd5095
```

**Resultado Final**
```
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_84fd5095}
```

---
## Notas Adicionales 
el otro método es editar el código java de esta forma 
```java
    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTM4JTM0JTY2JTY0JTM1JTMwJTM5JTM1";
        //return base64Encoded.equals(expected);
	String b64 = new String(Base64.getDecoder().decode(expected));
	String url =URLDecoder.decode(b64);
	System.out.println(url);
	return true;
    }
```

---
## Referencias 
[From Base64, URL Decode - CyberChef (gchq.github.io)](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm1KVFkySlRjeUpUTXdKVFprSlRWbUpUWXlKVFl4SlRNMUpUWTFKVFZtSlRNMkpUTTBKVFZtSlRNNEpUTTBKVFkySlRZMEpUTTFKVE13SlRNNUpUTTE)

