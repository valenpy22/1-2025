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

## Preguntas por responder para la prueba: Importante
¿Cuáles son las consecuencias de un alto bias? ¿Cuáles son las consecuencias de tener un modelo sorbeajustado? ¿Qué consecuencias hay si los parámetros no están optimizados para el modelo? 

# Clase 6
## Matriz de confusión
![[Pasted image 20250408100804.png]]

- Error rate = (FN+FP)/N
- Recall = TP / (TP+FN)
- Precision = TP/(TP+FP)
- Specificity = TN/(TN+FP)
- False alarm rate = FP/(FP+TN) = 1 - Specificity

## Curva ROC

## Evaluación de modelos
### De clasificación
- **Test binomial**: Cuando tenemos un solo conjunto de entrenamiento y un solo conjunto de evaluación.
- **Test normal aproximado**: Se trabaja con la mediana y varianza.
- **T-test**: Varios conjuntos de entrenamiento y de evaluación.
### Comparación de modelos de clasificación
Quiero ver solamente MI modelo.
- **Test McNemar**: Solo se tiene un conjunto de datos de entrenamiento y evaluación.
- **T-test pareado con k-cross validation**: Varios conjuntos de entrenamiento comparados de par en par. Queremos probar que un modelo es mejor que otro independiente de la distribución.
- **Análisis de varianza (ANOVA)**: Cuando no tenemos dos casos que comparar, sino que 3 o más. Compara todos estos modelos. Nos dice las diferencias significativas, si las hay se debe hacer de 2 en 2 la comparación para saber cuál es el mejor modelo. 

### Comparación con múltiples datasets
- **Comparar dos algoritmos**: Test de signo
- **Comparar múltiples algoritmos**: Test de Kruskal-Wallis

# Clase 7
## Ensemble Learning
Combina múltiples clasificadoress (usualmente con fortalezas distintas) para construir un clasificador más grande y mejor.

Cuanado hablamos de un aprendizaje ensamblado, tendremos muchos clasificadores. Necesitamos una estrategia de todos los modelos para que solamente salga un resultado, es decir, juntar las respuestas para generar una respuesta final.

![[Pasted image 20250410100232.png]]

## No Free Lunch Theorem
No hay ningún algoritmo que sea siempre preciso.

Generar un grupo de "aprendedores" base los cuales, al ser combinados, tienen una precisión más alta.

Los diferentes agentes usan diferentes:
- Algoritmos
- Hiperparámetros
- Representaciones (Modelos)
- Conjuntos de entrenamiento
- Subproblemas

Un ejemplo, es cuando se hace una tomografía, radiografía y una ecotomografía sobre un mismo torso. Se le pasan los mismos datos, pero cada modelo tiene mayor conocimiento en un tema en específico.

El usar diferentes conjuntos de entrenamiento, en promedio, son mejores que un solo clasificador.

Los clasificadores de base son débiles.

La idea es tener varios clasificadores débiles, y al momento de juntarlos, vamos a tener la garantía de que si todos tienen un rendimiento de más del 0.5, combinados serán mejor. 

¿Por qué puede ser mejor? 
Porque podemos hacer que cada uno de estos modelos debe tener un error, al juntarlos todos, el error es mucho más pequeño que la probabilidad de cualquier clasificador. 

## Estrategias de combinación
### Voting
- Unanimidad: Deben ser todos iguales. 
- Mayoría: El mayor entre dos opciones.
- Pluralidad: El mayor entre varias opciones.

Los votos pueden ser "pesados" por lo que algunos clasificadores podrían tener más influencia que otros. 

Pero... ¿cómo podemos ponderar los votos de los diferentes clasificadores?
Puede aprender la mejor forma de combinar clasificadores. Usa la salida del clasificador como características en un nuevo clasificador, aprende pesos para las características. A veces se le llama stacking. 

Puede usar las etiquetas predichas como características, o las probabilidades/puntajes predichos. 

Cuando tenemos muuuuchos clasificadores conviene hacer voto por mayoría.
### Métodos sin aprender
- Ponderar los votos según la confianza del clasificador: El puntaje o probabilidad, necesita ser el mismo tipo de clasificador en el "ensamblaje" para este ponderamiento para ser comparable entre clasificadores.
- Ponderar los votos según la precisión del clasificador: Confía más en los clasificadores precisos.

### Bagging
Entrenar distintos clasificadores con distintos conjuntos de entrenamiento. 
Este proceso es repetido K veces para crear K clasificadores.

