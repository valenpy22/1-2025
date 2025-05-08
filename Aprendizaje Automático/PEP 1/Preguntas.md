## Basadas en lecturas
### **Aprendizaje Supervisado**:

1. **¿Cómo evaluarías el rendimiento de un modelo supervisado cuando tienes un conjunto de datos con un desbalance de clases muy grande? ¿Qué métricas utilizarías y por qué?**
    
    - **Métricas**: En un **desbalance de clases** es mejor usar métricas que no se vean afectadas por la distribución desigual, como:
        
        - **F1-score**: Es la media armónica de **precision** y **recall**, útil cuando se tiene un desbalance y se necesita balancear la precisión y la capacidad de recuperación de clases minoritarias.
            
        - **Precision y Recall**: Específicamente para la clase minoritaria, ya que te permiten ver si el modelo está clasificando correctamente los ejemplos positivos de esa clase.
            
        - **AUC-ROC**: Mide la capacidad del modelo para discriminar entre clases, útil en casos de desbalance donde el **accuracy** podría ser engañoso.
            
2. **En un problema de clasificación binaria, tienes una precisión de 95% y un recall de 40%. ¿Cómo interpretarías estos resultados y qué acciones tomarías para mejorar el rendimiento del modelo?**
    
    - **Interpretación**: El modelo es muy preciso, pero tiene un **recall bajo**, lo que indica que **no está identificando correctamente la mayoría de los casos positivos**. Esto es un **falso positivo** de alto valor.
        
    - **Acción**: Se podrían ajustar los **umbral de decisión** para priorizar la **recuperación de los positivos**, o bien usar técnicas como **under-sampling o over-sampling** para mejorar la representación de la clase minoritaria. Además, se pueden optimizar los **hiperparámetros** con técnicas como **Grid Search** para encontrar un mejor balance entre **precision** y **recall**.
        
3. **Explica el concepto de overfitting en el aprendizaje supervisado. ¿Cómo sabes si tu modelo está sobreajustado, y qué estrategias utilizarías para mitigar el sobreajuste?**
    
    - **Overfitting** ocurre cuando un modelo aprende **demasiado bien** los detalles y el ruido de los datos de entrenamiento, lo que lleva a un **bajo rendimiento** en nuevos datos.
        
    - **Detección**: Si el modelo tiene **bajo error** en los datos de entrenamiento pero **alto error** en los datos de prueba, es probable que esté sobreajustado.
        
    - **Estrategias**: Usar técnicas como **regularización** (L1, L2), **validación cruzada**, y **early stopping** para evitar que el modelo continúe aprendiendo hasta sobreajustarse.
        
4. **¿Qué es un modelo de regresión lineal y en qué situaciones sería más adecuado usarlo? ¿Qué significan los coeficientes obtenidos de un modelo de regresión lineal?**
    
    - **Modelo de regresión lineal** es un modelo que predice una **variable continua** basándose en una relación lineal entre las variables independientes (características) y la variable dependiente (objetivo).
        
    - Es adecuado cuando las variables tienen una relación lineal y no se necesita modelar interacciones complejas.
        
    - **Coeficientes**: Los coeficientes indican el **cambio esperado en la variable dependiente** por cada unidad de cambio en la variable independiente correspondiente.
        

---

### **Aprendizaje No Supervisado**:

5. **En un problema de agrupación (clustering), ¿cómo determinarías el número óptimo de clusters? ¿Qué métricas usarías y qué técnicas emplearías para evaluar la calidad de los clusters generados?**
    
    - **Métodos**:
        
        - **Método del codo**: Grafica la **suma de errores cuadrados (SSE)** contra el número de clusters y busca el "codo", donde la disminución de SSE se hace menos pronunciada.
            
        - **Silhouette Score**: Mide qué tan bien separado está un cluster respecto a los demás, donde valores cercanos a 1 indican buen clustering y valores cercanos a -1 indican mala calidad de los clusters.
            
        - **Calinski-Harabasz Index**: Evalúa la densidad y separación entre los clusters.
            
6. **¿Qué diferencia hay entre k-means y DBSCAN? ¿Cuáles son las ventajas y desventajas de cada uno y en qué tipo de problema uno podría ser más adecuado que el otro?**
    
    - **k-means** es un algoritmo que **requiere un número predefinido de clusters** (k). Funciona bien cuando los clusters son de forma **esférica** y de **tamaño similar**.
        
    - **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise) no requiere un número de clusters predefinido y puede manejar **clusters de forma arbitraria**. También puede identificar **puntos ruidosos**.
        
    - **k-means** es más rápido pero no maneja bien clusters con formas irregulares o outliers, mientras que **DBSCAN** es más flexible pero puede ser más lento en grandes conjuntos de datos.
        
7. **En un análisis de componentes principales (PCA), ¿cómo interpretarías la varianza explicada por las primeras componentes? ¿Por qué es importante analizar la varianza acumulada cuando se reduce la dimensionalidad?**
    
    - **Varianza explicada**: Las primeras componentes principales en PCA capturan la mayor **varianza** de los datos, lo que significa que contienen la mayor parte de la **información**.
        
    - **Varianza acumulada**: Es importante observar la varianza acumulada para asegurarse de que se está **conservando suficiente información** al reducir la dimensionalidad. Esto te ayuda a decidir cuántas componentes seleccionar sin perder demasiada información.
        
