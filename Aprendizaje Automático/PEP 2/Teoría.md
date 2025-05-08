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