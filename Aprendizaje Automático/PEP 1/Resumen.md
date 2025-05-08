# Conceptos
## Bias (Sesgo)
Diferencia entre la predicción promedio del modelo y el valor real que se quiere predecir.
Se asume una representación demasiado simple del problema, causando un subajuste o _underfitting_ , es decir, el modelo no logra capturar la complejidad de los datos.
Esto provoca altos errores tanto en entrenamiento como en validación.

### Ejemplo
Si se trata de predecir si una imagen es un gato o un perro, pero el modelo siempre dice gato para todo, esto quiere decir que tiene un alto bias. 
### Soluciones
- Usar un modelo más complejo, ya que un modelo más potente puede aprender con relaciones más profundas.
- Añadir más características relevantes, así se le da más información al para aprender.

## Varianza
Variación de las predicciones del modelo cuando se entrena con diferentes subconjuntos del conjunto de entrenamiento.
Al tener una **alta varianza**, el modelo se vuelve muy sensible a pequeñas fluctuaciones en los datos de entrenamiento, esto quiere decir que no generaliza, sino que memoriza los datos.
Esto causaa sobreajuste u *overfitting*, es decir, el modelo tiene muy buen desempeño en entrenamiento, pero muy pobre en evaluación. 

### Ejemplo
El modelo clasifica perfectamente el conjunto de datos de entrenamiento, pero cuando se le dan datos nuevos, falla estrepitosamente. 
### Soluciones
- Usar un modelo más simple, así se puede reducir la capacidad del modelo de "memorizar" ruido
- Aumentar el tamaño del conjunto de entrenamiento, así pudiendo generalizar mejor.
- Usar técnicas de ensamble como bagging, ya que al combinar varios modelos reduce el efecto de un solo modelo sobreajustado.
- Aplicar cross-validation para validar la robustez del modelo.

#### Tip
Bias alto -> Se necesita más complejidad
Varianza alta -> Se necesitan más datos o regularización

## Underfitting (Subajuste)
Ocurre cuando el modelo es tan pero tan simple que no logra aprender los patrones relevantes en los datos. Tiene un alto error en entrenamiento y validación. Es decir, no capta la idea, nene.

### Ejemplo
Usar una regresión lineal para predecir una relación claramente curva. El modelo, evidentemente, no se ajusta a los datos.

## Overfitting (Sobreajuste)
Ocurre cuando el modelo **memoriza los datos de entrenamiento**, hasta el ruido. Tiene un error bajo en el entrenamiento, pero alto en la validación.

### Ejemplo
Entrenar una red neuronal muy compleja con pocos datos -> predice bien solo esos datos, pero falla con datos nuevos.

## Matriz de confusión
Tabla que muestra los verdaderos positivos, falsos positivos, verdaderos negativos y falsos negativos que generea un modelo de clasificación.

## Precision y Recall
### Precisión
Proporción de verdaderos positivos entre todo lo que el modelo predijo como positivo.
#### Ejemplo
¿Cuántos de los que marqué como positivos eran realmente positivos?

### Sensibilidad
Proporción de verdaderos positivos entre todos los que realmente eran positivos.
#### Ejemplo
¿De todos los positivos que había, cuántos detecté?

### Un mejor ejemplo: Diagnóstico de cáncer
Imagina que eres un doctor y tienes un test para detectar cáncer. El test tiene una **sensibilidad alta**, pero baja **precisión**.

- **Resultados del test:**
    
    - El test predice 30 personas con cáncer (las marca como positivas).
        
    - De esas 30 personas, 10 realmente tienen cáncer (verdaderos positivos), y las otras 20 no tienen cáncer (falsos positivos).
        

#### **Precisión (Precision):**

- **¿Cuántas de las personas que el test marcó como positivas realmente tienen cáncer?**

    - De las 30 personas predichas como positivas, solo 10 realmente tienen cáncer.
        
    - La **precisión** sería del 33%, ya que solo un tercio de los que fueron diagnosticados como positivos realmente lo son.
        

#### **Sensibilidad (Recall):**

- **¿Cuántos de los casos reales de cáncer fueron detectados por el test?**
        
    - Supón que hay 50 personas realmente con cáncer en total, y el test detecta 10 correctamente.
        
    - La **sensibilidad** sería del 20%, ya que solo detecta el **20% de los casos reales de cáncer**.

## Hiperparámetros
Parámetros del algoritmo de aprendizaje que deben ser definidos antes de entrenar el modelo, como el número de iteraciones. Es decir, son como las reglas del juego que se deciden antes de entrenar al modelo, y no cambian mientras se entrena. 


## Cross-Validation
Técnica de evaluación en la que se divide el conjunto de datos en varios subconjuntos o folds. El modelo se entrena y valida varias veces con diferentees combinaciones de subconjuntos. Es decir, es como repartir los datos en partes para entrenar y evaluar varias veces, de forma que todas las partes, al finalizar el procedimiento, actúan tanto como datos de enetrenamiento y datos de prueba.

### Ejemplo
Si se tienen 100 datos, se puede dividir en 5 bloques. Se entrena con los primeros 3 bloques y se evalúa con el bloque restante, repitiendo este proceso hasta que cada bloque haya sido usado para evaluar el modelo.

## Ground Truth
Conjunto de datos etiquetados con la verdad absoluta, es decir, las etiquetas son 100% confiables y correctas.

## Gold-Standard
Conjunto de datos etiquetados por expertos en el área, es utilizado cuando no existe un ground truth muy claro.

### Ejemplo
En un estudio médico donde no hay consenso sobre si una radiografía tiene cáncer, varios expertos podrían etiquetar las imágenes como positivas o negativas. Este conjunto sería el **gold-standard**.

## No Free Lunch
Teorema que establece que no existe un único modelo que sea el mejor para todos los problemas. Cada modelo tiene su propio conjunto de supuestos que funcionan mejor para ciertos tipos de datos. 

## Bagging
Técnica de ensemble que entrena múltiples modelos en diferentes subconjuntos de datos (con muestreo con reemplazo) y combina sus predicciones para obtener un resultado más robusto.

## Boosting
Técnica de ensemble que entrena modelos secuencialmente, donde cada nuevo modelo intenta corregir los errores del anterior, ajustando el peso de los datos mal clasificados. Es decir, se le da más importancia a aquellos donde se equivocó el modelo.

## Ensemble Learning
Estrategia que combina varios modelos débiles para formar un modelo más fuerte y preciso. 

## Stacking
Técnica de ensemble donde las predicciones de varios modelos base se usan como entradas para un modelo final que aprenderá cómo combinarlas. Es decir, es como un supervisor que mira las respuestas de varios expertos y decide cuál es la mejor. 