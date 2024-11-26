# herramientas

Creado: 21 de octubre de 2023 14:34

# Nmap

Nmap es una herramienta extremadamente versátil para el escaneo de redes y la evaluación de seguridad. A continuación, te proporcionaré una lista de las principales cosas que puedes hacer con Nmap, junto con una breve explicación de cada una:

1. **Descubrir dispositivos activos en una red:**
Puedes usar Nmap para identificar qué dispositivos están activos en una red, ya sea una dirección IP específica, una subred o un rango de direcciones IP. Esto te permite conocer qué dispositivos están conectados y responden en una red.
2. **Escanear puertos en un dispositivo:**
Nmap te permite identificar los puertos abiertos en un dispositivo. Esto es útil para determinar qué servicios están en ejecución y potencialmente vulnerabilidades.
3. **Identificar servicios y versiones:**
Con Nmap, puedes descubrir qué servicios se están ejecutando en los puertos abiertos y obtener información sobre las versiones de software de esos servicios. Esto es útil para conocer más sobre los servicios expuestos y las posibles vulnerabilidades asociadas.
4. **Adivinar el sistema operativo:**
Nmap puede intentar adivinar el sistema operativo del dispositivo objetivo, lo que te permite conocer el tipo de sistema que está en uso.
5. **Escaneo rápido:**
Puedes realizar escaneos más rápidos utilizando opciones como `F`, que se enfocan en los puertos más comunes, para obtener resultados rápidos en entornos donde el tiempo es crítico.
6. **Escaneo de red completo o parcial:**
Puedes escanear una dirección IP específica, un rango de direcciones IP o incluso una red completa para obtener una visión completa de los dispositivos y servicios en una red.
7. **Escaneo en modo silencioso:**
Nmap permite realizar escaneos sin mostrar la salida en la pantalla. Puedes guardar los resultados en un archivo para su posterior análisis.
8. **Utilizar scripts NSE:**
Nmap Scripting Engine (NSE) es un potente motor de scripting que te permite realizar escaneos y pruebas personalizadas. Puedes utilizar scripts predefinidos o escribir los tuyos propios para llevar a cabo tareas específicas, como escanear vulnerabilidades, detectar servicios específicos o realizar auditorías de seguridad.
9. **Escaneo de firewall y filtrado de paquetes:**
Nmap puede ayudarte a evaluar la efectividad de un firewall o las reglas de filtrado de paquetes. Puedes realizar escaneos para determinar qué puertos están filtrados o bloqueados.
10. **Escaneo de scripts de seguridad:**
Puedes utilizar Nmap para ejecutar scripts de seguridad específicos, como `smb-vuln-*, ftp-anon`, para buscar vulnerabilidades o configuraciones inseguras en servicios.
11. **Escaneo de subdominios:**
Nmap puede ayudarte a identificar subdominios activos al escanear un rango de direcciones IP o un dominio específico.
12. **Identificar dispositivos IoT:**
Nmap puede ser útil para detectar dispositivos IoT (Internet de las cosas) en una red, lo que es esencial para garantizar la seguridad de la IoT.
13. **Escanear una dirección IP o un rango de direcciones IP:**
    
    ```
    nmap 192.168.1.1
    nmap 192.168.1.1-50
    
    ```
    
14. **Escanear todos los puertos en un host:**
    
    ```
    nmap -p- <dirección_IP_objetivo>
    
    ```
    
15. **Escanear puertos comunes (Top 1000):**
    
    ```
    nmap -F <dirección_IP_objetivo>
    
    ```
    
16. **Identificar servicios y versiones:**
    
    ```
    nmap -sV <dirección_IP_objetivo>
    
    ```
    
17. **Adivinar el sistema operativo del objetivo:**
    
    ```
    nmap -O <dirección_IP_objetivo>
    
    ```
    
