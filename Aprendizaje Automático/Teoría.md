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

# Clase 5
## Parámetros
Definen el modelo de aprendizaje o la función predictora.
No se fijan valores óptimos para los parámetros, sino que los **parámetros aprenden sus propios valores** a partir de los datos.
Son modificados directamente por el algoritmo de aprendizaje durante el proceso de entrenamiento. 

Un modelo está entrenado cuando las métricas son buenas, haciéndolo adecuado para hacer predicciones sobre datos no vistos. Se van a detener cuando los valores de los parámetros hayan sido optimizados.

La idea de entrenar al modelo es poder encontrar los valores de los parámetros que hagan que el odelo funcione correctamente ante los datos de **validación**, más que antes los datos de entrenamiento. 
No me importan los datos de entrenamiento en sí porque va a tener métricas casi perfectas, es por eso que se utilizan los datos de validación.

## Hiper-parámetros
Representan propiedades del algoritmo de aprendizaje que se deben definir **antes de empezar el entrenamiento**. Se definen **antes** el cómo se le darán los datos, por ejemplo, cuántas iteraciones debe hacer, de qué forma se les pasará los datos (en bloques), etc.
¿Cómo se hará el experimento? Por ejemplo: ¿Habrá interacción con la niña? ¿Se le mostrarán las figuras desde lejos o cerca? 
Una vez especificados, los valores de los hiperparámetros no modifican su valor durante el entrenamiento. 

## Ajuste de hiper-parámetros
Es ir probando los hiper-parámetros y se va comparando para escoger los mejores hiper-parámetros para el modelo. 

## Formas de ajuste
### Grilla
Una opción es hacer una búsqueda por grilla, los chinos dijeron que el hiperparámetro valía "a" y el otro valía "b", por lo que se empieza a probar con un +- delta para entrenar el modelo, así probando y borrando la memoria.
Esto resulta en unas métricas y se ordenan de mayor a menor, así escogiendo los mejores hiper-parámetros.
![[Pasted image 20250401101341.png]]

### Random
Otra opción es escoger valores random para poder entrenar el modelo y se entrena el modelo con cada par de datos. Esto nuevamente resulta en métricas de cada modelo, y así se ordenan de mayor a menor según qué tan bueno es el modelo. 
![[Pasted image 20250401101412.png]]

## Versus
Los parámetros y los hiper-parámetros son variables. Pueden tomar distintos valores, ya sea aprendiendo de los datos o estableciendo los valores manualmente.
Los parámetros permiten al modelo aprender las reglas a partir de los datos, mientras que los hiper-parámetros controlan cómo se entrena el modelo. 

## Ejemplo: Regresión lineal simple
Modelo: Y = aX + b
Parámetros: a y b
Hiper-parámetros: Tasa de aprendizaje y el número de iteraciones. Por ejemplo, utilizando el algoritmo de descenso de gradiente para encontrar los valores óptimos de los parámetros a y b minimizando la función de coste.

## Ejemplo: Red neuronal
Modelo: Red neuronal profunda
Parámetros: Miles de parámetros pesos y sesgos en forma de matrices de pesos y vectores de sesgo. Los valores se actualizan mediante el algoritmo de backpropagation.
Hiper-parámetros: Controlan los balores de pesos y sesgos
- Tipop de función de pérdida
- Tipo de optimizador
- Tipo de función(es) de activación
- Tamaño del lote
- Épocas

## BIAS (sesgo)
Es la diferencia entre la predicción promedio de nuestro modelo con respecto al valor correcto. 
Un modelo con alto bias produce alto error en el conjunto de datos de entrenamiento como en el de validación, y además causa que el algoritmo pierda relaciones relevantes entre las entradas y las salidas.
Este tipo de problema genera un modelo subajustado (underfitting).

## Varianza
Mide la sensibilidad con respecto a pequeñas fluctuaciones en los datos de entrenamiento. 
Una consecuencia de este problema es al alta diferencia en el desempeño del modelo frente a datos de entrenamiento y validación.
Es decir, en los datos de entrenamiento puede ser una predicción perfecta, pero en la de evaluación, si se le agrega una pequeña variación, "se bloquea" el modelo. 
Un modelo con alta varianza genera un modelo **sobreajustado** a los datos de entrenamiento, lo que produce un pobre nivel de generalización a datos no vistos. Es así como tiene un desempeño pobre en datos de validación o evaluación. 

## Bias vs Varianza
![[Pasted image 20250401102845.png]]
El límite de tolerancia lo da la aplicación. 

## Equilibrio Bias-Varianza
Un modelo optimizado será sensible a los patrones de los datos de entrenamiento, pero al mismo tiempo será capaz de generalizar a nuevos datos.
Equilibrio entre bias y varianza resulta en el menor error.
![[Pasted image 20250401103312.png]]

## Subajuste (underfitting)
Un modelo presenta subajuste cuando este produce un **alto error** en ambos conjuntos de datos, datos de entrenamiento y validación.
Usualmente la causa de este problema es la elección incorrecta del modelo de aprendizaje automático, resultando insuficiente para representar la relación existente entre los datos.
## Sobreajuste (overfitting)
Existe sobreajuste cuando los datos logran alto desempeño en el conjunto de datos de entrenamiento pero un desempeño muy bajo en los datos de evaluación o validación.
Esto se traduce en una capacidad muy débil de generalización. 

## Subajuste vs Sobreajuste
![[Pasted image 20250401103658.png]]

¿Cuáles son las consecuencias de un alto bias? ¿Cuáles son las consecuencias de tener un modelo sorbeajustado? ¿Qué consecuencias hay si los parámetros no están optimizados para el modelo? 
