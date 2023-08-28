
# Level 0
---
## objetivo 
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is **bandit.labs.overthewire.org**, on port 2220. The username is **bandit0** and the password is **bandit0**. Once logged in, go to the [Level 1](https://overthewire.org/wargames/bandit/bandit1.html) page to find out how to beat Level 1.

---
## Datos de acceso al nivel 
```
Server  : **bandit.labs.overthewire.org**
User    : **bandit0**
Pasword : **bandit0**
Puerto  : 2220
```

---
## Solución 

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

---
## Notas Adicionales 

|**Comando** | **Descripción** |
|:---------:|:-------------|
| pwd | Me indica el directorio actual |
| whoami | Saber el usuario Actual |
| cd / | LLeva al directorio raíz |
| ls | Lista los archivos en la carpeta actual |


---
## Referencias 
[Secure Shell - Wikiwand](https://www.wikiwand.com/en/Secure_Shell)
[How to Use SSH (with Pictures) - wikiHow](https://www.wikihow.com/Use-SSH)
