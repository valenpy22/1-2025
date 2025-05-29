# 1. Databricks
Motor de análisis de datos con procesamiento distribuido, usa el motor Spark.
Introduce la Arquitectura Lakehouse.
## Delta Lake
Capa de almacenamiento transaccional que combina archivos de datos Parquet con un registro de metadatos.
Transforma un Data Lake en un sistema transaccional, dando mayor control.
## mlflow
Plataforma para gestionar el ciclo de vida completo del aprendizaje automático.
Facilita la gestión de modelos ML de forma estructurada, colaborativa y reproducible. 

## Componentes
- Workspaces: Entorno centralizado donde los equipos colaboran.
- Clusters: Conjunto de MV donde se ejecuta el procesamiento.
- Notebooks: Entornos interactivos que permiten escribir y ejecutar código.
- Jobs: Herramienta que permite programar y automatizar tareas. 

## Casos de uso
- Procesamiento de grandes volúmenes de datos de forma eficiente
- Análisis en tiempo real
- Machine Learning y AI escalable
- Gobernanza de datos
- Data Sharing y colaboración entre equipos o empresas
## Ventajas
- Democratización del big data: Permite hacer todo lo relacionado con análisis de datos
- Interoperabilidad e independencia de proveedores: Databricks se conecta directamente a la nube.
- Soporte end-to-end para ML e IA
- Documentación completa y base de conocimientos: Guía de inicio rápido y guías prácticas.

## Desventajas
- Curva de aprendizaje: Puede abrumar la cantidad de herramientas buenas.
- Scala como lenguaje principal: Si se utilizan otros lenguajes no se ejecutan en la máquina virtual de java, teniendo que hacer transformaciones para ejecutarlo.
- Comunidad relativamente pequeña: La gran cantidad de funciones son premium. 

## Conclusiones
Herramienta versátil con muchas funcionalidades, la cual es vital para las empresas para hacer un análisis de sus funciones. 

## Preguntas de profesora
- ¿Qué problemas trata de resolver Databricks en relación a su competencia? Por ejemplo, con Data Factory. 
- Deben comparar con otras herramientas.
- ¿Cómo se integra con Spark? ¿Cómo se conecta? ¿Cómo conversan?
- ¿Por qué ocupar Databricks versus otras?
- ¿Qué es Delta House?
- Si yo quisiera ocupar ML, ¿ocuparía Databricks? 
- Investigar cuadrante de Gartner para herramientas de ingesta o para herramientas de data security, puede que se repitan herramientas. 
# 2. Microsoft Fabric
## ¿Qué es?
SaaS. Plataforma integral de análisis de datos en la nube.
Permite gestionar, transformar y analizar datos en un solo lugar. 
Maximiza el valor a los datos en empresas: Es decir, tengo datos y estos datos valen mucho.
Integración de IA.
Permite análisis en tiempo real. 

## Características principales
- Mezcla de Azure Data Factory, Synapse Analytics y Power BI.
- Simplificación de tareas mediante una única interfaz.
- OneLake, como OneDrive pero de datos
- Compatible con Delta Lake
- Incorporó Azure OpenAI Services
- Automatización de tareas
- Insights generados con IA
- Escalable a cualquier volumen
- Económico

## Arquitectura técnica
- Data Factory: Más de 90 conectores integrados, ETL, ELT sin código, intuitivo.
- Synapse Workloads: Data engineering
- Power BI: Permite visualizar información de manera más rápida

## Aplicaciones
- Finanzas
- Salud
- Manufactura
- Retail

## Casos de uso
- Milliman: Pipelines customizados para clientes de firma actuaria/consultora
- Aurizon: Analítica de telemetría desde sensores de trenes

## Otras plataformas
- Databricks
- Snowflake
- SAP HANA Cloud

Está en el cuadrante de líderes.

## Beneficios
- Reducción de costos operativos
- ROI elevado
- Accesible desde aplicaciones amistosas de Microsoft

## Conclusiones
- Herramienta Software as a Service
- Disponible para varias industrias
- Muy útil para análisis

## Contras
- Podría quedar muy grande para empresas pequeñas al incluir tantas herramientas complejas.

## Preguntas de alumnos
- Sirve para ETL, ELT, ¿dónde posiciono la tecnología en un diagrama de arquitectura? 
- Hay 3 lakehouse, ¿el OneLake lo centraliza?

## Preguntas de profesora
- ¿Hicieron alguna demo? Si no, dar un ejemplo de dónde se podría usar, un ejemplo concreto: Manejo de información haciendo insights de clientes, por ejemplo no todos los pacientes no tienen los mismos síntomas. Serviría para mejores diagnósticos de enfermedades, o qué le conviene a las personas que compran en el retail.
- ¿Hicieron comparación con Synapse?

