# PI--2--ML---Datathon-Henry

## Descripción del problema
##### Usted ha sido contactado de una importante empresa inversora dentro del rubro de la inmobiliaria en Colombia, con el fin de que implemente un modelo de clasificación que permita clasificar el precio de las propiedades en venta, utilizando los datos que se han puesto a su disposición correspondientes al año 2020.Para esto, específicamente, debe predecir la categorización de las propiedades entre baratas o caras, considerando como criterio el valor promedio de los precios (la media).



### Descripción de las dimensiones
##### id - Identificador del aviso. No es único: si el aviso es actualizado por la inmobiliaria (nueva versión del aviso) se crea un nuevo registro con la misma id pero distintas fechas: de alta y de baja.
##### ad_type - Tipo de aviso (Propiedad, Desarrollo/Proyecto).
##### start_date - Fecha de alta del aviso.
##### end_date - Fecha de baja del aviso.
##### created_on - Fecha de alta de la primera versión del aviso.
##### lat - Latitud.
##### lon - Longitud.
##### l1 - Nivel administrativo 1: país.
##### l2 - Nivel administrativo 2: usualmente provincia.
##### l3 - Nivel administrativo 3: usualmente ciudad.
##### l4 - Nivel administrativo 4: usualmente barrio.
##### l5 - Nivel administrativo 5.
##### l6 - Nivel administrativo 6.
##### rooms - Cantidad de ambientes.
##### bedrooms - Cantidad de dormitorios (útil en el resto de los países).
##### bathrooms - Cantidad de baños.
#####  surface_total - Superficie total en m².
##### surface_covered - Superficie cubierta en m².
##### price - Precio publicado en el anuncio.
##### currency - Moneda del precio publicado.
##### price_period - Periodo del precio (Diario, Semanal, Mensual)
##### title - Título del anuncio.
##### description - Descripción del anuncio.
##### property_type - Tipo de propiedad (Casa, Departamento, PH).
##### operation_type - Tipo de operación (Venta).
##### geometry - Puntos geométricos formados por las coordenadas latitud y longitud.​geometry - Puntos geométricos formados por las coordenadas latitud y longitud.​

## Interpretacion  de los datos 

## Veamos el siguiente gráfico

##### Se observa que:
##### Teniendo conocimientos del dominio de la actividad podríamos conocer intuitivamente cuales son las variables más importantes a la hora de predecir si una propiedad es cara o barata. La superficie cuadrada y la cantidad de habitaciones deberían ser determinantes para ello pero qué ocurre aquí?, porque existen gran cantidad de datos faltantes en estas variables? Y como puede afectar a mi modelo estas variables que según mi conocimiento de dominio.
##### Como se aclara en el problema, en los tipos de variables, la cantidad de dormitorios son relevantes en otros países y no en Colombia. Consecuentemente, si se interpreta que en Colombia no es relevante la cantidad de dormitorios, podría decirse que  un departamento  de 1 habitación costaría lo mismo o no que un departamento de dos habitaciones (o dormitorios) estando uno al lado del otro.  Es decir, estaría determinado por el juego de la oferta y demanda de 1, 2, 3 o más habitaciones. 
##### Por otro lado, la fechas nos ayudan a contextualizar el modelo en un determinado periodo. Brevemente se podría decir que sería complejo que nuestro modelo pueda predecir bien ya que en el año 2020 nos encontrábamos en plena pandemia, y con tal incertidumbre y volatilidad de precios, sería difícil llegar a una buena predicción. La falta de datos en las variables que intuitivamente podrían ser determinantes,  también eventualmente reflejarían  esta situación de crisis o no.

### Algoritmo utilizado
##### En este caso,  al no darle importancia en el problema a la variable (dormitorios) y los pocos datos en las variables dormitorio y metros cuadrados,  que se intuye son que determinantes en la predicción, no hacemos análisis de correlación. Es decir, se descarta análisis de varianza. Normalizamos, codificamos y le aplicamos el algoritmo. 

#### HistGradientBoostingClassifier
##### Este estimador es mucho más rápido que GradientBoostingClassifier para grandes conjuntos de datos (n_muestras >= 10 000).Este estimador tiene soporte nativo para valores faltantes (NaN). 

##### Más info 
##### [HistGradientBoostingClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.HistGradientBoostingClassifier.html "HistGradientBoostingClassifier")
##### [Histogram Boosting Gradient Classifier]( https://www.analyticsvidhya.com/blog/2022/01/histogram-boosting-gradient-classifier/ "Histogram Boosting Gradient Classifier")



### Evaluación del modelo

##### True Positive: El valor real es positivo y la prueba predijo tambien que era positivo. Una persona propiedad es cara y la prueba así lo demuestra.
##### True Negative: El valor real  es negativo y la prueba predijo tambien que el resultado era negativo. O bien la propiedad es barata y la prueba así lo  demuestra.
##### Falso negative: El valor real es positivo, y la prueba predijo  que el resultado es negativo. La propiedad es cara, pero la prueba dice que la propiedad es barata. 
##### Falso positive: El valor real es negativo, y la prueba predijo  que el resultado es positivo. La propiedad es barata, pero la prueba nos dice que es cara.
##### Para un inversor lo importante sería estimar si una propiedad esta en buen precio o barata . Consecuentemente en este caso se debe evaluar la capacidad del modelo de clasificar bien las propiedades baratas. Para ello tendríamos que tener los Falsos Negative lo más bajo posible. Esto quiere decir que mientras mayor (menor) sea el valor de Falsos Positivos, la predicción no (si) clasifica correctamente las propiedades baratas.

##### Medias
##### Accuracy: 0.850214377192494 
##### Recall:  0.5217681652700287
##### Especificidad: 0.9511010534116775
##### Conclusión
#####  El modelo acierta un 0.85 sobre los casos totales, es decir, los resultados positivos sobre el total de casos sería una buena medida pero no suficiente. Para ello, como se comentó anteriormente, un inversor va a adquirir una propiedad si está barata o a “buen precio”por debajo del promedio, por lo tanto es necesario buscar una medida que nos permita evaluar esta situación

##### La especificidad nos va a indicar la  capacidad de detectar si las propiedades son baratas.
##### Finalmente, si una propiedad está por debajo del promedio, hay un 0.95 de que esa propiedad esté clasificada por el modelo como barata, y por lo tanto convendría realizar la inversión.