El proceso de sampling es llamado sampling de bootstrap. Tradicionalmente es usado para construir intervalos de confianza. 

Ocupar bagging disminuye la varianza, pero no reduce el bias. Aún si los clasificadores individuales están sobreajustados, tienden a estar sobreajustados en diferentes maneras, entonces al final el ensamble reduce el sobreajuste. 
Si los clasificadores individuales están subajustados debido al mismo bias, el ensamble también será subajustado. 
### Feature Bagging
Otra versión de baggin es samplear características de forma aleatoria (crear diferentes clasificadores en diferentes versiones del conjunto de características).
Es decir, escojo ciertas características al azar para que las ocupe un clasificador. 

## Boosting
En vez de entrenar múltiples clasificadores de forma independiente, boosting funciona de forma iterativa. 
En cada iteración, un nuevo clasificador es entrenado para intentar clasificar correctamente las instancias que el anterior clasificador erró.
El nuevo clasificador puede que ahora tenga malo algunas instancias que el anterior clasificador calificó como correctas.
La meta aquí es hacer que los clasificadores se comporten mejor en diferentes instancias.

Usualmente los clasificadores en boosting son débiles, es decir, clasificadores que son ligeramente mejor que "tirar la moneda".

Un clasificador débil es un "Decision stump", un árbol de decisión con solamente un nodo.

#### ¿Por qué débiles en vez de fuertes?
Principalmente por la eficiencia, boosting muestra que los clasificadores débiles son buenos, sin la necesidad de modelos grandes.
Los clasificadores débiles también son más diversos, mejor para el ensamblaje.

Se les pone un peso a los "datos malos" cuando pasa al siguiente clasificador, forzando a aprender los datos malos. El más potente es el clasificador de la última iteración.

### AdaBoost
Es un algoritmo de Boosting común.
Usa todos los datos de entrenamiento en cada iteración, pero pesa las isntancias de entrenamiento de forma distinta en cada iteración, así el clasificador está "concetrado" en priorizar ciertas instancias como correctas sobre otros. 

# Clase 8
## Modelos monolíticos vs embedidos
Se tienen 6 empresas que en el pasado han predecido correctamente:
- 70%
- 75%
- 70%
- 60%
- 75%
- 65%
De las veces. 

Dado el gran espectro de posibilidades, se puede combinar toda la información y hacer una decisión informada.
Asumiendo que los 6 expertos verifican que es una buena decisión (asumiendo que son independientes uno del otro), se obtiene una tasa de precisión combinada de 
= 1 - (30% x 25% x 30% x 40% x 25% x 35%)
= 1 - 0.07875 
= 99.92125%

Si combinamos la opinión de varios expertos, podemos obtener un resultado muy potente. 

## Ensamblado de modelos
Combinación de conjuntos de modelos diversos, individuales y sencillos, ayudando que el modelo predictivo sea más potente.
Da igual la cantidad de datos.

### Preguntas importantes dadas por la profesora
- ¿Cuándo sería ideal ocupar un ensamblaje de modelos? 
- ¿Cuándo no ocupar un monolítico?
- ¿Qué tiene que pasar con el otro clasificador para decir "no voy por aquí"?
Cuando apesar de entrenar y entrenar, optimizar los hiperparámetros y darle más datos, el error sigue siendo alto. 
Si no funciona con clustering, voy a ocupar otro modelo. Y luego, otro modelo, y otro modelo... O haceer combinaciones de modelos. 

![[Pasted image 20250415101003.png]]

## Ensamblaje
- Usar múltiples algoritmos de aprendizaje
- Combinar las decisiones
- Puede ser más preciso que los clasificadores individuales
- Generar un grupo de clasificadores simples
- Aprendedores diferentes usan diferentes: algoritmos, hiperparámetros, representaciónes de los datos (ej: dar 5 características) y conjuntos de entrenamiento.

Por ejemplo, si se decide ocupar diferentes representaciones de los datos, se pueden tomar las 20 características y se debe justificar la separación en grupos (por color, por tamaño, por forma). Puedo formar un clasificador pequeñito que solo sepa si una figura es una elipse.

### Ensemble Creation Approaches
- Voto sin ponderación
- Voto con ponderación
- Stacking

## Bagging vs Boosting
![[Pasted image 20250415101843.png]]

