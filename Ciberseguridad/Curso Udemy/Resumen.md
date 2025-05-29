# 1. Metodologías Hacking Ético
Es importante seguir este lineamiento ya que facilita la realización de un conjunto de actividades en un orden predeterminado, estableciendo prioridades de estas para alcanzar el objetivo final.

## Metodologías principales
- OSSTMM (Open-Source Security Testing Methodology Manual): https://www.isecom.org/OSSTMM.3.pdf (Es la más popular)
- The Penetration Testing Execution Standard: http://www.pentest-standard.org/index.php/Main_Page (Es bastante representativa, a pesar de ser de alto nivel)
- ISSAF (Information Systems Security Assessment Framework)
- OTP (OWASP Testing Project): Testeo de aplicaciones web

## Metodología del curso
1. Definición del alcance del test de penetración: Se deben discutir las tareas, roles y responsabilidades. Todo esto se debe asegurar mediante contrato firmado. Se deben analizar las políticas de la organización ya que puede haber información sensible, y también se debe establecer un procedimiento en el caso de que se localice una intrusión por un tercero.
2. Recopilación de información (pasiva, semi-pasiva y activa)
3. Identificación y análisis de vulnerabilidades
4. Explotación de las vulnerabilidades
5. Post-explotación
6. Elaboración de un documento de reporte

## Preguntas
- ¿Cómo es un **informe real** de Hacking Ético o auditoría de seguridad?
	Dependen mucho de la organización que los realiza y el tipo de auditoría que se lleve a cabo. 
	1. Este es el primer recurso donde se tienen cientos de reportes de auditoríaas reales de diferentes empresas del sector del Hacking Ético y de la Ciberseguridad.
	- https://github.com/juliocesarfort/public-pentesting-reports
	
	2. Aquí hay diferentes plantillas que se pueden utilizar para comenzar a elaborar un informe propio.
	- https://pentestreports.com/templates/
	- https://github.com/hmaverickadams/TCM-Security-Sample-Pentest-Report

# 2. Recopilación pasiva de información
Se refiere a la fase de reconocimiento donde se obtiene toda la información de la infraestructura de la organización.
## 2.1 Recopilación pasiva
Recolección de información sin que las actividades realizadas por el analista sean mínimamente detectadas por dicho objetivo. Es decir, no se intercambia tráfico de red. Es difícil de realizar y suele proporcionar resultados poco concluyentes.

Entonces, ¿cómo obtener esta información?
A través del acceso a la información almacenada en **lugares públicos.**