18. **Guardar resultados en un archivo de texto:**
    
    ```
    nmap -oN resultado.txt <dirección_IP_objetivo>
    
    ```
    
19. **Escanear una red completa (subred):**
    
    ```
    nmap 192.168.1.0/24
    
    ```
    
20. **Utilizar scripts NSE predefinidos:**
    
    ```
    nmap --script vuln <dirección_IP_objetivo>
    
    ```
    
21. **Escanear en modo sigiloso (sin salida en pantalla):**
    
    ```
    nmap -q <dirección_IP_objetivo>
    
    ```
    
22. **Identificar subdominios activos de un dominio:**
    
    ```
    nmap --script dns-brute <dominio>
    
    ```
    
23. **Escaneo de firewall y filtrado de paquetes:**
    
    ```
    nmap -sA <dirección_IP_objetivo>
    
    ```
    
24. **Escanear una red con un rango de puertos personalizado:**
    
    ```
    nmap -p 80,443,8080,8081 <dirección_IP_objetivo>
    
    ```
    
25. **Escanear varios objetivos desde un archivo:**
    
    ```
    nmap -iL lista_de_direcciones.txt
    
    ```
    
26. **Realizar un escaneo rápido de ping para determinar qué hosts están activos:**
    
    ```
    nmap -sn <dirección_IP_objetivo>
    
    ```
    
27. **Escanear utilizando un rango de puertos personalizado:**
    
    ```
    nmap -p 80-100,443 <dirección_IP_objetivo>
    
    ```
    
28. **Escaneo UDP para identificar servicios que utilizan este protocolo:**
    
    ```
    nmap -sU <dirección_IP_objetivo>
    
    ```
    
29. **Escaneo con un retraso personalizado entre paquetes:**
    
    ```
    nmap --scan-delay 2s <dirección_IP_objetivo>
    
    ```
    
30. **Ignorar el archivo `nmap-services` para la identificación de servicios:**
    
    ```
    nmap --version-intensity 0 <dirección_IP_objetivo>
    
    ```
    
31. **Mostrar resultados en formato XML para su posterior análisis:**
    
    ```
    nmap -oX resultado.xml <dirección_IP_objetivo>
    
    ```
    
32. **Escanear usando técnicas de fragmentación y evasión de firewall:**
    
    ```
    nmap -f -D RND:10 <dirección_IP_objetivo>
    
    ```
    
33. **Realizar un escaneo "stealth" (sigiloso) que oculta la identidad de Nmap:**
    
    ```
    nmap -sS <dirección_IP_objetivo>
    
    ```
    
34. **Escanear utilizando un proxy SOCKS para ocultar la dirección IP de origen:**
    
    ```
    nmap --proxy socks4://proxy_ip:1080 <dirección_IP_objetivo>
    
    ```
    
35. **Escanear solo hosts con el estado "open" (abierto):**
    
    ```
    nmap --open <dirección_IP_objetivo>
    
    ```
    
36. **Realizar un escaneo inverso DNS para obtener nombres de host:**
    
    ```
    nmap -R <dirección_IP_objetivo>
    
    ```
    
37. **Escanear usando un script personalizado de NSE:**
    
    ```
    nmap --script my_custom_script.nse <dirección_IP_objetivo>
    
    ```
    

---

---

# Hydra

Hydra es una herramienta muy versátil con una amplia gama de opciones y protocolos que pueden ser utilizados en combinación con ella. A continuación, te proporciono una descripción de los comandos y opciones más comunes en Hydra:

