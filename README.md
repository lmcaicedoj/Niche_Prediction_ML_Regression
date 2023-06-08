# Niche_Prediction_ML_Regression
En este proyecto evaluamos el desempeño de distintos algoritmos de aprendizaje de maquina, con respecto al algoritmo del estado del arte Biomat-Niche Modeling (BNM), para determinar el nicho real de una especie a partir de limitadas observaciones de campo contribuyendo así a una gestión de los recursos naturales y a una planificación de la conservación de la biodiversidad más efectiva. 

Este repositorio esta comprendido por los siguientes archivos: 

(i) BNM_Script_Matlab.html: Es un notebook donde se encuentan los pasos esenciales de generación de especies virtuales y modelado de nicho Biomat-Niche Modeling (BNM). BNM es el modelo del estado del arte utilizado en este modelo como la referencia a comparar con los demas modelos de aprendizaje de Maquina. 

(ii) EMA_Project_Nichos.pdf: Trabajo escrito del proyecto donde se encontrara la descripcion detallada del proyecto, metodologia, analisis de datos, conclusiones y posibles trabajos futuros sobre el tema investigado. 

(iii) dataTest_Final.csv: Archivo donde esta el set de datos utilizados para la elaboracion del presente proyecto. 

(iv) Project_Nichos_EMA_Final_Project_VF.zip: Dentro de este archivo comprimido se econtrara el jupyter notebook que hemos construido con las siguientes secciones para su facil navegacion:

	(0) Importing Libraries:
		En esta seccion importamos todas las librerias necesarias para limpiar, organizar, graficar, y modelar los datos estudiados. Entre las librerias mas importantes esta: sklearn, pandas,	numpy, xgboost, matplotlib, seaboarn, scipy, and statsmodels. 

	(1) Importing Dataset:
		Aqui el dataset bajo estudio fue importado y su informacion basica (i.e. numero de columnas, numero de 	filas, tipo de variables, uso de memoria). Aqui identificamos que algunas columnas tenian datos nulos que no iban a aportar en el proyecto, por tanto debiamos removerlos. 

	(2) Exploratory Data Analysis:
		La exploracion inicial de los datos se realizo por medio de la funcion describe(), la cual ayudo a indentificar las diferentes escalas en las que estaba cada variable. Esto tambien ayudo a identificar que Longitud y latitud a pesar de ser variables importantes para graficar las predicciones obtenidas pero no eran variables que describieran la variable objetivo y podian ocasionar un sesgo espacial en los resultados. Ademas se encontraron las correlaciones entre varialbes.
	
	(3) Scaling the studied dataset:
		En esta seccion se escalaron todas las variables de interes (excepto la variable objetivo, Latitud y longitud), dejando todos los valores comprendidos en un rango entre -3 y 3. 
	
	(4) Delete null entries:
		Aqui borramos los registros nulos para que no intercedieran con la modelacion. 
	
	(5) Principal Component Analysis (PCA):
		Se realizo analisis de componentes principales para identificar los pesos de cada una de la variables en las componentes resultantes. En este proyecto PCA no fue crucial a la hora de toma de decisiones. Sin embargo, PCA si ayudo a identificar que variables como bio10 eran importantes para predecir la variable objetivo. 
	
	(6) Splitting dataset between train, test, and validation sets:
		El set de datos estudiado se dividio en 20% validacion y el 80% de datos restantes se dividio en 70% training set y 30% testing set. 
	
	(7) Modeling:
		En esta seccion se modelaron los datos utilizando los siguientes algoritmos: Regresion Lineal Basica, Regresion Lineal Ridge, Regresion Lineal Lasso, Elastic Net, Decision Tree, Random Fores, Multilayer Perceptron, Support Vector Machine, y XGBoost. Para su comparacion se implementaron las metricas MAE, MSE, R2, e indicadores estadisticos  (media, varianza, asimetria, curtosis) para identificar la distribucion de los residuales obtenidos despues de la prediccion.   
	
	(8) Cross Validation (CV):
		Luego de comparar los modelos, escogimos los mejores para aplicar validacion cruzada. CV se aplico con el objetivo de optimizar la prediccion realizada por los modelos en la anterior seccion (minimizando la metrica MAE), escogiendo los mejores hiperparametros de los modelos estudiados.  Los modelos estudiados fueron Ridge Linear Regression, Random Forest y XGBoost. Se observan mejoras significates en la precision para Random Fores y XGBoost.  
	
	(9) Results from Best models for Niche Map Prediction:
		Finalmente los mejores modelos son utilizados para predecir la probabilidad de que una especie este en cierta locacion, se extrae la variable objetivo predecida y se grafican para su comparacion (aclaracion: en este notebook no estan las graficas realizadas con los datos predichos para cada locacion; para realizar estos mapas se debe utilizar la ultima seccion del notebook BNM_Script_Matlab.html). 
	
	(10) Complementary Plots: 
		Esta seccion se utilizo para mirar con detalle las posibles colinealidades entre variables. 
	
	(11) Run it all!!!
		Esta seccion del notebook ayuda a correr el algoritmo de manera rapida y facil, incorporando todos los ajustes que se pueden haber realizado lineas arriba.

Esperemos disfruten del proyecto. Ha sido una experiencia memorable.  
