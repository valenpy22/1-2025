# Preguntas de PEP y control
### **1. ¿Qué definición y el propósito de un Data Warehouse y cómo se relaciona con las actividades de BI?**

- **Respuesta**: Un **Data Warehouse** es un repositorio centralizado de datos estructurados provenientes de diversas fuentes que se utiliza para facilitar el análisis y la toma de decisiones estratégicas en una organización. Su propósito es integrar, almacenar y procesar datos históricos que son utilizados por las herramientas de **Business Intelligence (BI)** para realizar análisis descriptivos, predictivos y prescriptivos, lo que permite a las organizaciones tomar decisiones informadas basadas en datos históricos.

### **2. Explica los objetivos principales de implementar un Data Warehouse.**

- **Respuesta**: Los objetivos principales de implementar un **Data Warehouse** son:
    
    - Integrar datos provenientes de múltiples sistemas y fuentes en una estructura coherente.
        
    - Optimizar el rendimiento en consultas y análisis de grandes volúmenes de datos.
        
    - Proporcionar acceso a datos históricos para facilitar la toma de decisiones estratégicas.
        
    - Mejorar la calidad de los datos y su gobernanza a través de un almacenamiento estructurado.
        
    - Facilitar las actividades de **Business Intelligence (BI)** al almacenar datos organizados listos para análisis.
        

### **3. ¿Qué son los metadatos?**

- **Respuesta**: Los **metadatos** son datos que describen otros datos. Incluyen información sobre el formato, las estructuras, las fuentes, la procedencia y las relaciones de los datos. Los metadatos son fundamentales para la administración, comprensión y utilización adecuada de los datos almacenados en un **Data Warehouse** o **Data Lake**, y permiten realizar un seguimiento de su origen, transformación y uso.
    

### **4. Entregue ejemplos de orígenes de datos posibles.**

- **Respuesta**: Ejemplos de orígenes de datos incluyen:
    
    - **Bases de datos operacionales** (CRM, ERP).
        
    - **Archivos planos** (CSV, JSON, XML).
        
    - **Sistemas de archivos** (logs, documentos).
        
    - **Fuentes externas** (redes sociales, datos públicos, APIs).
        
    - **Sensores IoT** (datos de dispositivos conectados).
        
    - **Aplicaciones y servicios web** (APIs de terceros).
        

### **5. ¿Cuáles son los principales componentes y participantes en el proceso de Data Warehousing y Business Intelligence?**

- **Respuesta**: Los principales componentes y participantes son:
    
    - **Data Warehouse (DW)**: El repositorio central de datos organizados.
        
    - **ETL (Extract, Transform, Load)**: Los procesos que extraen los datos, los transforman y los cargan en el DW.
        
    - **Herramientas de BI**: Como **Tableau**, **Power BI**, que permiten analizar y visualizar los datos.
        
    - **Científicos de datos**: Analizan los datos y crean modelos predictivos.
        
    - **Arquitectos de datos**: Diseñan y gestionan la infraestructura del DW.
        
    - **Ingenieros de datos**: Se encargan de la integración y procesamiento de los datos.
        

### **6. ¿Cómo contribuye la integración de datos y la interoperabilidad a la efectividad de un Data Warehouse?**

- **Respuesta**: La **integración de datos** y la **interoperabilidad** son clave para un **Data Warehouse** porque permiten combinar datos de diversas fuentes heterogéneas (por ejemplo, sistemas operacionales, archivos, APIs) en una estructura unificada. Esto asegura que los datos sean consistentes, accesibles y útiles para los análisis, lo que mejora la toma de decisiones en la organización.

### **7. ¿Cuál es el mejor término que define Arquitectura de Datos?**

- **Respuesta**: La organización fundamental de un sistema y sus componentes.
    

### **8. Según la lectura del documento: Arquitectura de datos ¿Cuál es el resultado primario de la arquitectura de datos?**

- **Respuesta**: Establecer la Arquitectura de Datos Empresarial.
    

### **9. ¿Qué herramientas se sugieren para usar en la Arquitectura de Datos?**

- **Respuesta**: Herramientas de modelado de datos y software de gestión de activos.
    

### **10. ¿Cómo se describe el “Modelo de Datos Empresarial” (EDM) en el documento?**

- **Respuesta**: Un modelo detallado con entidades y atributos clave de la empresa.
    

### **11. ¿Cuál de los siguientes no es un objetivo de la Arquitectura de Datos?**

- **Respuesta**: Desarrollar exclusivamente nuevas aplicaciones de software.
    

### **12. ¿Cuál es la relación entre los “modelos de dominio empresarial” y la Arquitectura de Datos?**

- **Respuesta**: Los modelos de dominio definen las aplicaciones de software, que son las que interactúan con la **Arquitectura de Datos**.
    

