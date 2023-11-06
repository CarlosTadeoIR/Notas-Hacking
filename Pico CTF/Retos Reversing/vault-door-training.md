## Objetivo 

Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java)

---
## Datos de acceso al nivel 

https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java

---
## Solución 

cuando descarguemos el archivo solo tenemos que abrirlo con cualquier editor de texto y en la parte de abajo aparecerá lo que ira en la bandera 

```
// The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_3808d338b46");
    }
```

``` bash
w4rm1ng_Up_w1tH_jAv4_3808d338b46
```

**Resultado Final**
```
picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}
```

---
## Notas Adicionales 

---
## Referencias 