1. `l [nombre de usuario]` o `-login [nombre de usuario]`: Especifica el nombre de usuario que se utilizará en la prueba de fuerza bruta.
2. `L [archivo de usuarios]`: Permite especificar un archivo que contiene una lista de nombres de usuario para probar.
3. `p [contraseña]` o `-password [contraseña]`: Especifica una contraseña única que se probará.
4. `P [archivo de contraseñas]`: Permite especificar un archivo de contraseñas o diccionario que Hydra utilizará en la prueba de fuerza bruta.
5. `e ns` o `-empty-password [código de retorno]`: Configura el código de retorno que indica una contraseña vacía (ninguna contraseña).
6. `s [puerto]` o `-service [puerto]`: Especifica el puerto del servicio objetivo (por defecto, se utiliza el puerto predeterminado para el protocolo).
7. `t [número de hilos]` o `-threads [número de hilos]`: Define el número de hilos que Hydra utilizará para realizar el ataque de fuerza bruta. El uso de múltiples hilos acelera el proceso, pero ten en cuenta que puede aumentar la probabilidad de ser detectado.
8. `f` o `-forever`: Realiza un ataque de fuerza bruta de manera continua sin detenerse después de encontrar una contraseña válida.
9. `vV` o `-verbose`: Muestra información detallada durante la ejecución de Hydra.
10. `-f [formato]` o `-format [formato]`: Permite especificar el formato del archivo de contraseñas. Los formatos comunes son "simple" (nombre de usuario:contraseña) y "web1" (nombre de usuario:contraseña1 contraseña2).
11. `M [archivo de hosts]` o `-M [archivo de hosts]`: Especifica un archivo que contiene una lista de direcciones IP o nombres de host para probar.
12. `o [archivo de salida]` o `-output [archivo de salida]`: Guarda los resultados de la prueba de fuerza bruta en un archivo.
13. `-timeout [segundos]`: Define el tiempo de espera para cada intento de conexión.
14. `-no-restart`: Impide que Hydra vuelva a intentar después de encontrar una contraseña válida.
15. `-no-restore`: Evita que Hydra restablezca los intentos de fuerza bruta cuando se reinicia.
16. `-status [archivo de estado]`: Permite guardar y cargar el estado de un ataque en curso.
17. `-history [archivo de historial]`: Registra el historial de los intentos de autenticación.
18. `-disable [módulo]`: Desactiva un módulo de autenticación específico. Por ejemplo, `-disable ftp` deshabilitaría el módulo de FTP.
19. `-crack-status [código de retorno]`: Configura el código de retorno que indica que se ha encontrado una contraseña válida.
20. `-version`: Muestra la versión de Hydra.

Es importante tener en cuenta que la sintaxis exacta y las opciones pueden variar según el protocolo que estés atacando. Para obtener información detallada sobre las opciones y la sintaxis de un protocolo específico, puedes consultar la documentación oficial de Hydra o utilizar la opción `-U` para mostrar los módulos disponibles y luego consultar la documentación de un módulo específico.

---

---

## John The Ripper

John the Ripper es una herramienta de cracking de contraseñas que es extremadamente versátil y potente. Aquí tienes una lista de algunos comandos y características clave de John the Ripper:

1. **Crackear Contraseñas con Wordlist:**
    
    ```bash
    john --wordlist=<Wordlist> <Hashes>
    
    ```
    
    - `-wordlist=<Wordlist>`: Especifica la lista de palabras para la prueba.
    - `<Hashes>`: Archivo que contiene los hashes a crackear.
2. **Ataque por Fuerza Bruta:**
    
    ```bash
    john --incremental <Hashes>
    
    ```
    
    - `-incremental`: Realiza un ataque de fuerza bruta incremental.
3. **Seleccionar Formato de Hash:**
    
    ```bash
    john --format=<Formato> <Hashes>
    
    ```
    
    - `-format=<Formato>`: Especifica el formato del hash.
4. **Crackear Contraseñas con Reglas (Rule-based):**
    
    ```bash
    john --wordlist=<Wordlist> --rules <Hashes>
    
    ```
    
    - `-rules`: Aplica reglas para generar variantes de palabras.
5. **Mostrar Contraseñas Crackeadas:**
    
    ```bash
    john --show <Hashes>
    
    ```
    
    - `-show`: Muestra las contraseñas crackeadas.
