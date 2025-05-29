# Redes neuronales
## Idea básica
El buen comportamiento debería ser premiado, y el mal comportamiento se debe castigar (o no premiar). Esto mejora el ajuste del sistema. 
Los eventos correlacionados deberían ser combinados.

## Mecanismos de entrenamiento
Modificación del comportamiento de los individuos. 
Comportamiento del instinto. El animal mal codeado no se reproduce.

## Perceptrón
Modelo matemático básico de una red neuronal artificial.

### Entradas (x)
La entrada $x_0$ = 1. La entrada x es conocida como el vector de características (feature vector).
### Pesos (w)
También es conocido como bias. Estos son los paráametros que la neurona tiene que ajustar.
### Valor de agregación (a)
La suma agregada del vector de entrada con respecto al vector de parámetros.
$a = \sum^{d}_{i=0}x_{i}\phi_{i}$  
### Valor de activación (y)
Representa la salida de la neurona. $y=f(a)$ Es un problema de clasificación binaria, f es la función sigmoidal $f(a) = \frac{1}{1+e^{-a}}$ 

### Interpretación geométrica
![[Pasted image 20250508102732.png]]
### Regla de perceptrón
Lo que queremos es identificar los valores óptimos de los pesos. Mientras más entradas se tengan, más hiperparámetros se deben ajustar.
La regla de percetrón establece que el algoritmo debería, automáticamente, aprender los pesos óptimos de los coeficientes.
Las características de entrada son entonces multiplicadas con estos pesos para determinar si una neurona funciona o no.

### Función de pérdida
Mide el error entre la predicción y el valor real. Existen diversas funciones de pérdida, las cuales dependen de la tarea en particular que se trata de resolver. 

#### MSE (Mean Squared Error)
Mide la diferencia entre la predicción y el valor real.

#### BCE 
Trata de maximizar el valor de salida cuando $y_i = 1$ y minimizarlo cuando $y_i = 0$.

#### Pérdida total
$\frac{1}{N}\sum^{N}_{i=1}L(\Phi,x_i)$

Se debe minimizar el valor de la función de pérdida.

### Entrenamiento
El proceso es iterativo hasta que se cumpla alguna condición de parada:
- Se itera por cierto número de iteraciones o pasos
- Se llega a un error o valor de pérdida mínimo (pérdida < umbral)
- No existen mayores cambios en los pesos en los últimos pasos

## Perceptrón multi-capa
Algunos conjuntos de datos no son linealmente separables.
Funciona con neuronas en forma de cascadas.
Cada salida de una capa es la entrada de la siguiente.
Cada capa tiene su propio conjunto de pesos.

El MLP extiende, de manera natural, la lógica del perceptrón, agregando los siguientes cambios:
- Combina perceptrones, organizando las neuronas por capas. Así, se tienen una o más capas ocultas que transforman la entrada para facilitar la clasificación.
- Cada neurona está dotada de una función derivable no lineal. Sigmoidal, Tangente hiperbólica, ReLU.

Mientras más capas, se soluciona el problema de la no linealidad.

Si se tienen 5 clases de salida, se necesitan 5 neuronas.

## Términos nuevos
### Lote (Batch)
Cuando el conjunto de datos de entrenamiento es muy grande, entrenar usando todos los datos para estimar el cambio de los pesos es ineficiente. Se puede dividir el conjunto en lotes de cierto tamaño, y estimar el cambio de los parámetros usando la información de cada lote. Se debe hacer de forma aleatoria.
### Iteración (Step)
Cada vez que pasa un lote por la red y se actualizan los parámetros se conoce como iteración.
### Época (epoch)
Paso completo de todo el conjunto de datos por la red. Una época es igual al número de iteraciones necesarias para completaar el tamaño del conjunto de entrenamiento.

# Gradiente descendiente

## Perceptrón Multicapa
Combina perceptrones, organizando las neuronas en capas. Por ende, una o más capas ocultas transforman la entrada para facilitar la clasificación.
Cada neurona está equipada con una función no lineal diferencial.

Las funciones de activación pueden ser todas distintas. 
El peso del $x_0$ (bias) es el que se tiene que ajustar.

¿En qué caso la cantidad de neuronas es distinta a la cantidad de clases?

### Forward
Es de atrás hacia adelante, al final se deben ajustar los parámetros.

### One-Hot Coding
Técnica de codificación para convertir variables categóricas en un formato que pueda ser comprendido por los modelos.