### **13. ¿Qué técnicas se utilizan comúnmente para la carga de datos en un almacén de datos?**

- **Respuesta**: Extracción, transformación y carga (ETL).
    

### **14. ¿Cuál de los siguientes componentes no es parte de un almacén de datos según se menciona en el documento?**

- **Respuesta**: Herramientas de gestión de relaciones con clientes (CRM).
    

### **15. ¿Qué implicación tiene la implementación de un Data Lake sobre una Arquitectura de datos de una organización en términos de procesamiento de datos en tiempo real?**

- **Respuesta**: Un **Data Lake** simplifica significativamente el procesamiento de datos en tiempo real debido a su capacidad de almacenar grandes volúmenes de datos en su forma bruta y procesarlos rápidamente.
    

### **16. En un Data Warehouse, es recomendable mantener una estructura de datos normalizada para optimizar el rendimiento de las consultas analíticas y facilitar la integración de datos de múltiples fuentes.**

- **Respuesta**: **Falso**. Generalmente, en un **Data Warehouse**, se puede usar una estructura desnormalizada para optimizar el rendimiento de las consultas analíticas.
    

### **17. El proceso ETL, que significa Extracción, Transformación y Carga, es exclusivo para el manejo de datos estructurados.**

- **Respuesta**: **Falso**. El proceso **ETL** también se puede utilizar para manejar datos no estructurados y semi-estructurados.
    

### **18. Los Data Warehouses generalmente contienen datos que son volátiles y se actualizan en tiempo real.**

- **Respuesta**: **Falso**. Los **Data Warehouses** generalmente contienen datos históricos y no se actualizan en tiempo real.
    

### **19. Según el documento, los Data Marts y los Cubos OLAP no son componentes esenciales de un almacén de datos.**

- **Respuesta**: **Falso**. Los **Data Marts** y los **Cubos OLAP** son componentes comunes y útiles en la arquitectura de un **Data Warehouse**.
    

### **20. Un Data Lake permite almacenar datos exclusivamente estructurados.**

- **Respuesta**: **Falso**. Un **Data Lake** permite almacenar datos en su formato original, lo que incluye datos estructurados, semi-estructurados y no estructurados.
    

### **21. En un Data Lake, los datos pueden ser almacenados en su formato original sin necesidad de transformaciones previas.**

- **Respuesta**: **Verdadero**. Un **Data Lake** almacena los datos tal como son, sin necesidad de transformarlos antes del almacenamiento.
    

### **22. Los Data Lakes son únicamente útiles para grandes corporaciones y no aportan valor a las pequeñas empresas.**

- **Respuesta**: **Falso**. Los **Data Lakes** son útiles para cualquier tipo de empresa, ya que permiten almacenar grandes volúmenes de datos en su formato original, lo que también beneficia a las pequeñas empresas al permitirles acceder a datos de diversas fuentes.
    

### **23. Uno de los beneficios clave de un Data Lake es su capacidad para realizar análisis de datos en tiempo real.**

- **Respuesta**: **Verdadero**. Un **Data Lake** permite la ingestión y procesamiento de datos en tiempo real, lo que es crucial para el análisis en tiempo real.
    

### **24. El uso de Data Lakes y Data Warehouses es mutuamente excluyente; las organizaciones deben elegir entre uno de los dos.**

- **Respuesta**: **Falso**. **Data Lakes** y **Data Warehouses** no son mutuamente excluyentes, y pueden coexistir en una organización para cubrir diferentes necesidades de datos y análisis.
    

### **25. La implementación de un Data Lake garantiza por sí misma una mejora en la calidad de los datos.**

- **Respuesta**: **Falso**. Un **Data Lake** no garantiza automáticamente la mejora de la calidad de los datos; se debe implementar una gobernanza de datos adecuada para asegurar la calidad y la integridad de los datos almacenados.
    

### **26. Explique las funciones y beneficios de utilizar tanto un Data Warehouse como un Data Lake en una estrategia de arquitectura de datos moderna. ¿Cómo pueden estas dos tecnologías trabajar juntas para apoyar tanto el análisis operativo como el estratégico en una organización?**

- **Respuesta**: Un **Data Warehouse** es ideal para almacenar datos estructurados y realizar análisis históricos, permitiendo a las organizaciones tomar decisiones estratégicas basadas en datos consolidados. Un **Data Lake**, por otro lado, permite almacenar grandes volúmenes de datos no estructurados y realizar análisis en tiempo real. Juntas, estas tecnologías pueden trabajar de manera complementaria: el **Data Lake** proporciona flexibilidad para almacenar y analizar datos crudos, mientras que el **Data Warehouse** organiza esos datos para análisis detallados y apoyo en la toma de decisiones estratégicas. Esto permite a las organizaciones tener una vista integral de sus datos para respaldar tanto el análisis operativo como el estratégico.