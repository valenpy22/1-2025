1. Explique qué es la triada de seguridad, mencione un ejemplo, usabilidad y controles para mitigar cada una.
La triada de seguridad es un conjunto de principios que permiten proteger la información:
**a. Confidencialidad:** Principio que garantiza que los datos los puedan acceder solamente las personas autorizadas.
Ejemplo: El correo electrónico cifrado para que solo el destinatario pueda leer el contenido.
Se usa en sistemas donde la privacidad es vital, como banca en línea y registros médicos.
Controles: Cifrado, control de accesos, autenticación fuerte.

**b. Integridad:** Principio que garantiza que los datos sean modificados exclusivamente por personas autorizadas.
Ejemplo: Una base de datos con contratos que garantiza que no ha sido modificada sin autorización.
Es fundamental en bases de datos, sistemas financieros y transmisión de datos.
Controles: Hashing, control de versiones y backups, registros de auditoría.

**c. Disponibilidad:** Principio que garantiza que la información esté disponible cuando se necesite por los usuarios legítimos.
Ejemplo: Que un servicio web debe estar operativo 24/7.
Vital en sistemas de salud y telecomunicaciones.
Controles: Redundancia y balanceo de carga, sistemas de respaldo y mantenimiento preventivo y monitoreo.


2. Explique el no repudio y autenticación, mencione ejemplos y controles para cada uno.
El no repudio es un principio que garantiza que no se pude negar la acción de un usuario.
Un ejemplo de esto es la firma digital en un contrato electrónico.
Algunos controles es usar firmas digitales basadas en criptografía asimétrica, sistemas de auditoría y certificados digitales emitidos por una autoridad de confianza.

La autenticación es el proceso de verificar la identidad de un usuario o sistema para asegurar que quien intenta acceder es quien dice ser.
Por ejemplo, al iniciar sesión en una plataforma con usuario y contraseña.
Algunos controles para mitigar riesgos podrían ser usar contraseñas seguras y políticas de cambio frecuente, autenticación multifactor y biometría. 

2. Indique qué es la ingeniería social, explique 5 ataques y en qué consisten.
La ingeniería social es un conjunto de técnicas que usan manipulación psicológica para engañar a personas y que revelen información confidencial, realicen acciones que comprometan la seguridad o faciliten accesos no autorizados.

a. Phishing: Envío de emails que simulan ser de una entidad confiable para obtener datos sensibles.
b. Whaling: Es un ataque dirigido a las personas de alto cargos, usando lo mismo que en phishing.
c. Spear phishing: Es un ataque dirigido, usando lo mismo que en phishing.
d. Baiting: Ofrecer algo atractivo para una persona y que cuando esta persona la ocupe, comprometa su sistema. Por ejemplo, botar pendrives con archivos maliciosos.
e. Shoulder surfing: Es un ataque en vivo que involucra ver a la persona colocar sus credenciales.
f. Pretexting: El atacante inventa una historia falsa, demostrando que es de una entidaad legítima para obtener credenciales privadas.
g. Tailgating (o piggybacking): Se refiere a entrar a un lugar físico restringido siguiendo a alguien autorizado sin tener permiso propio.

3. Explique las componentes del modelo AAA.
Autenticación: Principio que garantiza que una persona que accede a un sistema realmente sea quien dice ser.
Autorización: Principio que garantiza que una persona tenga los permisos necesarios para ejecutar ciertas acciones.
Auditoría: Se refiere a revisar los sistemas para verificar su seguridad (cómo se guardan las contraseñas y los registros de logs).

4. Alice desea enviar un mensaje secreto a Bob, pero no le ha comaprtido una lalve de forma previa y se encuentra en un canal inseguro. Alice elige un número secreto a=3 y le envía a Bob el número primo p = 11, la base g = 2, y el resultado del logaritmo discreto. Bob, a partir de su número secerto b=4, calcula la operación y sse la transmite a Alice. Determine la llave que generan ambos usuarios al utilizar la operatoria.
5. Determine el resultado de codificar la palabra Mar en formato Base64.