6. **Ataque Incremental con Longitud Específica:**
    
    ```bash
    john --incremental:<Longitud> <Hashes>
    
    ```
    
    - `-incremental:<Longitud>`: Realiza un ataque de fuerza bruta incremental con contraseñas de una longitud específica.
7. **Utilizar Máquinas GPU (si está disponible):**
    
    ```bash
    john --format=<Formato> --device=<Número_GPU> <Hashes>
    
    ```
    
    - `-device=<Número_GPU>`: Especifica la GPU a utilizar.
8. **Generar Hash para Contraseña:**
    
    ```bash
    john --format=<Formato> --stdout <Contraseña>
    
    ```
    
    - `-stdout`: Muestra el hash de la contraseña proporcionada.

---

---

## Gobuster

1. **Enumerar Directorios:**
    
    ```bash
    gobuster dir -u <URL> -w <Wordlist>
    
    ```
    
    - `dir`: Indica el modo de búsqueda de directorios.
    - `u <URL>`: Especifica la URL objetivo.
    - `w <Wordlist>`: Selecciona la lista de palabras para la búsqueda.
2. **Enumerar Subdominios:**
    
    ```bash
    gobuster dns -d <Dominio> -w <Wordlist>
    
    ```
    
    - `dns`: Modo de búsqueda de subdominios.
    - `d <Dominio>`: Especifica el dominio objetivo.
3. **Búsqueda Recursiva de Directorios con Profundidad Específica:**
    
    ```bash
    gobuster dir -u <URL> -w <Wordlist> -t <Número_Hilos> -l -s <Código_Estado> -x <Extensiones> -r
    
    ```
    
    - `t <Número_Hilos>`: Especifica el número de hilos.
    - `l`: Mostrar la longitud de la respuesta.
    - `s <Código_Estado>`: Filtra por códigos de estado.
    - `x <Extensiones>`: Filtra por extensiones de archivo.
    - `r`: Búsqueda recursiva de directorios.
4. **Búsqueda de Archivos con Extensiones Específicas:**
    
    ```bash
    gobuster dir -u <URL> -w <Wordlist> -x <Extensiones>
    
    ```
    
    - `x <Extensiones>`: Filtra por extensiones de archivo.
5. **Búsqueda de Archivos o Directorios Ignorando Ciertos Códigos de Estado:**
    
    ```bash
    gobuster dir -u <URL> -w <Wordlist> -s "404,403,301"
    
    ```
    
    - `s "404,403,301"`: Ignora códigos de estado específicos.

---

---

## wireshark

### 1. **Instalación:**

