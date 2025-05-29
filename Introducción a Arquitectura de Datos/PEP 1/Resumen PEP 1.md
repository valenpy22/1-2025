# Arquitectura de datos
Se refiere al diseño estructurado y organizado de los componentes que almacenan, gestionan, y procesan datos en una organización.

# Data Warehouse
El concepto se desarrolló en los años 80, propuesto por Bill Inmon, y se convirtió en un elemento clave para la toma de decisiones en las empresas al integrar datos de diversas fuentes.

## Características
- **Integración de datos**: Reúne datos de sistemas diversos en una estructura unificada.
- **Optimización del rendimiento**: Diseñado para consultas rápidas, a diferencia de las bases de datos operacionales.
- **Almacenamiento histórico**: Permite el análisis de datos históricos para identificar tendencias y realizar comparaciones.
- **Repositorio centralizado**: Diseñado para almacenar datos estructurados de múltiples fuentes.
- **Procesos ETL**: Utiliza estos procesos para la integración de datos.
- **Cubos OLAP**: La información se almacena en un formato que facilita la consulta rápida.

## Arquitectura
- **Capa de origen de datos (data sources)**: Recopila los datos de diferentes fuentes.
- **Capa de preparación de datos (Staging)**: Limpia y transforma los datos.
- **Capa de almacenamiento**: Almacena los datos en un formato estructurado.
- **Capa de presentación**: Organiza los datos para facilitar su análisis y comprensión.

# Data Lake
Repositorio centralizado de datos crudos en su formato original, almacenando datos estructurados, semi-estructurados y no estructurados.
## Características
- **Formato original**: Repositorio que permite almacenar datos en su formato original, sin tener que hacer transformaciones previas.
- **Grandes volúmenes de datos**: Útil para almacenar grandes volúmenes de datos a una baja latencia. 
- **Integración de datos**: Puede integrarse con herramientas de procesamiento en tiempo real, como Apache Kafka o Apache Flume.

## Componentes
- **Capa de ingesta**: Recopila datos de diversas fuentes.
- **Capa de almacenamiento**: Guarda los datos sin transformarlos. 
	**Data en bruto**: Extracción, Carga. No se le hace ninguna modificación.
	**Metadata**: Son datos que describen otros datos. Los metadatos incluyen la definición de los datos, las estructuras, las fuentes y las relaciones entre ellos, facilitando su administración y análisis.
	**Data agregada**: Extracción, Transformación, Carga. La idea de todo esto, es poder normalizar o estandarizar los datos para que sigan un mismo formato. 
	**Sandbox**: Entorno aislado y controlado donde se pueden almacenar y procesar datos de manera experimental o en fase de prueba. Permite a los usuarios trabajar con los datos sin afectar el entorno de producción ni interferir con los sistemas principales de la organización.
- **Capa de procesamiento**: Utiliza herramientas como Hadoop o Spark para procesar y organizar los datos según sea necesario.
- **Capa de análisis y consumo**: Los analistas exploran los datos en busca de patrones y decisiones estratégicas.

## Ventajas
- Almacena grandes volúmenes de datos sin necesidad de transformación previa.
- Flexibilidad para almacenar diferentes tipos de datos (estructurados, semi-estructurados y no estructurados).

# Comparación entre DW y DL
- **Data Warehouse**: Se utiliza principalmente para análisis estructurados y consultas rápidas. Está diseñado para almacenar datos organizados y transformados, como un repositorio centralizado para decisiones estratégicas.
- **Data Lake**: Almacena grandes volúmenes de datos sin procesaar, permitiendo almacenar una variedad de tipos de datos. Es más flexible pero requiere un buen control de calidad de los datos para evitar convertirse en un "pántano de datos".

# Herramientas y técnicas en ADD
- **Data Warehousing**: Utiliza técnicas de integración de datos como ETL (Extract, Transform, Load) para limpiar y organizar los datos antes de almacenarlos.
- **Data Lakes**: Emplean herramientas como Apache Kafka para la transmisión en tiempo real y Apache Flume para la gestión de grandes registros de datos.

## Ventajas de utilizar DW y DL
- **DW**: Soporta el análisis estratégico a largo plazo, proporcionando datos históricos y bien organizados. Está optimizado para reportes, análisis histórico y toma de decisiones basadas en datos consolidados.
- **DL**: Soporta el análisis operativo en tiempo real, integrando datos crudos y permitiendo consultas rápidas sobre grandes volúmenes de datos. Permite la ingestión de datos masivos, facilitando el análisis en tiempo real y la flexibilidad de almacenamiento.

Ambas tecnologías pueden coexistir en una organización. El DW se usa para análisis estratégico con datos organizados y consolidados, mientras que el Data Lake se usa para almacenar datos en su formato bruto para análisis operativo y en tiempo real.

# ETL
Proceso utilizado para mover datos de un sistema de origen a un sistema de destino.

# DAMA-DMBOK (Data Management Body of Knowledge)
Marco de gestión de datos desarrollado por DAMA International. Este marco cubre prácticas y principios recomendados para gestionar los datos dentro de una organización de manera eficiente y conforme a estándares internacionales.