## Técnicas de reconocimiento pasivo
### Hacking con buscador o Google Dorks
Todos los buscadores proporcionan capacidades avanzadas para construir consultas más avanzadas, permitiendo encontrar información específica.
#### Comandos
#### define:término
**Descripción:** Muestra definiciones de diversas páginas web para el término buscado.
**Ejemplo:** `define:osint`
**Qué hace:** Devuelve definiciones de “OSINT”, ayudando a comprender su significado.
#### filetype:término (o ext:término)
**Descripción:** Restringe la búsqueda a documentos con la extensión especificada (PDF, XLS, DOCX, etc.). Útil para localizar informes, listados o archivos confidenciales.
**Ejemplo:** `filetype:xls "password"`
**Qué hace:** Muestra hojas de cálculo en formato XLS que contengan la palabra “password”, pudiendo revelar credenciales.
#### site:sitio/dominio
**Descripción:** Filtra los resultados a las páginas de un dominio concreto. Ideal para investigar un objetivo específico.
**Ejemplo:** `site:pastebin.com "email list"`
**Qué hace:** Busca dentro de Pastebin contenido que incluya la frase “email list”, posible indicio de fuga de datos.
#### link:url
**Descripción:** Muestra qué páginas enlazan a la URL indicada (solo se reflejan enlaces de sitios con cierta relevancia para Google).
**Ejemplo:** `link:https://example.com`
**Qué hace:** Permite averiguar quién enlaza a _example.com_, útil para investigación OSINT y reputacional.
#### cache:url
**Descripción:** Muestra la versión que Google tiene guardada en caché de la página indicada.
**Ejemplo:** `cache:https://example.com`
**Qué hace:** Permite ver la última copia de _example.com_, incluso si el contenido original ha cambiado o sido eliminado.
#### info:url
**Descripción:** Ofrece información que Google tiene sobre la página o dominio especificado.
**Ejemplo:** `info:https://example.com`
**Qué hace:** Muestra datos relacionados con _example.com_, por ejemplo la versión en caché o páginas similares.
#### related:url
**Descripción:** Devuelve páginas que Google considera similares al sitio indicado.
**Ejemplo:** `related:https://example.com`
**Qué hace:** Muestra sitios “relacionados” con _example.com_, útil para descubrir competencia o dominios similares.
#### allinanchor:términos
**Descripción:** Restringe resultados a páginas que reciben enlaces (backlinks) cuyo texto contenga todos los términos indicados.
**Ejemplo:** `allinanchor:"database leaked"`
**Qué hace:** Muestra páginas enlazadas con la frase “database leaked” en su anchor text, revelando brechas de datos.
#### inanchor:término
**Descripción:** Similar a _allinanchor_, pero se puede combinar con otros términos en la misma búsqueda.
**Ejemplo:** `inanchor:breach "credit cards"`
**Qué hace:** Encuentra páginas cuyo anchor text incluya “breach” y que mencionen “credit cards” en el contenido.
#### allintext:términos
**Descripción:** Muestra solo páginas que contengan todos los términos en el texto.
**Ejemplo:** `allintext:"internal use only confidential"`
**Qué hace:** Filtra resultados a aquellos que incluyan la frase exacta “internal use only confidential” en el cuerpo del texto.
#### intext:término
**Descripción:** Busca páginas que incluyan un término en su texto. Puede combinarse con más palabras.
**Ejemplo:** `intext:exposed "api key"`
**Qué hace:** Retorna páginas donde aparezca “exposed” en el texto y que incluyan la frase “api key”, útil para detectar posibles credenciales filtradas.
#### allinurl:términos
**Descripción:** Muestra solo resultados que tengan todos los términos en la URL.
**Ejemplo:** `allinurl:"admin portal"`
**Qué hace:** Localiza URLs que incluyan “admin” y “portal”, útil para encontrar paneles de administración expuestos.
#### inurl:término
**Descripción:** Similar a _allinurl_, pero se puede combinar con otras palabras de búsqueda. Devuelve URLs que contengan el término.
**Ejemplo:** `inurl:wp-admin "vulnerabilities"`
**Qué hace:** Filtra páginas donde la URL contenga “wp-admin” y mencione “vulnerabilities” en el texto, para detectar fallos en WordPress.
#### allintitle:términos
**Descripción:** Limita los resultados a páginas cuyo título contenga todos los términos indicados.
**Ejemplo:** `allintitle:"database dump"`
**Qué hace:** Muestra resultados con “database dump” en el título, posible indicio de bases de datos expuestas.
#### intitle:término
**Descripción:** Similar a _allintitle_, pero se puede combinar con otros términos. Devuelve páginas cuyo título contenga el término.
**Ejemplo:** `intitle:"sql injection" "bypass authentication"`
**Qué hace:** Retorna resultados que en el título incluyan “sql injection” y mencionen “bypass authentication” en el contenido.
#### Operadores Booleanos
Estos operadores permiten combinar o filtrar términos para obtener resultados más específicos en búsquedas OSINT o de información sensible.
#### " "
**Descripción:** Busca la frase exacta, sin variaciones.
**Ejemplo:** `"employee private data"`
**Qué hace:** Devuelve resultados que incluyan exactamente “employee private data”, revelando posible exposición de datos.
#### -
**Descripción:** Excluye una palabra de la búsqueda.
**Ejemplo:** `"database dump" -site:github.com`
**Qué hace:** Muestra resultados de “database dump” excluyendo GitHub, centrando la búsqueda en otros dominios.
#### OR (ó |)
**Descripción:** Funciona como un “o lógico”. Devuelve resultados que contengan uno u otro término.
**Ejemplo:** `"mysql dump" OR "database leak"`
**Qué hace:** Amplía la búsqueda para incluir fugas de bases de datos bajo cualquiera de esos términos.
#### +
**Descripción:** Fuerza la inclusión de palabras que Google suele ignorar (artículos, preposiciones) o caracteres especiales (tildes, ñ, etc.).
**Ejemplo:** `+la "exposed password"`
**Qué hace:** Impide que Google omita “la” y fuerza la frase “exposed password”.
#### *
**Descripción:** El asterisco se usa como comodín para uno o varios términos desconocidos. Suele usarse con comillas para mantener la posición.
**Ejemplo:** `"confidential * report"`
**Qué hace:** Encuentra frases con “confidential”, luego cualquier palabra, y termina con “report” (por ejemplo, “confidential company report”).
### Google Hacking Database
Repositorio donde se encuentran distintos dorks subidos por la gente.
- https://www.exploit-db.com/google-hacking-database