- Descarga e instala Wireshark desde el [sitio web oficial](https://www.wireshark.org/).
- Durante la instalación, asegúrate de instalar los controladores de captura de WinPcap o Npcap (según la plataforma).

### 2. **Inicio de Wireshark:**

- Abre Wireshark desde el menú de inicio o el acceso directo.

### 3. **Seleccionar Interfaz de Captura:**

- En la barra de herramientas, elige la interfaz de red que deseas monitorear y hacer clic en el botón "Start" (Inicio) para comenzar la captura.

### 4. **Capturar Datos:**

- Wireshark comenzará a capturar datos en tiempo real. Observa los paquetes que se muestran en la ventana principal.

### 5. **Filtrar Datos:**

- Puedes aplicar filtros para visualizar solo los paquetes relevantes. Ingresa expresiones de filtrado en la barra de filtro (ejemplo: `ip.src == 192.168.1.1`).

### 6. **Detener la Captura:**

- Para detener la captura, haz clic en el botón "Stop" (Detener) en la barra de herramientas.

### 7. **Análisis de Paquetes:**

- Haz doble clic en un paquete para ver detalles como dirección MAC, dirección IP, protocolos, etc.
- La sección de "Follow" (Seguir) permite ver el flujo de datos.

### 8. **Guardar Capturas:**

- Puedes guardar las capturas en formato pcap para revisarlas más tarde o compartirlas con otros.

### 9. **Estadísticas Básicas:**

- Accede a "Statistics" (Estadísticas) en la barra de menú para ver estadísticas básicas como resumen de protocolos, direcciones MAC, etc.

### 10. **Conversaciones:**

- La opción "Statistics" -> "Conversations" (Estadísticas -> Conversaciones) te permite ver las conversaciones por dirección IP, puerto, etc.

### 11. **Exportar Datos:**

- Wireshark permite exportar datos en varios formatos para un análisis más detallado.

### 12. **Análisis de Flujo Seguro (SSL/TLS):**

- Wireshark puede desencriptar el tráfico SSL/TLS si tienes las claves privadas correspondientes.

### 13. **Seguimiento de Streams:**

- Para analizar flujos de datos específicos, utiliza la función "Follow" (Seguir) para TCP, UDP, etc.

### Notas Importantes:

- Asegúrate de tener permisos adecuados para realizar capturas de red.
- Wireshark muestra información sensible. Úsalo de manera ética y respetando la privacidad de los demás.

---

---

## openvpn

Aquí tienes una guía técnica básica para usar OpenVPN. OpenVPN es una herramienta de código abierto que permite crear conexiones VPN seguras. A continuación, se describen los pasos básicos para configurar y utilizar OpenVPN:

### Manual Técnico de OpenVPN

### 1. **Instalación:**

- Instala OpenVPN en tu sistema operativo. Puedes descargarlo desde el [sitio web oficial de OpenVPN](https://openvpn.net/community-downloads/).

### 2. **Generación de Certificados:**

- OpenVPN utiliza certificados para autenticar clientes y servidores. Puedes generar certificados utilizando la herramienta `easy-rsa` que generalmente viene con la instalación de OpenVPN.

```
bash

```

```bash
cd /path/to/easy-rsa
source vars
./clean-all
./build-ca
./build-key-server <nombre-servidor>
./build-key <nombre-cliente>
./build-dh

```

### 3. **Configuración del Servidor:**

- Crea un archivo de configuración para el servidor OpenVPN (por ejemplo, `server.conf`). Aquí hay un ejemplo básico:

```
conf

```

```
port 1194
proto udp
dev tun
ca ca.crt
cert <nombre-servidor>.crt
key <nombre-servidor>.key
dh dh2048.pem
server 10.8.0.0 255.255.255.0
push "redirect-gateway def1"
push "dhcp-option DNS 8.8.8.8"

```

### 4. **Iniciar el Servidor:**

- Ejecuta OpenVPN con la configuración del servidor:

```
bash

```

```bash
openvpn --config server.conf

```

### 5. **Configuración del Cliente:**

- Crea un archivo de configuración para el cliente OpenVPN (por ejemplo, `client.ovpn`). Aquí hay un ejemplo básico:

```
conf

```

```
client
dev tun
proto udp
remote <ip-servidor> 1194
resolv-retry infinite
nobind
persist-key
persist-tun
ca ca.crt
cert <nombre-cliente>.crt
key <nombre-cliente>.key

```

### 6. **Conectar el Cliente:**

- Ejecuta OpenVPN en el cliente con la configuración del cliente:

```
bash

```

```bash
openvpn --config client.ovpn

```

### 7. **Verificar la Conexión:**

- Una vez conectado, verifica la conexión a través de comandos como `ip a` o `ifconfig` para ver si la interfaz `tun` se ha creado.

### 8. **Detener el Servidor/Cliente:**

- Para detener el servidor o cliente, simplemente presiona `Ctrl+C` en la terminal donde se está ejecutando OpenVPN.

### Notas Importantes:

- Asegúrate de tener permisos adecuados para acceder a los archivos de configuración y certificados.
- Los certificados y claves son esenciales para la seguridad; guárdalos en un lugar seguro.