# 3. Kafka
## ¿Qué es Apache Kafka?
Plataforma de código abierto para manejar flujos de datos en tiempo real. Tiene una arquitectura distribuida tolerante a fallos.

### Origen de Apache Kafka
Fue creado por LinkedIn, nace por una necesidad. 
Es en honor a Franz Kafka.

### Relevancia
Integración eficiente entre sistemas con eventos. Se ha vuelto popular entre las empresas.

## Kafka vs Rabbit
- Kafka evita duplicados, tiene persistencia de mensajes y es muy escalable. 

## Cuadrante mágico de Gartner

## Ventajas
- Rendimiento, baja latencia
- Escalable
- Procesamiento en tiempo real
- Tiene integración con diversas tecnologías
- Redundancia

## Integración con otras tecnologías
- IA generativa: Se puede aprovechar para crear contenido dinámico debido a su procesamiento en tiempo real
- IBM
- Microservicios: Replicar datos en un almacén intermedio
- Otras tecnologías de Apache: Spark, Flink y Hadoop.

## Casos de uso
- Mensajería: Uber
- Captura de actividad en la página web: Twitter, debido a que toman los datos de los usuarios para recomendar más posts.
- Métrica de datos: Walmart
- Recopilación de registro: LinkedIn
- Procesamiento de datos: Spotify, toma data cruda y los enriquecen para que los consumidores los ocupen.
- Organización de eventos: Gmail, en qué lugar se subieron los datos, cuándo, etc. Apoya este servicio.
- Registro de subida: Pinterest, puede recuperar datos debido a la redundancia.

## Ejemplo
Los productores son las películas y series, los brokers son los servidores, los topics son las categorías, los consumidores son los espectadores y hay un grupo de consumidores (se clasifica a las personas que consumen lo mismo para hacer un mejor sistema de recomendación).

## Conclusión
- Plataforma clave en eficiencia y capacidad de integración, se ha convertido en una base sólida para las empresas. 

## Preguntas de alumnos
- ¿Qué son los topics? Son las categorías de la información
- ¿Qué pasa si se cae un topic? Hay redundancia por lo que las películas tienen varios topics que hacen que no se caigan.

## Preguntas de profesora
- En una empresa chilena orientada a IoT con un Data Lake, ¿dónde colocar Kafka? En ingesta de datos y procesamiento de datos.
- Kafka tiene una forma de mover datos, ¿como se asegura la integridad de los datos? No hay profundidad al respecto.
- De todo lo que se evaluó, ¿cuál es la característica que más les llamó la atención? Procesamiento en tiempo real, escalabilidad a nivel horizontal, capacidad de integración.
- ¿Qué funcionalidades destacarían en comparación a otras tecnologías? Tiene una mayor capacidad de movimiento de datos al ser robusto, tiene múltiples canales de entrada. 

# 4. Archivos Parquet
## ¿Qué es?
Formato open source basado en columnas, enfocado al manejo eficiente de grandes cantidades de datos.
Se usa en situaciones donde el análisis de datos es más importante que el manejo de datos.

## Características clave
- Como es columnar, su rendimiento de escritura es más lento, pero su rendimiento de lectura es más rápido, es más eficiente en cuanto a compresión, tiene menor tamaño de archivos y la aplicación recomendada es para almacenar los datos. 
- Compresión eficiente: Admite algoritmos de compresión
- Esquema auto-descriptivo: Integra metadatos detallados dentro del propio archivo.
- Algoritmos de compresión: SNAPPY, LZO, GZIP, BROTLI...
- Compatibilidad con  herramientas del ecosistema: Apache Spark, Apache Hive, Apache Hadoop y Apache Flink.

## Ventajas de parquet
- Eficiencia en el almacenamiento y compresión
- Lectura selectiva y rendimiento de consultas
- Soporte de esquemas complejos y evolución
- Reducción de costos oeprativos

## Arquitectura interna
- Es como el traspuesto de un excel normal.
- Empieza con "PAR1", antes de terminar se encuentra la tabla de contenidos, terminando también con "PAR1".
- Se dividen las columnas en subgrupos, repartiéndose de manera estratégica

## Diferencia con otros formatos
- Está comprimido en hexadecimal. 

## Casos de uso reales
- Especial para análisis de datos
- Varios productos de la suite de Apache como Spark, Hadoop, etc.
- Amazon S3 con AWS Glue

## Buenas prácticas
- Seleccionar un buen codec de compresión
- Particionar los datos
- Mantener un tamaño de archivo no demasiado grande
- Realizar un buen esquema
- Monitorear los metadatos: Son esenciales para las consultas eficientes

## Limitaciones
- Compresión incluida hace su lectura humana virtualmente imposible.
- Ineficiente al momento de insertar datos nuevos de manera frecuente.
- No es muy útil para manejar cantidades de datos pequeñas

## Conclusión
- No son la solución perfecta.

