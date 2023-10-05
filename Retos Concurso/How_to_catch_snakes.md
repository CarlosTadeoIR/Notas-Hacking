## Objetivo 

We slipped like a snake and accessed confidential information available in a shared folder, to extract it without being discovered we have encrypted it in a simple way

---
## Datos de acceso al nivel 

https://ctfd.anuies.mx/challenges#How%20to%20catch%20snakes-5

---
## Solución 
Al descargar e imprimir el documento nos da como salida  lo siguiente:
  	 | 	  | 	|		 |		|	  	|    |  |	  |	  | |	 |		| |   |   | 	|		 | | 		|  |	|    |			| 	  |	  |   |	|  	|  	 |  	 	
Si nos damos cuenta entre cada pipe hay diferentes combinaciones entre espacios y tabuladores, si sustituimos los tabuladores por "-" y los espacios por "." nos saldria el siguiente codigo morse:

	..-. .-.. .- --. -- -..- .... .. -.. -.. . -. -- . ... ... .- --. . .-- .. - .... --- .-.. -.. ... - ..- ..-. ..-.
Ya traduciendolo nos da como resultado :
	
	FLAGMXHIDDENMESSAGEWITHOLDSTUFF
Solo queda adaptarlo a el formato y listo :)

	flagMX{hiddenmessagewithholdstuff}

---
## Notas Adicionales 

---
## Referencias 
https://morsedecoder.com/es/