De acuerdo como funcione ese modelo, se le asignan pesos a los datos. Mientras más avance secuencialmente, los datos en los que mayor error haya, más peso se le asigna, es decir, más importancia.

## AdaBoost
Se van a tener m datos de entrenamiento, las x son los datos y las "*y*" son las etiquetas.
La distirbución va cambiando después de cada iteración.
Cuando comienza, la importancia en el tiempo 1, todos los datos tendrán la misma importancia.

La T son clasificadores binarios, que clasificará en -1 o +1.
El clasificador h se entrena con los datos dados con importancia inicial.
Después, se calcula el error. Es decir, el h(x) != y, se multiplica por el peso del dato y se hace una sumatoria de todos estos errores.
Se escoge el alpha para saber la certeza del clasificador t. (Qué tan bueno es mi clasificador t).
Luego, para cada dato se le calcula su peso nuevo en la siguiente iteración. 

Luego de todas las iteraciones (H es el ensamble), se debe calcular una sumatoria ponderada de cada clasificador. Es decir, para cada clasificador, se multiplica por alfa y se suma todo esto. 

- Requiere de clasificadores débiles.
- Mientras más pequeño el error, mayor es el valor de alfa. Es decir, mientras más chico sea el error, más importancia se le dará a ese clasificador ya que responde bien. O al contrario, si aumenta el error, se le dará menor importancia, al responder mal.
- Se debe entrenar al principio con cosas más fáciles para luego pasarle los ejemplos más difíciles.
- Alfa es la importancia que se le da al modelo dependiendo de su error.
- Se siguen manteniendo los mismos datos, solo cambian sus pesos.

¿Cuándo ocupar Boosting?
Cuando nuestro modelo tiene overfitting. 

## Cascada
Hay casos donde el modelo puede ser super potente, pero no es capaz de resolver problemas muy específicos. 
Consiste en hacer una cascada de clasificadores, asociados a una confianza w.

![[Pasted image 20250415103904.png]]

Se definen diferentes umbrales $\theta$. Si es mayor que el umbral, se considera ese modelo. Si no, se continua. 
Con esto se generan "reglas".

## Stacking
Algoritmo de aprendizaje automático ensamblado. 
Se trata de combinar las predicciones de mútliples modelos de aprendizaje automático del mismo conjunto de datos, como bagging y boosting. 

Es decir, para la salida se define otro modelo de predicciones, en vez de votos ponderados.
Luego, se tiene otro nivel que aprende a predecir la salida de un ensamble en base de clasificadores base. 

### Nivel 0 (Modelo base)
Se ajustan a los datos de entrenamientos.

### Nivel 1 (Modelo meta)
Modelo que aprende a cćomo es mejor combinar las predicciones de los modelos base. 

Ajusta sus parámetros en base a las predicciones de los modelos simples. 

## Combinación de diferentes fuentes
- Integración temprana: Se ocupan todas las características y datos para entrenar un modelo. Mezclo todo.
- Integración tardía: Se les dan datos distintos a los modelos. Los clasificadores están separados. Se combinan datos finales.
- Integración intermedia: Se le pueden dar datos combinados, se le da el mismo clasificador pero con distintos hiperparámetros. 

## Ensamble
Es importante:
- Seleccionar los subconjuntos: Cómo separar características de los datos, tener en cuenta sesgos
- Entrenamiento de metaclasificadores: Ver clasificadores correlacionados, extraer nuevas combinaciones de los que no están correlacionados. 

# Clase 9
## SVM
- Support Vector Machine. Es un algoritmo de aprendizaje automático supervisado que puede ser usado para desafíos de clasificación o regresión.
- En este algoritmo, se grafica cada ítem de dato como un punto en un espacio n-dimensional (donde n es el número de características que se tienen) con el valor de cada característica siendo el valor de una coordenada en particular.
- Entonces, se realiza una clasificación encontrando el hiperplano que diferencie las dos clases de gran manera. Es decir, por default es un clasificador binario.
- Puede manejar fácilmente variables continuas y categóricas.
- SVM construye un hiperplano en un espacio multidimensional para separar diferentes clases. Genera un hiperplano óptimo de una manera iterativa, el cuál es usado para minimizar un error.
- La idea central de SVM es encontrar un hiperplano máximo marginal (MMH) que mejor divida el conjunto de datos en clases.

## Vectores de decisión o de soporte
- Son aquellos datos que están muy cerca de la otra clase. 
- Trata de maximizar el margen que hay desde el hiperplano a las clases que hay.

