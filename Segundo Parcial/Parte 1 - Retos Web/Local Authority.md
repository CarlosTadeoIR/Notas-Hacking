## Objetivo 

Can you get the flag? Go to this [website](http://saturn.picoctf.net:50920/) and see what you can discover.

---
## Datos de acceso al nivel 

http://saturn.picoctf.net:50920/

---
## Solución 
cuando ingresemos a la pagina esta nos pedirá un usuario y contraseña para ello inspeccionaremos el código fuente ayudándonos del comando `ctrl` + `u`. 

una ves estemos dentro del código fuente tenemos que acceder al archivo [login.php](view-source:http://saturn.picoctf.net:50920/login.php), una ves estemos dentro ahora tenemos que abrir el archivo [secure.js](view-source:http://saturn.picoctf.net:50920/secure.js), dentro de el se encontrara un fragmento de código con la información para el usuario y contraseña

``` bash
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```

regresamos a la pagina principal donde nos pide usuario y contraseña y registramos los datos encontrados 

```
Username : admin
password : strongPassword098765
```

cuando ingresemos los datos y accedamos aparecerá la contraseña 

**Resultado Final**
```
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
```

---
## Notas Adicionales 


---
## Referencias 