8. **En un conjunto de datos con altas correlaciones entre las variables, ¿cómo podrías usar PCA para mejorar el rendimiento de un modelo de aprendizaje supervisado? ¿Qué pasa si el conjunto de datos no tiene una relación lineal entre las variables?**
    
    - **PCA** ayuda a reducir la **redundancia** eliminando características correlacionadas, lo que puede mejorar el rendimiento del modelo y reducir el **ruido**.
        
    - Si el conjunto de datos no tiene una relación lineal, PCA podría no ser tan efectivo, ya que no captura relaciones no lineales. En este caso, técnicas como **UMAP** o **t-SNE** podrían ser más apropiadas.
        

### **Aprendizaje por Refuerzo**:

9. **Explica el concepto de exploración y explotación en un modelo de aprendizaje por refuerzo. ¿Cómo se balancean estos dos aspectos durante el entrenamiento de un agente?**
    
    - **Exploración** es cuando el agente prueba **acciones aleatorias** para descubrir nuevas formas de maximizar la recompensa. **Explotación** es cuando el agente selecciona las acciones que cree que le darán la **máxima recompensa** basada en su experiencia previa.
        
    - El **balance** se maneja ajustando la **tasa de exploración (epsilon)**. Un **valor alto de epsilon** fomenta la exploración, mientras que un valor bajo favorece la explotación.
        
10. **¿Qué es una función de recompensa en el contexto de aprendizaje por refuerzo? Da un ejemplo de cómo podrías definirla en un entorno de juegos, y cómo influye en las decisiones del agente.**
    

- La **función de recompensa** define el **valor numérico** que el agente recibe por realizar una acción en un estado dado. La recompensa guía el agente hacia comportamientos deseados.
    
- **Ejemplo**: En un juego de ajedrez, el agente podría recibir una **recompensa positiva** por capturar una pieza del oponente y una **negativa** por perder una pieza. El agente ajustará sus decisiones basándose en estas recompensas.
    

11. **En un agente que está aprendiendo a jugar a un juego usando Q-learning, ¿cómo se actualiza la función Q y qué rol juega la tasa de aprendizaje (learning rate) en este proceso?**
    

