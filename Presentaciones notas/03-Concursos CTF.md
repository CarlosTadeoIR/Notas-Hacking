__¿Que son los concursos CTF?__
CTF o "Capture The Flag" es un concurso cuyo objetivo es resolver diversas retos asociados a diferentes vulnerabilidades de hardware o software. 

estos concursos no tienen mucha duración ya que pueden durar desde horas hasta unos pocos días

_¿por que los concursos ?_
para aumentar el interés de los estudiantes 
las empresas suelen organizar CTFs para reclutar talento y satisfacer la demanda de la fuerza laboral en ciberseguridad

_¿Tipos de concursos?_
jeopardy (como 100 mexicanos dijeron)
attack - defender

# Jeopardy
- comprende una serie de tareas o desafíos clasificados en categorías tales como 
general skills, osint, web, forensic, Cryptography (crypto), Reversing, Binary explotation (pwning) ,misc.
- El equipo puede ganar algunos puntos por cada tarea resuelta.
- Las tareas complicadas generalmente dan más puntos.

# Attack-defense 
cada equipo tiene uno o varios hosts con servicios vulnerables 
a la par que atacas defiendes 

# ¿Qué categorías comprende un CTF Jeopardy?
# General Skills

bases de lo que ya se hacer
sistemas numéricos y conversión entre ellos
conceptos básicos de Linux
conceptos básicos de programación  
conceptos básicos de red
conceptos básicos de ciberseguridad 

OSINT
- Tiene que ver con la recolección y análisis de datos obtenidos de fuentes abiertas (disponibles públicamente), para encontrar información procesable que permita identificar plenamente a una persona o institución.

- Se parte de un nombre, un correo, una imagen, una dirección IP, o cualquier dato disponible.

WEB
- Tienen que ver con vulnerabilidades específicas a los diferentes lenguajes de programación utilizados para crear los sitios web que todo desarrollador debe considerar.

FORENSIC
- Trata sobre recuperar el rastro que queda en una computadora al usarla.
- Se trata de encontrar los datos que aparentemente se eliminan, no se almacenan o se registran de forma encubierta.

Cryptography (Crypto)
- Trata de los diferentes algoritmos de cifrado clásicos y los más modernos como cifrado por bloques y criptografía de llave pública, utilizados en diferentes mecanismos de autenticación, firmas digitales y certificados digitales.

Reversing
- volver sobre sus pasos 
- Consiste en tomar un programa compilado y aplicar ingeniería inversa para obtener un código legible generalmente en lenguaje ensamblador o una interpretación en lenguaje C.
- En algunos casos incluye revertir un cifrado o codificación hecho en algún lenguaje de alto nivel, examinando el código y entendiendo la lógica.

Binary Explotation (Pwning)
- Consiste en encontrar vulnerabilidades en un archivo binario (compilado), explotarla para obtener acceso a la línea de comando de un sistema remoto.
- Pasa por entender la lógica del archivo binario desensamblado para modificar su función o evadir medidas de seguridad.

# ¿Qué fases comprende un CTF Attack-Defense?

_Reconocimiento (Reconnaissance or Footprinting)_
- El atacante busca obtener la mayor cantidad de información como sea posible acerca del objetivo en evaluación previo al lanzamiento de un ataque.

_Escaneo (Scanning)_
- Es la fase de pre ataque cuando el hacker escanea la red en busca de información específica en base a la información obtenida durante el reconocimiento.
- El escaneo puede incluir el uso de dialers, port scanners, network mapping, sweeping, vulnerability scanners, etc.

_Ganar acceso (Gaing Access o Exploiting )_

- Se explotan las vulnerabilidades encontradas.
- El atacante trata de retener su propiedad sobre el sistema.
- Harán difícil a otros poder acceder al mismo, asegurando un acceso exclusivo con un backdoor, rootkit o trojan.
- el atacante puede robar datos de tu equipo y almacenar mas cosas 

_Mantener acceso (maintaining access)_

- Es la fase donde el atacante trata de retener su propiedad sobre el sistema.
- Trata de asegurar un acceso exclusivo al sistema mediante la instalación de Backdoors, Rootkits o Trojans.
- Pueden subir, bajar o manipular datos, aplicaciones, configuraciones en el sistema bajo su control.
- Usa el sistema comprometido para lanzar otros ataques.

Cubrir huellas ( Covering Tracks )
- El atacante trata de esconder sus actividades maliciosas.
- Trata de permanecer desapercibido y no capturado.
- Borra evidencia que podría llevar a su persecución.
