Ocean's 7 - Project Repository

Para Bootcamp The Bridge - Desaf�o por Tripulaciones

Este repositorio es para el almacenamiento de c�digo referente al desaf�o por tripulaciones de TheBridge.
En concreto aquel relacionado con la generaci�n de un modelo de ML de supervisi�n de tr�fico inform�tico.


----------------------------------------------------
Diario del proyecto
----------------------------------------------------

- 24/06/2020
	* Creado repositorio en GitHub

	* Prueba explorada
		- Problemas
			+ Carga del df
				No ha cargado sin usar "error_bad_lines=False".
				De 31813 filas, ha cargado 31809, no s� si se ha cargado columnas
			+ No sabemos qu� hay en las columnas (a qu� datos hacen referencia)
			+ Hay un mont�n de NaN en la columna 2



- 29/06/2020

	* Prueba_26/06 explorada
		- Problemas
			+ Datos demasiado juntos, dif�ciles de separar

	* Prueba_28/06 (1 y 2) explorada
		
		- Avances
			+ Empiezan a distinguirse los datos
		- Problemas
			+ Carga del df
				No ha cargado sin usar "error_bad_lines=False".
			
			+ Hay un mont�n de NaN en general �Puede ser el formato?

- 01/07/2020
	
	* Creada carpeta Pruebas

	* Nueva biblioteca para EDA añadida (EDA.py)
		+ Contiene funciones de EDA
	
	* Ataques antiguos movidos a Pruebas

	* 01-07_Kali notebook creado
		+ Vuelve a haber gran número de columnas vacías. La construcción del df ha sido automática.