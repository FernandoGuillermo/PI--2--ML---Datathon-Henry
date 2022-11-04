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










