### Shodan
Indexan servicios del sistema.

- https://github.com/jakejarvis/awesome-shodan-queries

#### Comandos
A continuación se presentan algunos de los filtros más relevantes para el uso de Shodan:
- `after`: Only show results after the given date (dd/mm/yyyy) string
- `asn`: Autonomous system number string
- `before`: Only show results before the given date (dd/mm/yyyy) string
- `category`: Available categories: ics, malwarestring
- `city`: Name of the city string
- `country`: 2-letter country code string
- `geo`: Accepts between 2 and 4 parameters. If 2 parameters: latitude, longitude. If 3 parameters: latitude, longitude, range. If 4 parameters: top left latitude, top left longitude, bottom right latitude, bottom right longitude.
- `hash`: Hash of the data property integer
- `has_ipv6`: True/False boolean
- `has_screenshot`: True/False boolean
- `server`: Devices or servers that contain a specific server header flag string
- `hostname`: Full host name for the device string
- `ip`: Alias for net filter string
- `isp`: ISP managing the netblock string
- `net`: Network range in CIDR notation (ex.199.4.1.0/24) string
- `org`: Organization assigned the netblock string
- `os`: Operating system string
- `port`: Port number for the service integer
- `postal`: Postal code (US-only) string
- `product`: Name of the software/product providing the banner string
- `region`: Name of the region/state string
- `state`: Alias for region string
- `version`: Version for the product string
- `vuln`: CVE ID for a vulnerability string

### Censys
Permite búsquedas como en Shodan, por lo que sirve para contrastar información.

### Whois
#### Comandos
- whois usach.cl

### Archive.org
Permite ver estados anteriores de páginas.

### TheHarvester
Herramienta que automatiza las búsquedas
#### Comandos
- theHarvester -d usach.cl -b baidu,yahoo,duckduckgo,bing -l 50 -f resultados
### Miniconda
- conda create -n "old_harvester" python=3.8.0
- conda activate old_harvester

### Maltego
Sirve para poder realizar una investigación a profundidad con grafos y herramientas automatizadas.
### Dehashed
Se pueden ver las contraseñas hasheadas.
### Have i been pwned?
Sirve para ver si han habido filtraciones de contraseña con respecto a un email.

### Recon-ng

## 2.2 Recolección semi-pasiva de información
### FOCA
### metagoofil
- metagoofil -d microsoft.com -l 10 -t pdf,doc,ppt -o Desktop
```bash
exiftool -r *.pdf | egrep -i "Author|Creator|Enail|Producer|Template" | sort -u
```

### Metashield
Página web para ver los metadatos, pero los muestra en bruto (al contrario de FOCA).

### Protocolo DNS
#### DNS Zone
Agrupación de registros DNS. Contienen diferentes tipos de registros:
![[Pasted image 20250521114849.png]]

### CentralOps
Permite conocer la IP del dominio asociado, si tiene redundancia y para hacer una resolución inversa.
### DNS Dumpster
Entrega iformación geográfica. 

#### Nota: Phrack.com
### Wireshark
Sniffer. Van a monitorizar todo el tráfico entrante y saliente de la red.

### TCPdump
Es un sniffer, igual que Wireshark, pero sin GUI. Todo se muestra a través de la consola.

sudo tcpdump -i interfaz
sudo tcpdump -v -i interfaz
sudo tcpdump icmp
sudo tcpdump host ip
sudo tcpdump -i wlan0 -w Desktop/capture.pcap
sudo tcpdump -n port 53 -v -r capture.pcap
sudo tcpdump -n port 80 -r capture.pcap | grep phrack.org


Así se puede ver con Wireshark

## 2.3 Recopilación activa
Se utilizan métodos que interactúan de manera directa con la organización, normalmente mediante el envío de tráfico de red.
- Escáneres de hosts
- Escáneres de puertos
- Escáneres de servicios

Se recomienda bug bounty de HackerOne. 