# python ofensivo

Creado: 1 de octubre de 2023 12:57

Python is a powerful programming language that can be used for various purposes, including penetration testing (pentesting). It provides a wide range of libraries and tools that can be utilized for security testing and identifying vulnerabilities in computer systems. Python's versatility and ease of use make it a popular choice among pentesters. However, it is important to note that the use of Python for offensive purposes should always be done legally and ethically, following appropriate guidelines and permissions.

---

# Etapas del proceso de pentesting

- **reconocimiento (Modulo 1: recopilacion de informacion)**
- **escaneo (Modulo 2: Escaneo de Puertos)**
- **explotacion (Modulo 3: Password Cracking)**
- **post explotacion (Modulo 4: Creacion de BackDoor)**
- **borrado de huellas**

---

# Modulo 1: Recopilacion de informacion

---

## Obtencion de subdominios

La obtención de subdominios es el proceso de identificar y recopilar los subdominios asociados a un dominio principal. Un subdominio es una parte adicional de un dominio principal y se coloca delante del nombre de dominio principal, separado por un punto. Por ejemplo, en el dominio "[blog.example.com](http://blog.example.com/)", "blog" es el subdominio.

La obtención de subdominios es una técnica comúnmente utilizada en el proceso de pentesting para recopilar información sobre un objetivo. Al identificar los subdominios asociados a un dominio principal, los pentesters pueden descubrir nuevas áreas de un sistema que podrían ser vulnerables o susceptibles a ataques.

usando los modulos:

```python
import sys
import requests  # Para realizar solicitudes HTTP
from os import path
import argparse  # Para manejar argumentos de línea de comandos
import re  # Para usar expresiones regulares
```

```python
# Llamamos al módulo argparse para manejar los argumentos de línea de comandos
parser = argparse.ArgumentParser()

# Le agregamos un argumento para pasar el dominio
parser.add_argument('-t', '--target', help='Indicar el dominio')

# Le pasamos el dominio a parser
args = parser.parse_args()

wordlist = open('subdominios.txt', 'r')
wordlist = wordlist.read().split('\n')
            
# Para dominios http
for subdominio in wordlist:
#Construye la URL
 url = f"http://{subdominio}.{args.target}"
                
 #Verifica si la URL es válida antes de hacer la solicitud HTTP
 if is_valid_url(url):
	 try:
			requests.get(url)  # Realiza una solicitud HTTP a la URL
			print("(+) subdominio encontrado: " + url)
      except requests.ConnectionError:
			  pass

	# Para dominios https
  for subdominio in wordlist:
	  #Construye la URL
	  url = f"https://{subdominio}.{args.target}"
                
    # Verifica si la URL es válida antes de hacer la solicitud HTTP
    if is_valid_url(url):
    try:
	    requests.get(url)  # Realiza una solicitud HTTP a la URL
	    print("(+) subdominio encontrado: " + url)
		  except requests.ConnectionError:
	      pass

# Función para verificar si una URL tiene el formato correcto utilizando expresiones regulares
def is_valid_url(url):
    url_pattern = re.compile(r'^https?://[a-zA-Z0-9.-]+\.[a-zA-Z]{2,63}(/.*)?$')
    return bool(url_pattern.match(url))
```

---

## Bannergrabbing

El bannergrabbing es una técnica utilizada en el proceso de pentesting para obtener información sobre un servidor remoto. Consiste en enviar una solicitud al servidor y analizar la respuesta del banner, que es una cadena de texto que identifica al servicio o aplicación que se está ejecutando en el servidor.

El objetivo del bannergrabbing es obtener información relevante sobre el servidor, como el sistema operativo, la versión del software utilizado y posibles vulnerabilidades conocidas. Esta información puede ser utilizada por los pentesters para evaluar la seguridad del sistema y planificar posibles ataques.

```python
import socket  # Importa el módulo de socket para la comunicación
import sys

def banner(ip, port):  # Función para obtener el banner
    s = socket.socket()  # Crea un objeto de socket
    s.connect((ip, port))  # Establece una conexión a la IP y puerto proporcionados
    print(str(s.recv(1024)))  # Recibe datos del servidor y los imprime en la consola
```

---

## escaneo de tecnologias en sitio web

escanear un sitio web (proporcionado como argumento de línea de comandos) en busca de tecnologías y luego mostrar esta información

La herramienta "wad" es un escáner de tecnologías web que se utiliza para identificar las tecnologías y marcos de trabajo utilizados en un sitio web específico. Puede detectar lenguajes de programación, sistemas de gestión de contenido (CMS), servidores web, bases de datos y otras tecnologías web relacionadas.

automatiza la tarea de escanear un sitio web para identificar las tecnologías utilizadas, lo que puede ser útil para fines de análisis y evaluación de la infraestructura tecnológica de un sitio web en particular.

```python
import argparse
import sys
import subprocess  # Importa el módulo subprocess para ejecutar comandos en el sistema operativo

# Llamamos al módulo argparse para manejar los argumentos de línea de comandos
parser = argparse.ArgumentParser()

# Le agregamos un argumento para pasar el dominio
parser.add_argument('-t', '--target', help='indica el URL del sitio web')

# Le pasamos el dominio a parser
args = parser.parse_args()
```

este codigo importa las librerias y genera el argumento `target` para luego ser utilizada la informacion q pide para ejecutarla en un subproceso:

```python
# Ejecuta el comando "wad" para realizar el escaneo de tecnologías y redirige la salida a un archivo "tecnologias.txt"
        subprocess.run("wad -u " + args.target + " > tecnologias.txt", shell=True)
```

---

---

# Modulo 2: Escaneo de Puertos