- **Q-learning** actualiza la **función Q** (que asigna valores a las parejas estado-acción) usando la fórmula:
    
    Q(s,a)=Q(s,a)+α(r+γmax⁡a′Q(s′,a′)−Q(s,a))Q(s, a) = Q(s, a) + \alpha \left( r + \gamma \max_{a'} Q(s', a') - Q(s, a) \right)Q(s,a)=Q(s,a)+α(r+γa′max​Q(s′,a′)−Q(s,a))
    
    donde **α** es la **tasa de aprendizaje** y **γ** es el **factor de descuento**.
    
- La **tasa de aprendizaje (α)** controla cuán rápido el agente **ajusta** su conocimiento basado en nuevas experiencias. Si α es muy alto, puede llevar a un **aprendizaje inestable**.
    


### **Modelos Lineales (ROC, AUC, cómo se grafica)**:

12. **Explica qué es la curva ROC y qué significa el AUC en el contexto de clasificación. ¿Cómo se interpreta un AUC de 0.5 versus un AUC de 0.9?**
    

- **ROC (Receiver Operating Characteristic)** es una curva que muestra la **relación entre el True Positive Rate (TPR)** y el **False Positive Rate (FPR)** a diferentes umbrales.
    
- **AUC (Área Bajo la Curva)** mide el área bajo la curva ROC y representa la **capacidad del modelo para distinguir entre clases**. Un **AUC de 0.5** significa que el modelo no tiene capacidad de discriminación (similar a una **selección aleatoria**), mientras que un **AUC de 0.9** indica un modelo con **buena discriminación**.

13. **¿Qué es el coeficiente de determinación (R²) en una regresión lineal y cómo lo interpretarías en el contexto de un modelo de predicción? ¿Qué significa un R² cercano a 0 y uno cercano a 1?**
    

- **R²** mide la proporción de la **varianza** en la variable dependiente que es explicada por el modelo. Un **R² cercano a 1** indica que el modelo **explica casi toda la variabilidad** de los datos, mientras que un **R² cercano a 0** indica que el modelo tiene **poca capacidad de explicación**.
    

---

### **Diferencias entre PCA y UMAP**:

14. **¿Cuáles son las diferencias fundamentales entre PCA y UMAP en términos de reducción de dimensionalidad? ¿Cuándo usarías uno sobre el otro y por qué?**
    

- **PCA** es una técnica **lineal** que busca encontrar las **direcciones principales** de los datos. Es más eficiente computacionalmente y útil cuando las relaciones entre características son **lineales**.
    
- **UMAP** es **no lineal** y más flexible, preserva tanto la **estructura global** como las **relaciones locales** entre puntos. **UMAP** es más adecuado cuando los datos tienen una **estructura no lineal**.
    

15. **¿Qué tipo de relaciones en los datos son capturadas mejor por PCA en comparación con UMAP? ¿Cuál de las dos técnicas preserva mejor la estructura global de los datos?**
    

- **PCA** captura bien las relaciones **lineales** y preserva la **estructura global** de los datos.
    
- **UMAP** es capaz de capturar **relaciones no lineales** y mantiene tanto la **estructura global** como la **local** de los datos, lo que lo hace más adecuado para datos complejos.
    

16. **¿Qué ventajas tiene UMAP sobre PCA cuando se trata de reducción de dimensionalidad en datos no lineales? Explica un caso práctico en el que UMAP sería más beneficioso que PCA.**
    

- **UMAP** es especialmente útil cuando los datos tienen **estructuras no lineales**. Mientras que **PCA** podría perder relaciones importantes en estos casos, **UMAP** puede preservar la **estructura local** y **global**.
    
- **Caso práctico**: En un conjunto de datos con imágenes o texto, donde las relaciones entre las características no son lineales, **UMAP** sería más efectivo que **PCA** para preservar patrones complejos.


## Estilo PEP
### **1.**

Un modelo SVM fue entrenado con datos balanceados. En evaluación, obtuvo una **precisión de 98%** pero un **recall de 20%**.  
**¿Qué está pasando? ¿Es aceptable el rendimiento? ¿Qué acciones tomarías para mejorar el modelo, sin reentrenar desde cero?**

Ocurre que, de los que se detectaron como positivos, realmente eran positivos el 98%, siendo una muy buena métrica. Sin embargo, del total de positivos, solo se pudo identificar el 20% de los casos. No es aceptable el rendimiento, ya que se está olvidando del 80% de los casos que fueron mal diagnosticados de los positivos. Por lo tanto, sin entrenar desde 0, cambiaría los umbrales de decisión para que más ejemplos sean clasificados como positivos. Esto aumentará el recall, y se sacrificará algo de precisión, pero se puede alcanzar un equilibrio.
Además, si hay un costo mayor por los falsos negativos, priorizaría recall aunque baje un poco la precisión.

### **2.**

Tienes un modelo de clasificación multiclase con exactitud del 60%. Sin embargo, la clase minoritaria obtiene un F1-score de 0.15.  
**¿Cómo interpretarías este resultado? ¿Qué métricas alternativas usarías y qué estrategias podrías aplicar?**

Aunque el modelo obtiene una accuracy del 60%, esta métrica puede ser **engañosa en contextos desbalanceados**. El F1-score de 0.15 en la clase minoritaria indica que el modelo tiene **problemas severos para predecir correctamente esa clase**.  
Para entender mejor este comportamiento, analizaría la matriz de confusión y métricas como **recall, precision y F1 por clase**, además de macro-average F1.  
Para mejorar, consideraría aplicar técnicas de balanceo como **ponderación de clases, aumento de datos o submuestreo**, con el objetivo de que el modelo preste más atención a las clases poco representadas.

Recordatorio:

$$F1 = 2*\frac{Precision * Recall}{Precision + Recall}$$
Supón que tienes un modelo que predice si un estudiante aprobará un ramo. En una evaluación, obtienes estos valores para la clase “Aprueba”:

- **TP = 8** (predijo aprueba, y aprobó)
- **FP = 2** (predijo aprueba, pero reprobó)
- **FN = 5** (predijo reprueba, pero aprobó)
- **TN = 10** (predijo reprueba y reprobó)

- Precisión: $$\frac{8}{8+2}=0.8$$
- Recall o Sensibilidad: $$\frac{8}{8+5}=0.615$$
- F1-score: $$2*\frac{0.8*0.615}{0.8+0.615}=0.695$$
Aunque la precisión es buena, el modelo está olvidando de muchos positivos reales (recall bajo). El F1-score da un balance, no es tan alto como la precisión, pero refleja mejor el rendimiento global para esa clase.

### **3.**

Entrenas un modelo complejo y obtienes alto rendimiento en los datos de entrenamiento, pero un rendimiento muy bajo en validación.  
**¿Qué tipo de problema estás enfrentando? ¿Cómo podrías solucionarlo sin cambiar el modelo ni los datos de evaluación?**

El modelo está sufriendo **overfitting**, lo que significa que tiene **muy buen rendimiento en entrenamiento** pero **muy bajo rendimiento en validación**, indicando **alta varianza**.  
Esto ocurre cuando el modelo **se ajusta demasiado a los datos de entrenamiento**, incluyendo el ruido.  
Como **no puedo cambiar el modelo ni los datos de evaluación**, una opción viable es aplicar **k-fold cross-validation**, para validar el modelo con distintas particiones y mejorar la estimación del error real.  
También puedo aplicar **regularización** (si el modelo lo permite) o limitar su complejidad (por ejemplo, reducir la profundidad en árboles), todo **sin cambiar su arquitectura**, sino ajustando **sus hiperparámetros** para que generalice mejor.

### **4.**

Estás trabajando con datos de imágenes con miles de dimensiones por muestra. Tu modelo tarda mucho en entrenar y presenta overfitting.  
**¿Qué técnica aplicarías antes de entrenar nuevamente el modelo? ¿Por qué esa técnica y no otra?**

En el caso de datos de imágenes, cada imagen tiene una alta cantidad de características (cada píxel es una dimensión). Esto puede provocar **overfitting** y **alto costo computacional**, por lo que aplicaría una técnica de **reducción de dimensionalidad** como PCA o UMAP.  
Si las relaciones entre características son **lineales** y quiero una reducción rápida y directa, **PCA** es más adecuado.  
En cambio, si el patrón entre los píxeles es **no lineal o complejo**, o si me interesa **preservar la estructura local y global de los datos (por ejemplo, para clustering visual o detección de similitud)**, entonces **UMAP** sería una mejor opción.  
Además, ambas técnicas pueden mejorar la **capacidad de generalización del modelo** al eliminar ruido y redundancia en las variables.

### **5.**

Explica cómo mejorarías el rendimiento de un modelo sin cambiar su arquitectura ni el set de datos, pero sí usando una técnica de validación distinta.  
**¿Qué esperas lograr con ese cambio? ¿En qué casos sería útil esta estrategia?**

Para mejorar el rendimiento del modelo sin cambiar su arquitectura ni modificar el conjunto de datos, aplicaría **validación cruzada (k-fold cross-validation)**.  
Esta técnica consiste en dividir el conjunto de datos en _k_ particiones. En cada iteración, una partición actúa como conjunto de validación y las demás como entrenamiento, rotando hasta que cada partición haya sido usada como validación.  
Esto permite que **todos los datos participen como entrenamiento y como validación**, proporcionando una **estimación más robusta y menos dependiente del azar**.  
Es especialmente útil cuando **hay pocos datos**, ya que evita perder información útil en un solo split. Además, ayuda a detectar mejor si el modelo está **sobreajustando o subajustando**.

### **6.**

Estás usando una red neuronal con alto error en entrenamiento y validación. Ajustaste hiperparámetros, pero el problema persiste.  
**¿Qué indica esto sobre el modelo? ¿Qué estrategias podrías seguir para resolverlo?**

Si el modelo tiene un **alto error tanto en entrenamiento como en validación**, y ajustar los hiperparámetros no mejora su rendimiento, esto indica un problema de **underfitting**.  
El modelo **no tiene suficiente capacidad** para aprender los patrones en los datos, o **su inductive bias es demasiado restrictivo**.  
Para resolverlo, una estrategia sería **aumentar la complejidad del modelo** (por ejemplo, usar más capas o nodos en una red, o mayor profundidad en un árbol), o **cambiar el tipo de modelo** por uno más flexible. 

Si el modelo no puede cambiarse, también podría ser útil aplicar **ingeniería de características**, por ejemplo:

- Crear nuevas variables derivadas.
- Usar una transformación no lineal sobre los datos.
- Usar kernels no lineales (si es un SVM).  
    Finalmente, si el modelo lo permite, podría aplicarse un enfoque como **boosting** para aumentar la capacidad efectiva del conjunto, pero solo si cambiar la estructura está permitido.

### **7.**

Te entregan el output de un clasificador con 100 árboles entrenado por bagging, y otro clasificador boosting con 10 árboles secuenciales.  
**Ambos tienen el mismo accuracy. ¿Qué aspectos adicionales considerarías para decidir cuál usar? Justifica.**

Aunque ambos clasificadores tienen la misma accuracy, eso no basta para decidir cuál usar.  
Primero consideraría la **complejidad del problema**: si se trata de un problema difícil y no lineal, **boosting** puede ser más adecuado por su capacidad de reducir el **bias** al enfocarse en errores difíciles.  
Sin embargo, si los datos son **ruidosos** o tengo un riesgo de **overfitting**, preferiría **bagging** (como Random Forest), ya que es más **robusto**, al reducir la **varianza** mediante el entrenamiento en subconjuntos aleatorios.  
También analizaría otras métricas (como F1-score, recall o AUC) y evaluaría la **estabilidad del modelo** en validación cruzada.  
Finalmente, si el rendimiento es similar, priorizaría el modelo **más interpretable, más eficiente o más fácil de mantener**.


### **8.**

Un modelo obtiene una curva ROC con AUC de 0.95, pero en producción falla con frecuencia al clasificar correctamente una clase importante.  
**¿Cómo puede suceder esto? ¿Qué métrica adicional usarías para estudiar el problema? ¿Cómo podrías mitigarlo?**

Aunque el **AUC de 0.95** es excelente en términos generales, no garantiza que el modelo sea adecuado para **todas las clases**. Un **AUC alto** refleja que el modelo tiene una buena capacidad para **separar las clases en general**, pero puede estar **fallando en una clase minoritaria o importante**.  
Esto es común en casos de **desbalance de clases**, donde la clase menos representada no está siendo correctamente identificada, a pesar de que el modelo **generalmente clasifica bien**.  
Una métrica más relevante sería la **curva de precisión-recall**, ya que mide específicamente cómo el modelo está manejando la **clase importante**.  
Además, ajustaría el **umbral de decisión** para ser más sensible a la clase minoritaria, **ponderaría las clases** durante el entrenamiento o incluso intentaría aumentar los datos de esa clase importante. También podría usar **F1-score** para equilibrar precisión y recall en situaciones desbalanceadas.


### **9**.

Estás aplicando PCA y reduces de 100 a 10 dimensiones. El modelo mejora velocidad, pero pierde rendimiento.  
**¿Qué significa esto respecto a las componentes elegidas? ¿Qué harías para conservar más información útil?**

Al usar **PCA**, es posible que la **reducción de dimensionalidad** haga que algunas **componentes principales no representen toda la variabilidad** de los datos, resultando en una **pérdida de información importante**.  
Para mitigar esto, **aumentaría el número de componentes** seleccionadas, asegurando que se conserve al menos un **70% de la varianza** de los datos originales. Esto se puede lograr calculando la **varianza explicada** por cada componente y estableciendo un umbral.  
Además, podría graficar la **varianza acumulada** para determinar el número óptimo de componentes, usando el enfoque del **codo**.  
Si la pérdida de información sigue siendo significativa, podría considerar **alternativas como UMAP** para capturar relaciones no lineales entre los datos.

### **10.**

Explica por qué una mala elección del parámetro `C` en un modelo SVM puede llevar a overfitting o underfitting.  
**¿Qué pasos seguirías para elegir un valor de C adecuado? ¿Qué señales buscarías en el rendimiento del modelo?**

El valor de **C** en un modelo SVM controla el balance entre **margen** y **errores de clasificación**.

- Un **valor bajo de C** permite más errores (máximo margen, pero tolera mal las clasificaciones incorrectas), lo que puede llevar a **underfitting**, ya que el modelo no se ajusta bien a los datos.
    
- Un **valor alto de C** busca minimizar los errores, **reducir el margen** y ajustarse más a los datos de entrenamiento, lo que puede causar **overfitting** si el modelo se adapta demasiado a los ruidos o fluctuaciones en los datos de entrenamiento.
    

Para encontrar un valor adecuado de C, usaría **grid search** con validación cruzada, probando una **gama de valores** (por ejemplo, de 0.001 a 1000). Esto me permite **evaluar el rendimiento** del modelo para cada valor de C y **elegir el que maximice el rendimiento general** sin sobreajustar.  
Además de **accuracy**, consideraría otras métricas como **F1-score** o **AUC** para obtener una visión más completa del rendimiento del modelo, especialmente en problemas desbalanceados.


### **11.**

Te piden implementar un sistema de detección de fallas en tiempo real con datos secuenciales.  
**¿Por qué un ensamblaje tipo boosting puede ser mejor que bagging en este caso? ¿Qué riesgos implica usar un modelo demasiado ajustado a los errores anteriores?**

En un sistema de **detección de fallas en tiempo real**, un modelo tipo **boosting** sería más adecuado que **bagging** por varias razones:
- **Boosting** entrena los modelos **secuencialmente**, penalizando los errores cometidos en iteraciones anteriores. Esto es esencial para un sistema en tiempo real donde **aprender de las fallas previas** es crucial para evitar que se repitan.
- Además, **boosting** puede enfocarse en los casos más difíciles, donde el modelo comete errores, lo cual es importante en sistemas críticos como la detección de fallas, donde incluso un pequeño error puede tener grandes consecuencias.     
- **Bagging**, por otro lado, entrena modelos de manera **paralela**, y aunque es muy útil para reducir la varianza y mejorar la estabilidad, **no se enfoca en corregir errores pasados**, lo que hace que sea menos eficiente en un escenario donde se necesita **una constante mejora del rendimiento** en función de los errores cometidos.

**Riesgos de un modelo ajustado demasiado a los errores anteriores (overfitting):**
- **Boosting** puede llevar al **overfitting** si el modelo se ajusta demasiado a los datos de entrenamiento y empieza a aprender **ruido o fluctuaciones aleatorias**. Esto se puede mitigar utilizando técnicas como **early stopping** (detener el entrenamiento antes de que el modelo se ajuste demasiado) o limitando la **profundidad de los árboles** en cada iteración.

### **12.**

Un modelo de **Random Forest** ha sido entrenado y produce buenos resultados en el conjunto de entrenamiento, pero el rendimiento en el conjunto de validación es bajo.  
**¿Qué podría estar pasando y cómo lo resolverías?** ¿Qué técnicas de ajuste y optimización propondrías para mejorar la generalización del modelo?

El **overfitting** ocurre cuando el modelo se ajusta demasiado a los datos de entrenamiento, lo que lleva a un **bajo rendimiento en los datos de validación**. En este caso, ya estoy utilizando **Random Forest**, que es un modelo basado en **bagging**, lo cual ayuda a **reducir la varianza** y mejora la **generalización**. Random Forest entrena múltiples árboles de decisión en subconjuntos aleatorios de los datos y características, y promedia sus predicciones, lo que **diversifica el modelo** y evita el sobreajuste.  
Para mejorar aún más el rendimiento, realizaría un **ajuste de hiperparámetros** usando **grid search** con **validación cruzada**, lo que me permitiría encontrar los valores óptimos para los parámetros del modelo y asegurarme de que generaliza correctamente.  
Adicionalmente, podría considerar técnicas como **early stopping** o **regularización** si el modelo lo permite, y también ajustar la **profundidad máxima de los árboles** para evitar que los árboles se ajusten demasiado a los datos de entrenamiento.

### **13.**

En un problema de clasificación con un conjunto de datos muy desbalanceado, estás considerando usar **SVM**.  
**¿Cuándo no sería adecuado utilizar SVM? ¿Qué alternativas podrías considerar y por qué?**

**SVM** no es adecuado cuando las clases no son **linealmente separables**. Aunque **SVM** puede usar kernels (como el **RBF kernel**) para transformar los datos en un espacio de mayor dimensión donde puedan separarse linealmente, si las relaciones entre las clases son **demasiado complejas o hay mucho ruido en los datos**, **SVM** puede seguir teniendo un **rendimiento limitado**.

Alternativas que podrías considerar incluyen:

- **Árboles de decisión**, que son **excelentes para problemas no lineales** y pueden manejar datos con **relaciones complejas** sin requerir una transformación previa.
- **Redes neuronales**, que pueden modelar **relaciones muy complejas**, pero requieren **más datos** y **potencia computacional**.
- **k-NN (K-Nearest Neighbors)**, que también maneja **relaciones no lineales** sin necesidad de una separación explícita.
- **Random Forest**, que es robusto frente al **ruido** y puede capturar **relaciones no lineales**, mejorando la **generalización** frente a **SVM**.

### **14.**

Estás trabajando con un conjunto de datos de imágenes y decides usar **PCA** para reducción de dimensionalidad antes de entrenar un modelo.  
**¿Cómo sabrías si PCA está afectando negativamente el rendimiento del modelo? ¿Qué métrica usarías para evaluar su impacto y cómo podrías mejorar la estrategia de reducción de dimensionalidad?**

Para evaluar si **PCA** está afectando negativamente el rendimiento del modelo, entrenaría primero el modelo **sin reducción de dimensionalidad** y luego **con PCA**. Esto me permitirá **comparar directamente** los resultados y ver si el modelo mejora o empeora con la reducción de características.

Usaría **accuracy** para evaluar el rendimiento, pero también podría usar otras métricas como **F1-score** o **recall** si el conjunto de datos es desbalanceado o si el **accuracy** no refleja correctamente el rendimiento del modelo.

Si al usar PCA, el **accuracy disminuye considerablemente**, sería un indicio de que **estoy perdiendo información importante** durante la reducción. Para determinar cuántas componentes elegir, examinaría la **varianza explicada** por cada componente y seleccionaría el número que conserve al menos el **70%** de la varianza.

**PCA** es especialmente útil cuando las **relaciones entre los datos son lineales**, como en el caso de **imágenes de baja resolución** o cuando los **píxeles son lineales entre sí**. Sin embargo, si las **imágenes son complejas** y contienen **relaciones no lineales**, podría ser más adecuado usar **UMAP**, que es capaz de capturar **relaciones no lineales** entre los datos y preservar tanto la **estructura local como global**.

En resumen, la elección de la técnica de reducción de dimensionalidad depende de **la complejidad de los datos** y de **cuántas características tienen**. Si las relaciones son lineales, PCA es adecuado, pero si son no lineales, **UMAP** es una opción más efectiva.

### **15.**

En un problema de clasificación multiclase con **SVM**.  
**¿Cuál es la diferencia entre el enfoque **One vs One** y **One vs All** en SVM para clasificación multiclase? ¿Cuáles son las ventajas y desventajas de cada uno?**

**One vs One (OvO)** y **One vs All (OvA)** son dos enfoques para manejar clasificación multiclase en **SVM**:

- **One vs One** crea un **modelo binario** para cada **par de clases**. Si hay **K clases**, se entrenan **K(K-1)/2 modelos**. En cada modelo, se compara solo entre dos clases. Al final, el modelo con **más votos** de todos los modelos determina la clase final.
- **One vs All**, por otro lado, convierte el problema multiclase en **K problemas binarios**, donde cada modelo se entrena para distinguir **una clase específica** contra **todas las demás clases**. Gana el modelo que mayor probabilidad tenga. 

**Ventajas**:

- **One vs One**: Puede ser más preciso en ciertos casos porque cada modelo solo tiene que diferenciar entre dos clases, lo que **simplifica** la tarea.
- **One vs All**: Más **eficiente computacionalmente** porque solo requiere **K modelos** en lugar de **K(K-1)/2**.

**Desventajas**:

- **One vs One**: El número de modelos aumenta **cuadráticamente**, lo que puede hacer que el proceso sea **más lento** en comparación con **One vs All**, especialmente con muchas clases.
- **One vs All**: Aunque es más rápido, puede **sufrir de imprecisiones** si las clases están **muy solapadas**, ya que un modelo podría **confundir una clase con todas las demás**.

En resumen, la elección depende del **número de clases** y la **eficiencia computacional** requerida. **One vs One** es preferible si la precisión es más importante que la eficiencia computacional, mientras que **One vs All** es más adecuado para **grandes conjuntos de clases** cuando la eficiencia es crucial.


### **16.**

Tu modelo de clasificación está entrenado usando **árboles de decisión** y obtiene buenos resultados en el entrenamiento, pero en el conjunto de validación muestra **signos de sobreajuste**.  
**¿Cómo abordarías este problema sin cambiar la arquitectura del modelo? ¿Qué parámetros ajustarías?**

Si el modelo muestra **una gran diferencia entre el rendimiento en el conjunto de entrenamiento y el de validación**, esto indica que el modelo tiene **alta varianza** y está **sobreajustado** a los datos de entrenamiento. Para mitigar el **overfitting** y reducir la varianza, aplicaría las siguientes estrategias:

- **Bagging**, específicamente utilizando **Random Forest**, si es posible cambiar la arquitectura del modelo. Bagging entrena múltiples modelos en **subconjuntos aleatorios de los datos** y promedia sus resultados, lo que ayuda a **reducir la varianza** y mejora la **generalización**.
- **Validación cruzada** para obtener una **estimación más precisa del rendimiento** del modelo, lo que permite una evaluación más confiable y ayuda a **detectar posibles problemas de overfitting** de manera más eficaz.
    

En cuanto a los parámetros que debería ajustar para reducir la varianza:

- **Profundidad máxima del árbol**: Limitar la profundidad del árbol ayuda a evitar que el modelo se ajuste demasiado a los detalles finos de los datos.
- **Número de estimadores en Random Forest**: Un número adecuado de árboles ayuda a **balancear el rendimiento** sin sobreajustarse.
- **Mínimo de muestras por split o hoja**: Aumentar estos valores ayuda a evitar que el modelo aprenda patrones muy específicos de los datos.
- **Regularización**: Si el modelo lo permite, ajustaría la **regularización** para reducir la complejidad y mejorar la generalización.

Si el modelo es **iterativo** (como un **modelo de boosting**), aplicaría **early stopping** para detener el entrenamiento antes de que el modelo se sobreajuste.

### **17.**

En un modelo de ensamblaje, decides usar **stacking** como estrategia para mejorar el rendimiento.  
**¿Cómo funciona stacking y cuándo es preferible usarlo frente a otros métodos de ensamblaje como bagging o boosting?**

**Stacking** es una técnica de ensamblaje que utiliza múltiples modelos base para hacer predicciones y luego pasa estas predicciones a un **modelo final** que aprende a **ponderar y combinar** las salidas de los modelos base, como si fuera un **"supervisor"**. La idea es aprovechar las **diversas fortalezas** de cada modelo base para obtener una **predicción más robusta**.

**¿Cuándo es preferible usar stacking?**

- **Diversidad de modelos base**: Es útil cuando se tiene un conjunto de modelos **diversos** que pueden **aprender diferentes representaciones** de los datos. Por ejemplo, puedes combinar **SVM**, **árboles de decisión** y **k-NN** para que el modelo final aprenda a **mejorar el rendimiento global** al combinar estas predicciones.
- **Mejora tanto la varianza como el sesgo**: A diferencia de **bagging** (que reduce varianza) y **boosting** (que reduce sesgo), **stacking** puede ser útil cuando quieres reducir tanto la **varianza** como el **sesgo**, aprovechando lo mejor de ambos enfoques.
- **Mejores resultados que un solo modelo**: Si varios modelos base tienen un desempeño razonable pero no excelente, **stacking** puede mejorar el rendimiento final al **combinar** sus salidas.

**Ventajas de stacking** sobre otros métodos:

- **Mayor flexibilidad**: En **bagging** y **boosting**, todos los modelos base suelen ser del **mismo tipo**, mientras que en **stacking** puedes usar **modelos de diferentes tipos** para obtener una combinación más potente.
- **Mejor generalización**: Al permitir que el modelo final aprenda a combinar los modelos base, **stacking** puede resultar en **mejores predicciones** en casos complejos donde los modelos individuales no pueden generalizar bien por sí solos.

### **18.**

Tienes un conjunto de datos con características muy correlacionadas y decides usar **feature bagging** para reducir la redundancia de características.  
**¿Cómo implementas feature bagging y qué problemas podría resolver en comparación con el bagging tradicional?**

**Feature bagging** es una técnica de ensamblaje que se utiliza para entrenar varios modelos considerando **subconjuntos aleatorios de características** del conjunto de datos. A diferencia del **bagging tradicional**, que selecciona aleatoriamente **subconjuntos de ejemplos** (filas de datos), el **feature bagging** selecciona **características** (columnas de datos) de forma aleatoria para entrenar cada modelo base.

**Ventajas**:

- **Reducción de la correlación entre características**: Cuando algunas características están **fuertemente correlacionadas**, **feature bagging** ayuda a **diversificar** los modelos entrenados, haciendo que cada modelo se enfoque en un subconjunto diferente de características. Esto mejora la **generalización** del modelo final.
- **No reducción de datos**: A diferencia del bagging tradicional, que reduce el número de ejemplos de entrenamiento, **feature bagging** mantiene **toda la información original** de los datos, solo que distribuye las características de manera diferente entre los modelos base.

**Aplicaciones**:

- **Feature bagging** es útil especialmente en conjuntos de datos donde las características están **altamente correlacionadas**, ya que permite reducir la dependencia entre los modelos base y **mejorar la generalización**.
- **Random Forest** es un caso de **feature bagging**, ya que utiliza **subconjuntos aleatorios de características** en cada división del árbol de decisión para evitar la correlación entre los árboles y mejorar la robustez del modelo.

**Consideraciones**:

- Si las características seleccionadas no son representativas o **no capturan suficiente información**, esto puede **debilitar el modelo**. Por lo tanto, es importante asegurar que la selección aleatoria de características no **pierda información clave** para el aprendizaje.

### **19.**

Estás utilizando un modelo **SVM** con kernel lineal, pero obtienes resultados insatisfactorios. Decides probar un **kernel no lineal**.  
**¿Cuándo es necesario elegir un kernel no lineal y qué podría indicar el desempeño de un kernel lineal en el contexto de tu problema?**

Cuando las clases no son **separables linealmente**, el **kernel lineal** no será adecuado porque no podrá encontrar un **hiperplano** que divida las clases correctamente. Esto ocurre cuando las clases tienen una **relación no lineal** entre ellas, como en los casos donde las clases están separadas por **curvas** o **círculos** en lugar de líneas rectas.

En estos casos, un **kernel no lineal** es necesario. El **RBF kernel (Radial Basis Function)** es una de las opciones más populares, ya que proyecta los datos en un **espacio de mayor dimensión** donde las clases pueden separarse mediante un **hiperplano** no lineal. Esto es útil cuando las clases tienen una distribución **compleja**.

Además, el **kernel polinómico** puede ser útil cuando las relaciones entre las clases pueden describirse con un **polinomio**, aunque el **RBF kernel** suele ser más efectivo en problemas con separaciones no lineales complejas.

Si el **kernel lineal** no da buenos resultados, es probable que las clases no sean separables linealmente, y se debe considerar probar otros kernels. Se puede realizar **validación cruzada** para comparar el rendimiento de diferentes kernels y elegir el más adecuado para el conjunto de datos.

### **20.**

Estás trabajando con **cascadas de clasificadores** para la detección de objetos en imágenes.  
**¿Cómo funciona una cascada de clasificadores y cuándo es útil utilizarla en comparación con otros modelos de detección? ¿Qué desafíos podrías enfrentar?**

Una **cascada de clasificadores** es una secuencia de clasificadores, donde cada etapa evalúa si un ejemplo debe ser **descartado o pasar a la siguiente etapa**. En cada nivel, el clasificador decide rápidamente si el ejemplo es probablemente negativo (lo descarta) o si debe ser evaluado más a fondo en niveles posteriores.

Se usa principalmente en **detección de objetos**, como **caras en imágenes**. El primer clasificador es rápido y simple, y los clasificadores siguientes son más complejos y costosos, pero solo procesan los ejemplos que pasaron las etapas previas.

### **Ventajas**:

- **Rápido y eficiente**: Descarta rápidamente ejemplos negativos y procesa solo los ejemplos más relevantes.

Depende de la calidad del primer clasificador, porque si es inexacto o muy simplista, puede descartar demasiados ejemplos válidos.

### **21.**

En un problema de clasificación multiclase con **Random Forest**, el rendimiento en clases minoritarias es bajo, aunque la precisión global es alta.  
**¿Qué acciones tomarías para mejorar la detección de las clases minoritarias? ¿Qué técnicas de manejo de clases desbalanceadas aplicarías sin cambiar el modelo?**

Si el modelo muestra un **bajo rendimiento en las clases minoritarias** debido al **desbalance de clases**, se pueden aplicar las siguientes estrategias:

- **Ponderación de clases**: Asignar un **peso mayor** a las clases minoritarias durante el entrenamiento. Esto hace que el modelo preste más atención a esas clases, mejorando su capacidad de predicción. Muchos modelos como **Random Forest** o **SVM** permiten esta opción de ponderación.
- **Aumento de datos (oversampling)**: Aumentar la cantidad de ejemplos de las clases minoritarias duplicando instancias o generando nuevas instancias sintéticas usando técnicas como **SMOTE**. Esto mejora el rendimiento del modelo en las clases menos representadas.

También podría considerar el **undersampling** de las clases mayoritarias, aunque esto podría llevar a perder información importante. La clave es encontrar el balance adecuado entre el número de ejemplos de cada clase y la precisión del modelo.

### **22.**

Tienes un conjunto de datos con muchas características, pero algunas de ellas no parecen ser útiles para la predicción.  
**¿Qué técnicas de selección de características usarías para mejorar el rendimiento del modelo y evitar el sobreajuste? Explica por qué cada una es útil.**

**PCA** es una técnica eficaz para reducir la dimensionalidad de un conjunto de datos al identificar y conservar las características que **aportan la mayor varianza**. Al aplicar **PCA**, transformo las características originales en **componentes ortogonales** (independientes), manteniendo las que más información aportan y descartando las características menos relevantes.

La clave al usar **PCA** es evaluar cuánta **varianza** se conserva al reducir la cantidad de componentes. Usualmente, selecciono suficientes componentes para mantener al menos el **70%-90% de la varianza** del conjunto de datos original, lo que asegura que el modelo siga siendo informativo y preciso.

**PCA** es ideal cuando las características están **correlacionadas** entre sí, ya que al reducir la redundancia, mejora tanto el rendimiento del modelo como su **eficiencia computacional**. Sin embargo, si las relaciones entre características son **no lineales**, **PCA** podría no ser la mejor opción, y podría considerar **UMAP** o **t-SNE**.

### **23.**

En un problema de clasificación con muchas clases y un alto costo asociado a la clasificación incorrecta de una clase en particular, decides usar **boosting** para mejorar el modelo.  
**¿Cuáles son los riesgos de usar boosting en este caso y qué precauciones tomarías para evitar el sobreajuste? ¿Qué métricas adicionales deberías usar para monitorear el rendimiento de la clase importante?**

El uso de **boosting** en un problema con **muchas clases** y un **alto costo de clasificación incorrecta** para una clase en particular puede ser arriesgado debido a la posibilidad de **sobreajuste**, especialmente si el modelo comienza a dar demasiado **peso** a la clase importante. Para evitar el sobreajuste, es fundamental usar **regularización**, **early stopping** y **validación cruzada**. Además, se deben ajustar los **hiperparámetros** del modelo para controlar su complejidad.

Para monitorear el rendimiento de la clase importante, además de la **accuracy**, se deben usar métricas como **precision**, **recall**, y **F1-score**, que permiten medir tanto la **precisión** de las predicciones como la capacidad del modelo para **recuperar ejemplos positivos**. También se podría considerar el uso de **ponderación de clases** y **cost-sensitive learning** para asegurarse de que el modelo minimice los errores costosos.