# Modelos de Datos Empresariales (EDM)
Es una representación detallada que describe entidades clave y sus relaciones dentro de la organización, que sirve de base para la integración de datos en un DW.

# Roles importantes
- **Arquitecto de datos**: Responsable de diseñar, crear y mantener la infraestructura de datos de la organización. Implica la creación de arquitecturas de bases de datos, la selección de tecnologías adecuadas, la definición de estrategias de almacenamiento y la integración de datos desde diversas fuentes. Diseña.
- **Ingeniero de datos**: Se encargan de construir y mantener los sistemas que permiten la recolección, almacenamiento y procesamiento de grandes volúmenes de datos. Gestiona.
- **Científico de datos**: Analizan grandes volúmenes de datos para extraer información útil mediante técnicas estadísticas. Analiza.

# Business Intelligence (BI)
Se refiere a las tecnologías, procesos y prácticas que permiten la recopilación, análisis, interpretación y presentación de datos empresariales para apoyar la toma de decisiones informadas en una organización. 

# Tecnologías
## DataBricks
Plataforma unificada de análisis de datos basada en Apache Spark. Proporciona herramientas para la ingeniería de datos, aprendizaje automático y análisis en la nube.

### Características
- Soporta notebooks interactivos.
- Se integra con Azure, AWS, y otros servicios en la nube.
- Optimiza el procesamiento de datos mediante Delta Lake.

## Microsoft Fabric
Plataforma de análisis unificado que integra herramientas de datos, aplicaciones y servicios en la nube. 

### Características
- Facilita la integración de datos desde varias fuentes.
- Enfocado en la transformación de datos en tiempo real.
## Parquet
Formato de almacenamiento columnar abierto y eficiente para grandes volúmenes de datos, muy utilizado en entornos de Big Data. 

### Características
- Optimiza el rendimiento y reduce los costos de almacenamiento.
- Soporta compresión y es altamente eficiente para operaciones de lectura/escritura.
- Es compatible con herramientas como Apache Spark, Hive, y Drill.

## Iceberg Netflix
Formato de almacenamiento de datos en tablas utilizado para gestionar datos a gran escala.

### Características
- Permite operaciones de lectura y escritura eficientes sobre grandes volúmenes de datos.
- Es ideal para entornos de data lakes y soporta la evolución del esquema de manera eficiente.
- Proporciona características como ACID para la gestión de transacciones.

## Apache Hudi
## Flume
Herramienta diseñada para la recolección, agregación y movimiento de grandes volúmenes de datos en tiempo real.

### Características
- Utilizado para la ingestión de datos de logs en data lakes o sistemas de almacenamiento como HDFS.
- Flexible y escalable para recopilar datos desde múltiples fuentes.
- Facilita la transmisión continua de datos.
## Dremel
Herramienta de Google utilizada para consultas en grandes volúmenes de datos. Su característica principal es su capacidad de realizar consultas interactivas a gran escala.

### Características
- Arquitectura de procesamiento en columnas
- Utiliza un motor de consulta distribuido que permite consultas rápidas sobre grandes volúmens de datos.
- BigQuery se basa en la tecnología Dremel.
## Kafka
Plataforma distribuida para el procesamiento de flujos de datos en tiempo real.

### Características
- Permite la transmisiión y procesamiento de datos en tiempo real.
- Ideal para la construcción de sistemas de mensajería distribuida.
- Es utilizado para gestionar grandes volúmenes de datos de manera eficiente, garantizando alta disponibilidad y tolerancia a fallos.
## Snowflake
Plataforma de data warehousing en la nube que permite almacenar y analizar datos a gran escala de manera eficiente.
### Características
- Soporta almacenamiento y análisis de datos estructurados y semi-estructurados
- Arquitectura separada para el almacenamiento y procesamiento de datos, mejorando el rendimiento.
- Integración con herramientas de BI y aprendizaje automático.
## ACID
Conjunto de propiedades que garantizan que las transacciones en bases de datos sean procesadas de manera confiable.
### Características
- Atomicidad: La transacción se completa en su totalidad o no se realiza.
- Consistencia: Los datos deben pasar de un estado válido a otro.
- Aislamiento: Las transacciones concurrentes no interfieren entre sí.
- Durabilidad: Una vez que la transacción ha sido confirmada, los cambios son permanentes.
## Redshift
Servicio de data warehousing en la nube proporcionado por AWS, utilizado para realizar análisis rápidos sobre grandes volúmenes de datos.
### Características
- Arquitectura optimizada para consultas analíticas.
- Utiliza almacenamiento columnar y compresión de datos para mejorar el rendimiento
- Integración con el ecosistema de AWS y herramientas de BI.
## Synapse
Plataforma de análisis en la nube de Microsoft que integra grandes volúmenes de datos y herramientas de BI.
### Características
- Permite la integración de datos desde diferentes fuentes.
- Ofrece capacidades de Big Data y Data Warehousing
- Se integra con herramientas como Power BI y Azure Machine Learning para análisis avanzado.