### CrossEntropy Loss
Función de pérdida utilizada comúnmente en problemas de clasificación, especialmente de multiclase y binaria.

$$L(y,\hat{y})=-\sum_{i=1}^{C}y_ilog(\hat{y_i})$$

- C: Número de clases.
- $y_i$: Es el valor real.
- $\hat{y_i}$: Probabilidad predicha para la clase i.

## Conceptos importantes
### Batch (Lote)
Este es un hiperparámetro, por lo que se debe decidir qué valor debe tener antes de entrenar el modelo. 
Es un subconjunto completo de datos de entrenamiento que se utiliza en una única iteración del proceso de entrenamiento. 

### Iteration (Iteración)
Una única actualización de los parámetros del modelo durante el proceso de entrenamiento. 
Ocurre cuando pasa un lote completo , los parámetros (pesos) son actualizadas cada vez que pasa un batch.

### Epoch (Época)
Ocurre cuando pasan todos los batch. 

## Gradiente descendente
¿Cómo actualizo los pesos? ¿Qué tanto nos vamos acercando a los mínimos locales (y ojalá globales)? ¿Cómo saber qué hemos llegado a los valores óptimos? ¿Cuál función nos dice que tanto nos estamos acercando a los valores óptimos? La función de pérdida.
Algoritmo de optimización para minimizar una función de pérdida. La idea es ajustar los parámetros del modelo (pesos) de manera que la función de pérdida se haga lo más pequeña posible. 

¿Cómo podemos elegir el tamaño de la iteración? 
Si la y es muy pequeña, nunca va a llegar al valor porque se va haciendo cada vez más pequeño (converge).
Si la y es muy grande, nunca va a llegar porque se pasa mucho.

### Gradiente descendente estocástico
Variante del algoritmo de gradiente descendente. En lugar de calcular el gradiente de la función utilizando todo el conjunto de datos, SGD utiliza un solo ejemplo de entrenamiento en cada iteración. Se hace esto hasta que converja el modelo. 

¿Cuáles son las 3 formas de detener el entrenamiento?
- Cuando la función de pérdida es menor que un umbral definido.
- Se cumplen la cantidad de épocas.
- La diferencia entre un entrenamiento y otro es mínima.

¿Qué es el momentum?
Técnica para acelerar la convergencia y mejorar la estabilidad del proceso de entrenamiento, especialmente en SGD.
Los parámetros del modelo se actualizan en función del gradiente de la función de pérdida con respecto a los parámetros en la iteración actual. Pero las actualizaciones pueden ser irregulares debido al ruido o fluctuaciones en las estimaciones del gradiente. 

¿Qué es AdaGrad? ¿Qué es RMSProp? ¿Qué es Adam?
¿Qué es early stopping?

### Normalización
Proceso de escalar los valores de las características de los datoss que todos estén en una escala comparable. Los modelos a menudo funcionan mejor cuando las características tienen escalas similares, evitando que una característica domine sobre las demás debido a su mayor magnitud. 

### Backpropagation
Algoritmo para entrenar redes neuronales. Método de optimización basado en la técnica de gradiente descendente que permite ajustar los pesos de una red neuronal para minimizar el error en las predicciones.

El error que se encuentra al final, se propaga hacia atrás. Para cada capa, se calcula cómo cambia el error con respecto a cada peso y se ajusta el peso de acuerdo con este cambio. 

### Vanishing gradient
Problema que ocurre durante el entrenamiento. Este problema afecta el proceso de backpropagation y dificulta que las redes neuronales aprendan de manera efectiva.
Durante backpropagation, los gradientes de la función de pérdida con respecto a los pesos se calculan y se retropagan a través de las capas de la red. Si estos gradientes son demasiado pequeños (tienden a acercarse a 0), los pesos en las capas anteriores (más cercanas a la entrada) reciben actualizacines muy pequeñas, lo que significa que el aprendizaje se detiene o se hace muy lento en esas capas.

# Aprendizaje profundo
Tiene 3 componentes clave
- **Se tiene una composición jerárquica**
	Existirán transformaciones en cascadas, distintos niveles de representación.
- **Tiene un aprendizaje end-to-end**
	Todo se aprende, se aprende a extraer características.
- **Representaciones distribuidas**
	Como se tienen muchas neuronas, se puede sacar provecho de ellas. Ninguna neurona por sí sola "soluciona" todo, los grupos de neuronas trabajan juntas.

¿qué problema quiero resolver con el paper? este es el modelo, estos son los datos, estas son las métricas.
Esto debe estar en la presentación