# PI--2--ML---Datathon-Henry

## Descripción del problema
##### Usted ha sido contactado de una importante empresa inversora dentro del rubro de la inmobiliaria en Colombia, con el fin de que implemente un modelo de clasificación que permita clasificar el precio de las propiedades en venta, utilizando los datos que se han puesto a su disposición correspondientes al año 2020.Para esto, específicamente, debe predecir la categorización de las propiedades entre baratas o caras, considerando como criterio el valor promedio de los precios (la media).


#### Descripción de las dimensiones y tratamiento

##### 1. id - identificador del aviso. no es único: si el aviso es actualizado por la inmobiliaria (nueva versión del aviso) se crea un nuevo registro con la misma id pero distintas fechas: de alta y de baja.
 ##### Se elimina esta esta columna y cada fila se lo considera como un registro o suceso. Es decir no existen filas duplicadas cuando se hace la carga incremental ya que difieren las fechas. 
##### 2. ad_type - Tipo de aviso (Propiedad, Desarrollo/Proyecto). 
##### Se elimina ya que existe un solo tipo de aviso: propiedadSe elimina ya que existe un solo tipo de aviso: propiedad
##### 3. start_date - Fecha de alta del aviso.  Y created_on - Fecha de alta de la primera versión del aviso.
##### Puede ayudarnos a calcular variaciones
##### 4. Y end_date –( Fecha de baja del aviso) No se le ha encontrado utilidad en principio y se elimina. 
