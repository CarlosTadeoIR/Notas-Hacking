## Objetivo
We managed to intercept a suspicious file that wanted to be shared with cyber attackers, it is believed to contain hidden instructions, help us find out what message was intended to be shared.

Remember to use the flag format **flagMX{HIDDENINSTRUCTION}**

## Datos de acceso al nivel
```bash
Usuario:
Contraseña:
```
## Solución
```bash
Pass lvl: flagMX{STARTATTACKNOW}
---------------------------------------------
instalar audacity
bajarle la velocidad y el tono
lo que nos da EDFOKTLBPLVIMK
lo cual esta invertido y sería
KMIVLPBLTKOFDE
ahora se necesita una clave para desencriptarlo 
por lo cual hacemos lo siguiente 

┌──(kali㉿kali)-[~/Downloads]
└─$ eyeD3 --write-images=~/Downloads/ Hidden_instruction.mp3
/home/kali/Downloads/Hidden_instruction.mp3                                                                                                              [ 335.18 KB ]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Time: 00:01     MPEG1, Layer III        [ ~130 kb/s @ 48000 Hz - Mono ]
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
ID3 v2.3:
title: 
artist: 
album: 
track: 
Comment: [Description: ] [Lang: eng]

FRONT_COVER Image: [Size: 324981 bytes] [Type: image/png]
Description: 

Writing /home/kali/Downloads/FRONT_COVER.png...
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Downloads]
└─$ 

Ahora con la clave de la imagen que es 
STIESPI lo desencriptamos en cyberchef

```
## Notas Adicionales


| Comando  | Descripción | 
|------------|--------------|

## Referencias 
https://gchq.github.io/CyberChef/
https://eyed3.readthedocs.io/en/latest/