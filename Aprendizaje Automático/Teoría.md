# Clase 4
## Segmentación
¿Cómo validamos que la segmentación se hizo de forma correcta?
¿Se pueden comparar resultados con otros?

## Clasificación
¿Cómo podemos asegurar que la clasificación es correcta?
¿Qué nos garantiza eso?

Teniendo los **datos etiquetados** se pueden sacar las métricas de interés como precisión, rendimiento, etc.

La evaluación SIEMPRE requiere de que los datos estén etiquetados, independiente del modelo que se ocupe para entrenar los datos.

## Modelo general de AA
Existe la necesidad de tener un conjunto de datos con resultados válidos para poder comparar resultados de nuevo modelo de ML.

### Conjuntos de datos
Hay una gran proliferación de datos y una fácil disponibilidad.

#### Tipos de datos
- Imágenes
- Texto
- Series de tiempo
- Datos categóricos 
- Vídeos

#### Dataset
Se compone de:
- Datos de entrenamiento: Sirven para entrenar el modelo. Estos se subdividen en entrenamiento y validación, el de validación es aún más pequeño y es para afinar el entrenamiento. 
- Datos de evaluación: Sirven para evaluar el modelo y NUNCA se topan con los datos de entrenamiento. 

## Ground Truth
Consiste en un conjunto de datos y una única etiqueta asociada. Es 100% probable de que la etiqueta es verdadera. Se utiliza para validar algoritmos de segmentaicón y clasificación.

Existen casos donde no hay un Ground Truth, por ejemplo, en el caso de las mamografías. 

## Gold-Standard
Es una alternativa válida a falta de GT.
Consiste en un conjunto de datos y una única etiqueta asociada a partir de opinión de expertos en el área.

Sin embargo, considerar la opinión de un único experto genera sesgo en el gold-standard. Lo idóneo es considerar opinión de varios expertos.

## Aprendizaje supervisado basado en múltiples expertos
Cada imagen tiene múltiples etiquetas, haciendo que el modelo genere una sola etiqueta. 

Se puede determinar la etiqueta tomando la mayoría, unanimidad o ponderación. Es decir, darle cierta credibilidad a cada etiqueta. 

## Aumento de datos
Se puede hacer a través de la transformación de los datos, por ejemplo, rotar una imagen, desplazar, ampliar, achicar, estirar, etc. 

## Cross-Validation
¿Cómo nos aseguramos que nuestro conjunto de test es confiable?
Queremos asegurarnos que todo el dataset pueda pasar a ser el conjunto de datos de evaluación, así demostrando la robustez del modelo. 
Se suele ocupar cuando hay pocos datos, ya que no se puede confiar en la precisión de un solo conjunto de validación al ser tan pequeña la muestra.
Recordar que la elección de los conjuntos para entrenamiento debe ser al azar.

## No Free Lunch
No existe el mejor modelo para todos los problemas.
Existen modelos útiles para casos particulares. La razón es que el conjunto de suposiciones (inductive bias) que funciona bien en un dominio, puede funcionar muy mal en otro. 
AA busca explotar estas peculiaridades o regularidades de los datos en un dominio particular. 
Se pueden emplear modelos entrenados en otras áreas para aplicarla en nuestra área.



