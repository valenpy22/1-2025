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

# Clase 3
## Funciones hash
MD5, SHA1, SHA2, SHA3.

```bash
Get-FileHash -Algorithm md5 .\1.txt  # 148
Get-FileHash -Algorithm sha1 .\1.txt # Más robusta, 160
Get-FileHash -Algorithm sha512 .\1.txt # Mucho más robusta
Get-FileHash -Algorithm RIPEMD160 .\1.txt # Más robusta, 160
```

El hash no cambia si es que se mantiene el contenido y se cambia el nombre del archivo. 

Mientras más alto sea el número del sha, más complejo será la encriptación.
### Fips202

### Shake hash
Sirve para IoT o para sensores, es liviano, no requiere tantos recursos. 

### Tiger
### Blake3

## Endianness
Se refiere al formtato en que se almacenan los datos de más de un byte en un ordenador.
### Little endian
Formato de orden de bytes en memoria, tomando el byte menos significativo primero.

### Big endian
Formato de orden de bytes en memoria, tomando el byte más significativo primero.

## Ofuscación
Técnica de protección de software que dificulta la lectura y comprensión del código fuente.

## God killer
Envía SMS automatizados de forma rápida.

## Salt
Cadena aleatoria que se agrega al dato original antes de calcular el hash, para evitar que dos usuarios con la misma contraseña tengan el mismo hash, y aumentar entropía y unicidad.
Tiene entre 8 y 16 caracteres.
```bash
mkpasswd -m sha-512 # Se ingresa una contraseña y se generará un hash automáticamente
```

### NeuralHash collisions
Técnica desaarrollada por Apple que intenta identificar imágenes semánticamente similares, usando una red neuronal que produce un hash basado en características visuales de la imagen.
```
python nnhash.py cat.pbg
```

## Key Derivation Function
Un KDF toma como entrada una contraseña (o clave base) y otros parámetros como una sal y un contador de iteraciones, y produce una clave criptográfica adecuada para ser usada en cifrado, autenticación u otras operaciones criptográficas.

### PBKDF2
Password Based Key Derivation Function 2 es una functión criptográfica que convierte una contraseña en una clave segura, usando una función hash, una sal aleatoria, iteraciones.

## Light Weight Cryptography Environment
SHAKE proporciona un excelente recurso, es eficiente con el consumo de energía, ya que no requiere grandes recursos lógicos ni físicos.

### Imphash
Es una técnica en la que los valores hash se calculan basándose en los nombres de las bibliotecas/funciones importadas y su orden particular dentro del ejecutable. Especial para análisis forense y detección de malware en ejecutables. 

### Humanhash
Facilita que un usuario pueda leer un hash.