# Proxies de interceptación
- Burp Suite
- OWASP ZAP

# Escáneres de vulnerabilidades
- Nikto
- Nessus

# Herramientas para fuzzing y descubrimiento
- Gobuster/Dirbuster
- Wfuzz

# Análisis de código y frameworks
- SonarQube: Para análisis estático de código
- OWASP Dependency-Check
- Nuclei: Para análisis de código dinámico

# Herramientas específicas para exploits
- SQLmap: Para detección y explotación automática de inyecciones SQL
- XSStrike: Para detección de vulnerabilidades XSS

# Metodología básica de análisis
## 1. Reconocimiento
Se deben identificar las tecnologías con Wappalyzer, mapear la estructura de la aplicación e identificar puntos de entrada, como lo podrían ser formularios, APIs, etc.

## 2. Escaneo y análisis
Se deben ejecutar escáneres automatizados, analizar manualmente la lógica de negocio y revisar el manejo de sesiones y autenticación.

## 3. Explotación controladas
Probar vulnerabilidades comunes como inyecciones SQL, XSS, CSRF, verificar configuraciones incorrectas y evaluar protecciones implementadas.

## 4. Documentación
