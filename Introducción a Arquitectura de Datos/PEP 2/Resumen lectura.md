# Integración e interoperabilidad de datos (DII)
Describe los procesos relacionados al movimiento y consolidación de datos entre los almacenes de datos, aplicaciones y organizaciones. 
La integración consolida la información en dos formas consistentes: física o virtual.
La interoperabilidad de los datos es la habilidad para múltiples sistemas de comunicarse. Algunas funciones que permite DII son:
- Migración y conversión de datos
- Consolidación de datos en hubs o marts

DII depende de estas áreas de gestión de datos:
- Gobernanza de datos
- Arquitectura de datos
- Seguridad de datos
- Metadatos
- Almacenamiento y operaciones de datos
- Modelamiento y diseño de datos

## Conceptos esenciales
### Extract
Es el proceso que incluye seleccionar la información requerida y extraerla de su fuente. Luego está en staged.
### Transform
El proceso hace que la información seleccionada sea compatible con la estructura del almacén de datos objetivo. Este proceso incluye casos donde la data es removida de su fuente cuando se mueve al objetivo, donde la información es copiada en múltiples partes, y donde la información es usada para disparar eventos pero no es persistida. Puede incluir cambios de formato (EBCDIC a ASCII), cambios de estructura (denormalizado a normalizado), conversión semántica (género a números), de-duping (remover duplicados) y reordenar (cambiar el orden de los datos para definir un patrón).
### Load
Se trata de guardar físicamente o presentar el resultado de las transformaciones en el sistema objetivo. 

### ELT
Si el sistema objetivo tiene más capacidades de transformación que la fuente o una aplicación intermediaria, cambia el orden a ELT. Esto permite hacer transformaciones luego de cargar la info. 

### Mapping
Es tanto el proceso de desarrollar una matriz de búsqueda desde la fuente a las estructuras objetivo y el resultado de ese proceso.

### Latency
Es la diferencia de tiempo entre cuando la información es generada en el sistema fuente y cuando la información está disponible para su uso en el sistema final. 

### Batch
Mucha información se mueve entre aplicaciones y organizaciones en bloques o archivos tanto por petición humana o automáticamente.

## Modelos de interacción
### Point-to-point
Pasan información directamente entre sí. Este modelo tiene sentido en el contexto de un pequeño conjunto de sistemas. Sin embargo, se vuelve ineficiente y aumenta el riesgo organizacional cuando muchos sistemas requieren la misma información de las mismas fuentes.

### Hub-and-spoke
Es una alternativa a PP, consolida la información compartida en un central data hub que muchas aplicaciones pueden usar. Todos los sistemas que quieran intercambiar información lo hacen a través del sistema en común central operativo de información, en vez de hacerlo directamente uno con otro. Data warehouses, Data Marts, Operational Data Stores.

### Publish - Subscribe
Involucra sistemas enviando información (publish), y otros sistemas tomando esa información (subscribe). Cuando la información es publicada, la información es automáticamente enviada a los subscribers.
