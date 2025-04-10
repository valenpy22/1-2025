Pregunta PEP
1. Indique la triada de seguridad y de ejemplos.

# Triada de Seguridad (CID o CIA)
Se refiere a los tres principios fundamentales que son esenciales para proteger la información: 
1. **Confidencialidad**: Protección de la información para que solo las personas autorizadas puedan acceder a ella. Asegura que la información seinsible esté protegida de accesos no autorizados.
2. **Integridad**: Se enfoca en asegurar que la información sea precisa y completa, y que no haya sido modificada o alterada de manera no autorizada.
3. **Disponibilidad**: Se enfoca en que la información y los recursos asociados estén disponibles para los usuarios autorizados cuando los necesiten. 
4. Autenticación: Verifica la identidad de un usuario, dispositivo o entidad antes de otorgarle acceso a recursos o sistemas. Lo que soy (algo exclusivamente mío), lo que sé (usuario, contraseña), lo que tengo (llave, token). Captcha + MFA. 
5. No repudio: Asegura que una persona o entidad no puede negar la validez de sus acciones o compromisos. Por ejemplo, al haber firmado un documento. 
# Conceptos
Codificación: Es un cambio de formato de algo, como por ejemplo cuando se cambia a binario

x⁴+x²+x+1 = x⁴+x³+x²+x+1
          1       0    1    1  1

Minería de datos -> Base 58
Mar -> Base 64
1. Tabla ASCII
M = 77 -> 01001101
a = 97 -> 01100001
r = 114 -> 01110010

010011 010110 000101 110010
   19         22          5         50
   T           W           F          y

Ofuscación
Permite hacer más complicado el decodificar.

3N Sin padding
3N+1 ==
3N+2 = 

Hola -> Cada 24 bits, termina en ==
Diego -> Cada 24 bits, termina en =

Rot 13 
cheef

OSPF
1. Sin autenticación
2. Con texto plano
3. Con MD5

MD5 syn
sha-sum
Los hash deben tener un 50% de sensibilidad, es decir, si cambio algo, debe cambiar al menos la mitad del hash.
No es lo mismo cifrado y hash, hash es para ver la integridad del archivo. 

Datos
1. Personales: Rut, nombre, etc
2. Sensibles: Contraseñas
3. Sintéticos: Datos creados por inteligencia artificial

Quickwins -> Tareas rápidas
Métrica -> KPI -> Lo que espero

Vector de ataque -> Ser humano 

5 ataques de ingeniería social
1. Phishing: Se relaciona con el correo
2. Vishing: Se relaciona con la voz
3. Smishing: Se relaciona con los SMS
4. Quishing: Se relaciona con un QR
5. Whaling: Consiste en engañar a personas de alto perfil en una organización. 
6. Spearphishing: Ataque a una sola persona.
7. Trashing: Buscar en la basura datos importantes.
8. Shouldersurfing: Ver por encima los datos personales (como en el metro)
9. Baiting: Deja carnada (un pendrive)
10. Tailgaiting: Como cuando dos personas pasan en el metro.


# Clase 2
## Entropía
Según el NIST, la entropía de una contraseña debe tener como mínimo 112 bits.

Entroía del caracter
log(2)(94) = 6,55 x 17 = 112,35 (17 caracteres de solo combinación de teclado)
log(2)(10) = 3,5 x 32 = 120 + otro factor (MFA)

La política lleva a normas, y la norma a procedimientos concretos.

## VPN (Virtual Private Network)
Tecnología que permite crear una conexión segura sobre una red menos segura entre tu computadora e internet. 