![[Pasted image 20250422101251.png]]

## Definiciones
### Vectores de soporte
Son puntos de datos, los cuales son los que están más cerca al hiperplano. Estos puntos definirán la mejor línea separadora para calcular los margenes. Estos puntos son más relevantes para la construcción del clasificador.

### Hiperplano
Plano de decisión que separa entre un conjunto de objetos que tienen diferentes clases.

### Margen
Es un espacio entre dos líneas de los vectores de soporte.
Es calculado como la distancia perpendicular desde un vector de soporte al hiperplano.
Si el margen es más grande entre las clases, entonces es considerado un buen margen. Si es pequeño, es un mal margen porque se puede confundir entre ambas clases.

## ¿Cómo funciona SVM?
El objetivo principal es segregan el conjunto de datos dado en la mejor manera posible.
El objetivo es seleccionar un hiperplano con el mayor margen posible entre los vectores de soporte. Lo hace siguiendo los siguientes pasos:
- Genera hiperplanos los cuales segregan las clases en la mejor manera.
- Selecciona el hiperplano correcto con la máxima segregación desde los puntos de datos.

### Tip
Se define una mejor clasificación cuando el margen es mayor.

## ¿Cuándo SVM no funciona?
### Clases no separables linealmente
Cuando tenemos clases no separables linealmente. Es decir, tanto de la clase positiva como de la negativa están mezclados, sin definirse una separación lineal o aparente. 

En este caso, se debe minimizar la sumatoria de los errores generados y multiplicarlo por C. El valor de C depende de qué tan estricto se quiere ser con respecto a la clasificación.

### Planos no separables linealmente
- Se deben separar por dimensiones, llamado Kernel Trick. 

![[Pasted image 20250422103551.png]]

El algoritmo SVM es implementado usando un kernel.

## Tipos de kernels
- Kernel lineal
- Kernel polinomial
- Radial Basis Function Kernel
- Kernel sigmoide

### Radial Basis Function Kernel
Utiliza un parámetro gamma entre 0 y 1, usando una extrapolación de los datos originales en un espacio infinito. 

## SVM Multi-clase
### One vs One
Sean Q clases, se requiere construir tantos modelos svm como pares existan. 
Cada SVM vota por una clase. La clase se determina como aquella con máximo score agregado. 

### One vs All
Sean Q clases, se requiere construir Q modelos.
La clase se determina como aquella con máximo score. Se van cambiando la clase de cada uno para volverlo a un problema binario. 

Para el laboratorio debemos hacer un SVM multi-clase. Quick Draw dataset. 
Informe de 4 páginas, vale el 60%. El 40% es el código.

## Análisis crítico
¿Cómo afecta el valor de C en el entrenamiento?
- C muy chico (ej C=0.0001)
- C "normal" (ej C=10)
- C muy grande (ej C=10000)
¿Cuál es la relación entre C y el sobreajuste a los datos de entrenamiento?

# Clase 10
## Árboles de decisión
Modelo jerárquico para aprendizaje supervisado en donde regiones discriminantes son identificadas en una secuencia sucesiva de divisiones. Sigue la estrategia de Divide y Conquista.
### Nodos internos
- Univariado: Usa un único atributo para cada split, puede ser numérico o discreto.
- Multivariado: Usa todos los atributos para estimar split.

### Hojas
- Clasificación: Cada hoja representa una clase.
- Regresión: Numérico; promedio, o ajuste local.

### Aprendizaje
Construcción del árbol, el cual sigue un algoritmo greedy para encontrar el mejor split recursivamente.

![[Pasted image 20250424100935.png]]

### Input
Conjunto de entrenamiento.

### Split
Si la entropía es 0, no hay incertidumbre.

## Random Forest
Método de ensamblaje específicamente diseñaado para los clasificadores de árboles de decisión.

- Ocupa Bagging (elige al azar cuáles datos se van a ocupar y puede volver a ocupar esos datos) y Random Input Vectors.
- Método de vectores aleatorios, por cada nodo, se escoge el mejor split de un ejemplo random de m atributos en vez de toods los atributos.

¿Cuántos árboles ocupar? ¿Es mejor 3, 100 o 1000?
Depende de cómo sean los datos, del problema y cuántos errores se permiten en el problema.

Idóneo para trabajar con multiclase.

Mientras más profundidad tenga el árbo, más overefitting hay. 


