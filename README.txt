Ocean's 7 - Project Repository

Para Bootcamp The Bridge - Desafio por Tripulaciones

Este repositorio es para el almacenamiento de codigo referente al desafío por tripulaciones de TheBridge.
En concreto aquel relacionado con la generación de un modelo de ML de supervisión de tráfico informático.


----------------------------------------------------
Diario del proyecto
----------------------------------------------------

- 24/06/2020
	* Creado repositorio en GitHub

	* Prueba explorada
		- Problemas
			+ Carga del df
				No ha cargado sin usar "error_bad_lines=False".
				De 31813 filas, ha cargado 31809, es posible que también columnas
			+ No sabemos qué hay en las columnas (a qué datos hacen referencia)
			+ Hay un montón de NaN en la columna 2



- 29/06/2020

	* Prueba_26/06 explorada
		- Problemas
			+ Datos demasiado juntos, difíciles de separar

	* Prueba_28/06 (1 y 2) explorada
		
		- Avances
			+ Empiezan a distinguirse los datos
		- Problemas
			+ Carga del df
				No ha cargado sin usar "error_bad_lines=False".
			
			+ Hay un montón de NaN en general ¿Puede ser el formato?

- 01/07/2020
	
	* Creada carpeta Pruebas

	* Nueva biblioteca para EDA añadida (EDA.py)
		+ Contiene funciones de EDA
	
	* Ataques antiguos movidos a Pruebas

	* 01-07_Kali notebook creado
		+ Vuelve a haber gran número de columnas vacías. La construcción del df ha sido automática.

- 04/07/2020

	(Dibmar)
	* Explorando 01-07_Kali
		Se ha presupuesto que los espacios NaN corresponden con la misma información que los válidos
		+ Se va a dividir el df en 3:
			- kali_frame (contiene el número de ataque y fecha)
				Tiempos de ataque explorados. Pueden ser útiles para predicción
			- kali_ip (contiene la ip de ataque, objetivo y la geolocalización del atacante)
				Sometido a bfill() y ffill() para eliminar los NaNs presentes
				Columnas de geolocalización ignoradas por no contener nada
			- kali_http (contiene host, paquetes, métotos, cookies, protocolos e información del paquete)
				Sometido a bfill() y ffill() para eliminar los NaNs presentes
	
	* Librería EDA
		+ Añadida función value_counter (cuenta los valores de todas las columnas y los muestra)

- 06/07/2020

	(Dibmar)
	* Explorando 01-07_Kali(2)
		Se ha presupuesto que los espacios NaN corresponden con la misma información que los válidos
		Se va a proponer la idea de que los espacios vacíos sean representados por '0'
		+ Se va a dividir el df en 3:
			- kali_frame (contiene el númeor de ataque y fecha)
				Tiempos de ataque explorados. Pueden ser útiles para predicción
			- kali_ip (contiene la ip de ataque, objetivo y la geolocalización del atacante)
				Sometido a bfill() y ffill() para eliminar los NaNs presentes
				Columnas de geolocalización ignoradas por no contener nada
			- kali_http (contiene host, paquetes, métotos, cookies, protocolos e información del paquete)
				Sometido a bfill() y ffill() para eliminar los NaNs presentes


- 07/07/2020

	(Dibmar)
	* Explorando 07-07_Kali-Normal
		Vuelve a haber presente un número elevado de NaNs. Sin embargo, el problema de importación se ha solucionado.
		+ Se va a dividir el df en 3:
			- kali_time (contiene el número de ataque y fecha)
				Tiempos de ataque explorados. Pueden ser útiles para predicción
			- kali_local (contiene la ip de ataque, objetivo y la geolocalización del atacante)
				
			- kali_protocol (contiene host, paquetes, métotos, cookies, protocolos e información del paquete)
				

- 08/07/2020

	(Dibmar)
	* Explorando 08-07_Kali-Normal
		Vuelve a haber presente un número elevado de NaNs. Sin embargo, el problema de importación se ha solucionado.
		+ Se va a dividir el df en 3:
			- kali_time (contiene el númeor de ataque y fecha)
				Tiempos de ataque explorados. Pueden ser utiles para predicción
			- kali_local (contiene la ip de ataque, objetivo y la geolocalización del atacante)
				
			- kali_protocol (contiene host, paquetes, métotos, cookies, protocolos e información del paquete)
				Protocolos prácticamente vacíos (99%). Se espera que la cosa mejore en el siguiente envío


- 11/07/2020

	(Dibmar)
	* Explorando 08-07_Hydra_attacks (tanto éxito como fracaso)
		Vuelve a haber presente un número elevado de NaNs. Preocupante columna de protocolo
		Se observa una diferencia de un 18% entre los ataques fallidos y los exitosos, siendo los primeros los más largos.
		Por otro lado, los ataques fallidos también utilizan un mayor número de protocolos, mientras que los exitosos usan TCP y FTP
		No parece haber relación entre hydra['info'] y hidra_fail['info']
		+ Se va a dividir el df en 3:
			- hydra_time (contiene el númeor de ataque y fecha)
				Tiempos de ataque explorados. Pueden ser útiles para predicción
			- hydra_local (contiene la ip de ataque, objetivo y la geolocalización del atacante)
				Geolocalización sigue estando vacía.
			- hydra_protocol (contiene host, paquetes, métotos, cookies, protocolos e información del paquete)
				Protocolos prácticamente vacíos (99%). Se espera que la cosa mejore en el siguiente envío
	
	* Añadidas funciones a la librería EDA
		El objetivo es generar plot sencillos (feos por necesidad) para agilizar la labor de representación. No están pensadas para plots elaborados
		+ plot_bar
			Gráfico de barras
		+ plot_line
			Gráfico de líneas
		+ plot_pie
			Gráfico de quesos