Readme

Conclusiones:

Empezando por el modelo 1, su desempeño obtuvo un R2 de 0.429, el cual es insuficiente para considerar sus predicciones aceptables utilizando 0.50 como parámetro mínimo de rendimiento; su promedio de equivocación es de 1174 bicis. Lo positivo del modelo 1 es que, en contraste con el baseline, fue ampliamente mayor su R2 (0.429 contra -0.019) y con 418 bicis menos de promedio de equivocación (1174 contra 1592). Por otro lado, el modelo 2 logró subir su R2 a 0.763, quedando por debajo del ideal que es 0.80, y bajar el promedio de equivocación a 728 bicis, con la inclusión de una variable más ("yr") a las que ya tenía el modelo 1.

La variable con el coeficiente más grande es "temp" en el modelo 1: a mayor temperatura, más alquileres. En el caso de "hum" y "windspeed", al ser negativos, restan. Como ya están normalizadas entre 0 y 1 podemos comparar entre coeficientes, y coincide con el heatmap, donde "temp" tenía la mayor correlación con "cnt". En la variable "yr" el coeficiente suma 1900 bicis más por día en 2012, en iguales condiciones de clima que en 2011.

De las 3 variables del primer modelo, "temp" es la que más aporta; "hum" y "windspeed" mejoran el modelo en menor medida. Cuando hablamos de clima en general, la temperatura es el dato que más utilizamos para informarnos, pero en este caso el clima solo explica el 43% de la variación de los alquileres, por lo que no alcanza para predecir bien. Por eso sugerimos agregar "yr" a las features que ya tenía el primero. El segundo modelo aprendió que los alquileres eran más altos en 2012 que en 2011, probablemente por el crecimiento del servicio entre un año y el otro. La variable "atemp" (sensación térmica) fue descartada por colinealidad, y "casual" y "registered", si las sumamos, dan el resultado que queremos predecir ("cnt"), por lo que también fueron descartadas.

El modelo 1 tuvo como resultado 0.473 en R2 de entrenamiento y 0.429 en R2 de test, valores muy similares entre sí. Respecto al modelo 2, su R2 de entrenamiento es 0.717 y, a diferencia del primer modelo, su R2 de test fue mayor, con 0.763. En ambos modelos los valores de test y entrenamiento son similares, lo que indica que no hay sobreajuste: el modelo aprendió la relación general.


Información del dataset:

	- yr : year (0: 2011, 1:2012)
	- temp : Normalized temperature in Celsius. The values are divided to 41 (max)
	- atemp: Normalized feeling temperature in Celsius. The values are divided to 50 (max)
	- hum: Normalized humidity. The values are divided to 100 (max)
	- windspeed: Normalized wind speed. The values are divided to 67 (max)

	- cnt: count of total rental bikes including both casual and registered
	