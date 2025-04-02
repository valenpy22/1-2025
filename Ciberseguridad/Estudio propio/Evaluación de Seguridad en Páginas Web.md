# 1. Preparación y planificación
- Definir el alcance, por ejemplo, determinar qué partes de la web se van a analizar, páginas públicas, áreas de login, funcionalidades específicas.

# 2. Explotación inicial
- Observar la estructura navegando manualmente por el sitio para entender el funcionamiento.
- Identificar puntos de entrada, como lo podrían ser formularios, campos de búsqueda, áreas de carga de archivos y APIs.
- Reconocer tecnologías y frameworks que utiliza el sitio.

# 3. Búsqueda de vulnerabilidades comunes
## Problemas de autenticación
- Intentar contraseñas débiles o predeterminadas
- Verificar si hay limitación en intentos de login
- Comprueba la robustez del sistema de recuperación de contraseñas

## Evaluar la gestión de sesiones
- Cómo se manejan las cookies
- Verificar si las sesiones caducan adecuadamente
- Comprueba si funciona la opción de cierre de sesión

## Verifica la entrada de datos
- Prueba entradas inesperadas en formularios
- Intenta enviar caracteres especiales o código simple
- Comprueba cómo responde la aplicación a entradas muy largas

## Revisa la protección de datos
- Observa si la información sensible viaja cifrada (HTTPS)
- Verifica si hay información sensible visible en URLs
- Comprueba si los mensajes de error revelan demasiada información

# 4. Verificación de configuraciones
- Cabeceras HTTP: Revisar si el sitio implementa cabeceras de seguridad básicas.
- Política de cookies: Comprueba si las cookies tienen atributos de seguridad.
- Archivos expuestos: Busca archivos de configuración, backups o directorios que no deberían ser accesibles.

# 5. Análisis lógico
- Verifica la lógica de negocio: Prueba si puedes alterar el flujo normal de operaciones
- Comprueba los permisos: Intenta acceder a recursos restringidos cambiando parámetros.
- Prueba la validación del lado del servidor: Verifica si todas las validaciones del lado del cliente también ocurren en el servidor.

# 6. Documentación de hallazgos
- Registrar problemas
- Captura de evidencias
- Evaluar el impacto

# 7. Reporte y recomendaciones
- Elabora un informe claro: Detallar los problemas encontrados de manera comprensible
- Prioriza por impacto: Ordena las vulnerabilidades según su gravedad
- Sugiere soluciones: Para resolver cada problema

