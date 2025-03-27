Comandos Nmap
```
-p-: Esta bandera escanea por todos los puertos TCP desde el puerto 0 hasta el 65535.

-sV: Intenta determinar la versión del servicio corriendo en un puerto.

--min-rate: Es usado para especificar el número mínimo de packetes Nmap que se deberían enviar por segundo; aumenta la velocidad de escaneo mientras más alto es el número.
```

# Conceptos
Windows Remote Management (WinRM) es un protocolo de Windows nativo para manejar el acceso remoto. 

Para poder acceder a otros archivos se debe modificar el parámetro "page=", donde después del signo igual se debe introducir:

```
page=../../../../../../../../windows/system32/drivers/etc/hosts
```

Así, se pueden ver los contenidos de la carpeta en cuestión. En este caso, se posible acceder porque en el método "include()" del backend en PHP está siendo usado para procesar el parámetro de URL *page* para mostrar una página distinta por diferentes lenguajes.
Y además porque no hubo una correcta sanitización.
Por lo tanto, existe una posibilidad de incluir un archivo en el espacio de trabajo.
Si seleccionamos un protocolo como SMB, Windows tratará de autenticarse a nuestra máquina, y así se puede capturar el NetNTLMv2.

**NTLM (New Technology Lan Manager)**
Es una colección de protocolos de autenticación creados por Microsoft. 
