Imágenes de Frutas
==================

Utilizo los datos de imágenes pequeñas de Data Access Layer(DAL) https://github.com/cioc/DAL, que es una biblioteca que facilita el uso de los conjuntos de datos. 

Para este proyecto, trabajo con dos colecciones. La primera incluye 200 imágenes, mientras que la otra colección contiene 10,000 imágenes y solo es visible en Amazon Web Service(AWS), al cual actualmente no tengo permiso para acceder.

Inicialmente, transformo el conjunto de datos de imágenes de 32*32 píxeles a un array numpy anidado de 960 componentes tipo gist. Luego normalizo cada gist en todo el conjunto de datos para facilitar el clustering k-means.  

A continuación, utilizo el algoritmo k-means en la colección local de imágenes pequeñas con puntos de inicio aleatorios, selecciono el resultado con menor distorsión y visualizo los clusters resultantes. 

De los resultados del clustering, el rendimiento para clasificar los plátanos y tomates mejora con un K mayor, el número de clusters. Sin embargo, si K es demasiado grande, por ejemplo, si cada imagen tiene su propio cluster, el clustering no tendría sentido. Cuando K es 5 o 6, aunque hay clusters con la mitad de frutas mal clasificadas, los últimos dos clusters tienen resultados de clasificación perfectos. Por lo tanto, en mi opinión, el número óptimo de K para este conjunto de datos es 5 o 6.