## Preguntas de alumnos
- ¿Se pueden comprimir en varios tipos de archivos? Sí, pero tienen que tener soporte para realizar esto. 

## Preguntas de profesora
- ¿Cuáles son las ventajas de ocupar Parquet en vez de CSV? Útil para obtener datos de un atributo en específico, ya que trabaja de forma columnar. No se necesita leer toda la tupla entera, sino que el atributo que se necesita. Reduce bastante el tiempo de búsqueda. También en temas de almacenamiento. 
- ¿Qué beneficios podría tener en el mundo de la analítica? Tiempo y espacio, se traduce en más ganancias en las empresas. 
- ¿Qué tipos de datos soporta Parquet? ¿Se puede meter una foto ahí? Respuesta: Lo que importa es cómo ordena los datos, no lo que entra. Soporta enteros, strings, etc.
- Mencionaron que los archivos Parquet guardan la metadata: ¿Qué rol cumple ese metadata? ¿Para qué sirve? Muestra el tipo de compresión del archivo, dónde se encuentra el tipo de dato buscado. Sirve para tener un registro de los mismos datos, al tenerse repartidos, si un dato se llegara a corromper, en el metadata hay un registro.
- ¿Hicieron una prueba para ver si realmente es más rápido que procesar un CSV? Sí, pero no lo tiene ahora. Se notaba la gran diferencia de procesamiento. 

# 5. Apache Parquet
## ¿Qué es?
Formato de almacenamiento columnar, libre y de alto rendimiento. 
Tiene un ahorro de almacenamiento.

## Historia
Nace de la necesidad de un procesamiento columnar más potente.

## Formato columnar
- Técnica que organiza datos en columnas

## Ventaja
- Mejor compresión
- Reducción de I/O
- Menor tiempo de descompresión y decodificación

## Desventajas
- No es eficientes para cargar por fila
- No ideal para OLTP (consultas transaccionales)
- Necesita un motor externo

## Otras tecnologías columnares
### Formato de almacenamiento columnar
- Feather
- FST
- Apache ORC

### Bases de datos analítica columnar
- ClickHouse
- Snowflake
- BigQuery
- Amazon RedShift

## Formato columnar v/s BD Columnar
- El formato tiene archivos portables, bajo costo, puede combinarse con herrramientas, requiere un motor externo, y se puede usaar en datalakes y pipelines. 


## Apache Parquet v/s Apache ORC
- Parquet tiene más compatibilidad con herramientas y plataformas, compresión por defecto (Snappy), el tamaño de archivo es más pequeño y compresión rápida. 

## Características técnicas
- Archivo: Unidad completa.
- Grupo de filas: Divide los datos horizontalmente.
- Fragmento columna: Dentro de cada grupo, los datos se almacenan verticalmente.
- Página: Valores reales
- Metadatos: Esquema de columnas, estadísticas, información de compresión y ubicación

## Casos de uso
Se tiene una empresa que centraliza sus datos en un data lake en la nube con diversas fuentes, en constante evolución, no se puede reescribir completamente cada vez que hay un cambio en el esquema.

### ¿CSV o JSON?
- Esquemas
- Evolución en su estructura
- Pipelines: Proceso de limpieza para pasarlo a otro ambiente

Es un archivo autodescriptivo, permite agregar columnas y eliminar columnas.
Maximiza la eficiencia analítica y la interoperabilidad entre sistemas.

Disminuye drásticamente el tamaño de los archivos, con un tiempo de consulta mucho menor, haciendo que el costo estimado sea del 99.7% de ahorro.

## Conclusión
- Formato ideal para arquitecturas de datos modernas por su eficiencia, escalabilidad y flexibilidad
- Mejora el rendimiento técnico, habilita infraestructura más robusta.

## Preguntas de alumnos
- No hay

## Preguntas de profesora
- ¿En qué caso no ocupar este tipo de archivo? Cuando hay strings porque pesan mucho. 

# 6. Iceberg Netflix
## ¿Por qué fue creado?
Ocupaba Apache Hive en un principio, pero al crecer tanto se vio limitado. 

# 7. ACID
## ¿Qué es?
Conjunto de propiedades que garantizan que las transacciones en una base de datos. 

## Componentes ACID
### Atomicidad
Garantiza que una transacción compuesta por múltiples operaciones se ejecute completamente. 

## Consistencia
Asegura que solo pueda llevar a la base un estado válido. 

### Aislamiento 

### Durabilidad

## ¿Qué es BASE?
Basically Available, Soft state, Eventually consistent.
Modelo usado en bases NoSQL y sistemas distribuidos

## Preguntas de alumnos
- ¿Se ocupa en Banco Estado?

## Preguntas de profesora
- ¿Cuál es el impacto de ACID en datos transaccionales?

# 8. Apache Flume

Qué tipo de integración tiene
Cuáles son sus componentes principales

# 9. Apache Hudi
## 