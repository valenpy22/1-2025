# Clase 1
## Unidad 1: Introducción a la Arquitectura de Datos
- Qué es la arquitectura de datos
- Data Warehouse
- Data Lake
- Lake House
- Data Mesh
- Tipos de datos
- Estrategias de almacenamiento de datos y zonas de consumo
- Data "caliente" o data "fría"

## Unidad 2: Modelado de datos y métodos de ingesta

- Arquitectura On-Premise
- Arquitecturas Cloud
- Modelos de analítica avanzada
- Productos de datos (DevOps)
- Ciclo de vida de productos de datos
- Métodos de ingesta: DTS, ETL, ELT y SQL
- Deploy de datos
- Test, cuadraturas y monitoreo
## Unidad 3: Introducción Gobierno de datos
- Qué es el Gobierno de Datos
- Por qué es importante
- Para qué es
- Tipo de Gobierno de Datos
- Framework DAMA
- Dueños, roles, dominio de datos, glosario y catálogo de datos
## Unidad 4: Introducción Seguridad en datos
- Gobierno de datos, compliance, privacidad y seguridad
- Clasificación de activos de datos
- Políticas de seguridad
- Herramientas de visualización y sus riesgos de seguridad
- Mecanismos de encriptación y ofuzcación de datos

# Clase 2
## ¿Qué es la arquitectura de datos?
Se refiere al arte y la ciencia de construir cosas. Es decir, se refiere a una disposición organizada de elementos o componentes destinados a optimizar el funcionamiento, el rendimiento, viabilidad, costo y estética de una estructura o sistema general.

## TOFAG (The Open Group Architecture Framework) - Arquitectura Empresarial
Uno de los primeros frameworks de arquitectura. 

## Definición y objetivos
Identificar las necesidades de datos de la empresa (independiente de la estructura), y diseñar y mantener los planos maestros para conocer las necesidades. Hacia dónde quiere ir la empresa, hay que tener en cuenta que ahora mismo todas las empresas están interesadas en la IA generativa. Alinear la inversión de datos con la estrategia de negocios. 

## Entradas (Proveedores)
Debe entender la arquitectura empresarial, de negocios, estándares y metas IT, y estrategias de datos. En el fondo, conocer el negocio.

## Actividades (Participantes)
Se debe establecer una arquitectura empresarial de datos, evalúa especificaciones de arquitecturas de datos existentes, desarrollar una hoja de ruta, gestionar requerimientos empresariales dentro de proyectos e integrar con la arquitectura empresarial.

## Salidas (Consumidores)
Se entrega un diseño de arquitectura de datos, flujo de datos, cadenas de valor de datos, modelo empresarial de datos y ruta de implementación.

### Notas de la profesora
Actualmente muchos se están certificando con Google, como arquitecto no puedes ofrecer algo tan grande.
Hay que entender bien el sistema tecnológico.

## Métricas
- Tasas de cumplimiento de estándares de Arquitectura
- Tendencias de implementación
- Métricas de valor de negocio
## Herramientas
- Herramienta de modelado de datos
- Software de Gestión de activos
- Aplicaciones para diseño gráfico
## Técnicas
- Revisión de ciclos de vida
- Claridad de diagramación

### Notas de la profesora
- Herramientas: Miro
- Una cosa es que en el papel se pueda dibujar, pero no necesariamente se apega a la realidad. Esto sucede por los permisos y autorizaciones que se tienen con respecto a los datos.

## Objetivos de la Arquitectura de Datos
Implementar una ==visión coherente== del panorama de datos de la organización.
Utilizar enfoque de arquitectura estándar en línea con la estrategia de TI y/o las hojas de ruta. 

## Importancia de la Arquitectura de Datos
Es el proceso de evaluar, diseñar y gestionar los sistemas de almacenamiento y procesamiento de datos de una organización. 
Esta infraestructura incluye bases de datos, servidores de archivos, herramientas de análisis, sistemas de integración de datos y cualquier otro componente necesario par el almacenamiento.

## Frameworks de arquitectura
1. **TOGAF (The Open Group Architecture Framework)**: Enfocado en ==arquitectura empresarial== con un proceso de certificación de dos partes.
2. **DAMA (Data Management Association)**: Framework específico para ==gestión de datos==, que abarca planificación, control, desarrollo y operaciones.
## Roles y responsabilidades clave
1. **Arquitecto de datos:** Comprende cómo los elementos impactan en el servicio y soporta los requerimientos del negocio.
2. **Ingeniero de datos y Machine Learning:** Extrae y carga datos entre sistemas en diferentes componentes organizacionales.
3. **Analista y Científico de datos**: Extrae datos y crea nuevos modelos para ser consumidos por servicios.

## Documentación necesaria
Los documentos deben satisfacer a:
- **Usuarios de negocio:** Documentos de requerimientos, diagramas de procesos, glosario de negocios.
- **Usuarios de desarrollo:** Documentos de arquitectura, diagramas de flujos.

### Notas de la profesora
- ETL o ELT (Extract, Transform, Load): Proceso fundamental donde se obtienen los datos de múltiples fuentes, se convierten los datos extraídos mediante reglas de negocio, limpieza, validación y estandarización para que sean consistentes y se depositan los datos transformados en un destino final, como un data warehouse, data mart o data lake.
- El arquitecto se mete entremedio del Sprint Backlog porque puede ocurrir algo no pronosticado, problemas de escalabilidad.

