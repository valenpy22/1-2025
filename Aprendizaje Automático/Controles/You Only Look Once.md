## 1. Introducción y contexto (3 minutos)

- **Objetivo:** Explicar el problema general y contexto.
- **Contenido:**
    - Qué es detección de objetos y su importancia (vehículos autónomos, seguridad, robótica).
    - Problema principal: métodos tradicionales son lentos y complejos (pipeline con múltiples pasos).
    - Necesidad de detección rápida y eficiente para aplicaciones en tiempo real.
- **Consejo de slide:** Imagen ilustrativa del problema (ej. una imagen con objetos detectados y comparativa de tiempos). Poca letra, usa un esquema o un dibujo.
- **Lenguaje:** Simple, cercano, evita tecnicismos sin explicación.

---

## 2. Objetivo del artículo (1.5 minutos)

- **Objetivo:** Explicar qué propone YOLO.
- **Contenido:**
    - Proponer un modelo unificado para detección que haga todo en una sola red, una sola pasada.
    - Buscar alta velocidad sin sacrificar mucha precisión.
- **Slide:** Texto breve, un esquema simple con "YOLO = una red, una pasada".

---

## 3. Arquitectura del modelo (4 minutos)

- **Objetivo:** Explicar cómo funciona la red YOLO.
- **Contenido:**
    - División de la imagen en grilla (ejemplo 7x7).
    - Cada celda predice cajas delimitadoras (x, y, ancho, alto) y probabilidades de clase.
    - Concepto de confianza para cajas.
    - Uso de red convolucional profunda (24 capas conv + 2 fully connected).
    - Función de pérdida combinada para coord., confianza y clase.
- **Slide:** Esquema visual de la grilla con cajas, arquitectura simplificada en bloques (no texto técnico pesado).
- **Lenguaje:** Explica con analogías si quieres (ej. “imagina dividir la imagen en sectores para que cada uno busque objetos ahí”).
    

---

## 4. Datos y protocolo de experimentación (2 minutos)

- **Objetivo:** Explicar dónde y cómo se evalúa YOLO.
- **Contenido:**
    - Uso de dataset PASCAL VOC 2007 y 2012 (imágenes con objetos etiquetados).
    - Entrenamiento con imágenes completas y anotaciones de cajas.
    - Métricas usadas: mean Average Precision (mAP), frames por segundo (FPS).
    - Proceso de entrenamiento con aumento de datos y uso de dropout para evitar sobreajuste.
- **Slide:** Imagen o tabla simple con los datasets, métricas y proceso de entrenamiento resumido.

---

## 5. Resultados y comparación (3 minutos)

- **Objetivo:** Mostrar cómo se comporta YOLO frente a otros métodos.
- **Contenido:**
    - YOLO es mucho más rápido que métodos tradicionales (ej. Fast R-CNN, DPM).
    - Muestra números clave: 45 FPS con 63% mAP vs otros más lentos y menos precisos.
    - Limitaciones: problemas con objetos pequeños o cercanos.
    - Combinación con Fast R-CNN mejora aún más resultados.
    - Generaliza bien a otros dominios (arte, pinturas).
- **Slide:** Gráficos o tablas de comparación velocidad vs precisión, ejemplo visual de detección.

---

## 6. Análisis de resultados (2 minutos)

- **Objetivo:** Explicar qué significa la performance y errores.
- **Contenido:**
    - YOLO comete más errores de localización, pero menos falsos positivos en fondo.
    - Esto indica que ve mejor el contexto global.
    - Trade-offs entre velocidad y precisión.
- **Slide:** Gráficos de análisis de error (simplificados), esquema visual de errores comunes.

---

## 7. Conclusiones (2 minutos)

- **Objetivo:** Resumir los hallazgos y aporte del paper.
- **Contenido:**
    - YOLO es un avance significativo en detección rápida y unificada.
    - Combina velocidad y precisión aceptable, ideal para aplicaciones en tiempo real.
    - Su diseño simple y entrenable de extremo a extremo es una ventaja clave.
    - Aún hay espacio para mejorar detección de objetos pequeños.
- **Slide:** Bullet points claros con las conclusiones, sin texto denso.

---

## 8. Relación con materia vista en clases (2 minutos)

- **Objetivo:** Conectar el paper con conceptos de la asignatura.
- **Contenido:**
    - Ejemplo: En clase vimos redes convolucionales y su aplicación en visión por computador. YOLO usa una CNN profunda.
    - Aprendizaje supervisado con función de pérdida compuesta, similar a lo visto en aprendizaje automático.
    - Conceptos de regresión aplicada a coordenadas de cajas, en vez de solo clasificación.
    - Optimización end-to-end vs pipelines tradicionales: refleja principios de ingeniería de software y modelos integrados.
- **Slide:** Diagrama o tabla conectando términos del paper con los temas vistos en clase (redes, pérdida, optimización).