Un Data Warehouse es una gran base de datos relacional. 
Suele incluir el id, ~~rut~~, dirección (normalizar), renta (rango), género (0 o 1), ~~nombre~~, edad. 
Esto es data estructurada, y vive en motores relacionales. Se puede hacer analítica descriptiva, pero no se pueden hacer mejores cosas.

En el caso de querer procesar diferentes tipos de documentos, nos encontramos con data no estructurada (PDF, Word, Twitter). 
Claramente, no se pueden cargar imágenes en un Data Warehouse. 

Un Data Lake puede recibir tanto data estructurada como data no estructurada.

Las infraestructuras actuales tienen tanto un Data Warehouse como un Data Lake.

## Un poco de historia
Bill Inmon fue un profesional de datos desde finales de la década de 1970 hasta la de 1980. Desarrolló el concepto de almacenes de datos: "Una colección de datos orientada a temas, integrada, no volátil y variable en el tiempo en apoyo de las decisiones de la gerencia".

## The data warehouse sunrise
Entra data operacional y sale data analítica.

### Razones para utilizar un DW
1. Integración de datos: Reune información de diferentes sistemas y formatos en una estructura unificada.
2. Optimización del rendimiento: Consultas y análisis rápidos.
3. Histórico de datos
4. Mejor toma de decisiones
5. Seguridad y control: Políticas de gobernanza sobre la información.

### ¿Para qué sirve?
- Soporte en la toma de decisiones
- Análisis de tendencias
- Optimización de procesos
- Cumplimiento de normativas

En el fondo, permite a la empresa ser más competitiva al transformar datos en información estratégica.

Originalmente, se tenía pensado cierta capacidad y cierta demanda para su uso. Pero durante el tiempo, se quedó corto. Sigue sirviendo para la analítica, ya que esa es su función principal.

Últimamente muchas empresas han migrado de DW a Data Lake.

Tradicionalmente los DW se han enfocado en datos estructurado. Sin embargo, con el tiempo, el espacio de BI y DW ahora abarca datos semi-estructurados y no estructurados.

## Tipos de datos
## Datos estructurados
Elementos en campos definidos, como en archivos o tablas, documentados en modelos de datos.

## Datos semi-estructurados
Elementos electrónicos organizados como entidades semánticas sin afinidad de atributos requerida. Por ejemplo, transferencias EDI.

## Datos no estructurados
Datos no predefinidos mediante un modelo de datos. Por ejemplo, correos electrónicos, textos de formato libre, documentos empresariales, vídeos, etc.

# Clase 3
## Data WareHouse
Repositorio centralizado diseñado para almacenar datos integrados de múltiples fuentes heterogéneas. Es decir, cualquier sistema que este reconocido en la organización debería entrar y con una herramienta ETL los transforma. 
Estos datos se procesan y estructuran para consultas y análisis. 

Las empresas, en vez de ocupar un staging area, pasan directamente al Data Warehouse.

Internamente, se tienen 3 espacios de trabajo distintos.

## Data en bruto
Extraction, Load. No le hizo ninguna modificación, y guardó la metadata.
## Metadata
Qué es lo que se movió, tiempos de carga, qué procesos fallaron, qué hacía el proceso, etc.
## Data agregada
Extract, Transform, Load. Así, tengo la data lista para hacer el análisis. 

La idea de todo esto, es poder normalizar o estandarizar los datos para que sigan un mismo formato. 
Además, la idea es contrastar si los datos agregados están bien al comparar con la data en bruto. 

Se le crea un servidor aparte para la presentación, y otro para data mining. 

Se espera a un horario que no sea peak para poder trasladar los datos de un lugar a otro.

# Clase 4
## Data Lake
Repositorio de almacenamiento a gran escala que contiene una gran cantidad de datos sin procesar en su formato nativo hasta que se necesita. Puede manejar datos estructurados, semi-estructurados y no estructurados.

### Capas
#### Capa de ingesta de datos
Recopila datos de muchas fuentes diferentes.  
Los datos se pueden recopilar todos a la vez en momentos específicos o se pueden transmitir continuamente en tiempo real.
Apache Kafka puede transmitir datos en tiempo real, Apache Flume puede administrar grandes registros de datos y las herramientas ETL manejan el procesamiento de datos por lotes.

#### Capa de almacenamiento
Una vez recopilados los datos, se almacenan como están, sin ningún cambio.
Pueden contener diferentes tipos de datos, desde datos muy organizados (como bases de datos) hasta datos menos organizados (como correos electrónicos o vídeos).

Cuando se controla el consumo en la zona aumentada, empeora el funcionamiento.

Sandbox: Ambiente para jugar, pero los gastos son reducidos y acotados.

Diagramas de tipo C1
#### Capa de procesamiento
Utiliza herramientas para clasificar y utilizar los datos según sea necesario.
Hadoop o Apache Spark pueden procesar rápidamente grandes cantidades de datos.

#### Capa de análisis y consumo
Aquí se trabajan con los datos, los analizan para encontrar ideas y tomar decisiones.
Utilizan herramientas de análisis para explorar los datos, buscando patrones o información útil que pueda ayudar al negocio. 

### Elefante amarillo
Hadoop (especial para trabajar con grandes volúmenes de daatos). Es una herramienta de EL.
