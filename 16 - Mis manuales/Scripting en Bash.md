# Scripting en Bash

Creado: 17 de diciembre de 2023 11:14

# Archivos de Bash

Guardar y ejecutar archivos en Bash es un proceso bastante simple. Aquí hay una guía paso a paso:

### Guardar un Archivo en Bash:

1. **Abre un Editor de Texto:**
    - Utiliza tu editor de texto favorito. Puedes usar nano, vim, gedit, o cualquier otro que prefieras.
    
    ```bash
    nano mi_script.sh   # Utiliza "nano" como ejemplo, puedes usar el editor que prefieras
    
    ```
    
2. **Escribe tu Script:**
    - Escribe tu código Bash en el editor. Por ejemplo:
    
    ```bash
    # mi_script.sh
    echo "Hola, mundo!"
    
    ```
    
3. **Guarda el Archivo:**
    - Guarda el archivo con el nombre que desees y con la extensión `.sh` para indicar que es un script de shell.
4. **Otorga Permisos de Ejecución (Opcional):**
    - Si no tienes permisos de ejecución, otórgalos al archivo.
    
    ```bash
    chmod +x mi_script.sh
    
    ```
    

### Ejecutar un Archivo en Bash:

1. **Navega a la Carpeta del Archivo:**
    - Abre una terminal y navega al directorio donde se encuentra tu archivo.
    
    ```bash
    cd ruta/del/archivo
    
    ```
    
2. **Ejecuta el Archivo:**
    - Puedes ejecutar el archivo directamente.
    
    ```bash
    ./mi_script.sh
    
    ```
    
    O si no otorgaste permisos de ejecución:
    
    ```bash
    bash mi_script.sh
    
    ```
    
    También puedes especificar el intérprete directamente en la primera línea del script:
    
    ```bash
    #!/bin/bash
    echo "Hola, mundo!"
    
    ```
    
    Después otorga permisos y ejecuta:
    
    ```bash
    chmod +x mi_script.sh
    ./mi_script.sh
    
    ```
    

---

# Scripting en Bash

El scripting en Bash se refiere a la creación de scripts (archivos de texto con comandos) que son ejecutados por el intérprete de Bash.

### 1. **Shebang (#!):**

Al inicio del script, agrega la línea `#!/bin/bash`. Esto indica que el script debe ser interpretado por Bash. Por ejemplo:

```bash
#!/bin/bash

```

### 2. **Comentarios:**

Usa `#` para comentarios. Los comentarios son ignorados por el intérprete de Bash y son útiles para documentar tu script.

```bash
# Esto es un comentario

```

### 3. **Variables:**

Las variables se crean sin espacios alrededor del signo igual. Se recomienda usar nombres de variables en mayúsculas.

```bash
MI_VARIABLE="Hola, mundo"

```

### 4. **Entrada de Usuario:**

Para obtener entrada del usuario, puedes usar el comando `read`.

```bash
echo "¿Cuál es tu nombre?"
read NOMBRE
echo "Hola, $NOMBRE"

```

### 5. **Condicionales:**

Los condicionales en Bash son similares a otros lenguajes.

```bash
if [ $EDAD -ge 18 ]; then
  echo "Eres mayor de edad."
else
  echo "Eres menor de edad."
fi

```

### 6. **Bucles:**

Los bucles `for` y `while` son comunes en scripts Bash.

### Bucle `for`:

```bash
for i in {1..5}; do
  echo $i
done

```

### Bucle `while`:

```bash
CONTADOR=0
while [ $CONTADOR -lt 5 ]; do
  echo $CONTADOR
  ((CONTADOR++))
done

```

### 7. **Funciones:**

Las funciones te permiten dividir tu script en bloques lógicos.

```bash
function saludar {
  echo "Hola, $1"
}

saludar "Juan"

```

### 8. **Ejecución de Comandos:**

Puedes ejecutar comandos y almacenar el resultado en una variable.

```bash
FECHA=$(date)
echo "La fecha actual es: $FECHA"

```

### 9. **Parámetros del Script:**

Puedes pasar parámetros a tu script.

```bash
#!/bin/bash

echo "El primer parámetro es: $1"
echo "El segundo parámetro es: $2"

```

### 10. **Redirección y Tuberías:**

Puedes redirigir la salida de un comando o unir varios comandos con tuberías.

```bash
ls > archivos.txt
cat archivos.txt | grep "documento"

```

### 11. **Manejo de Errores:**

Puedes usar el comando `trap` para manejar señales y errores.

```bash
trap 'echo "Error en la ejecución" && exit 1' ERR

```

### 12. **Arrays:**

Bash también permite el uso de matrices.

```bash
FRUTAS=("Manzana" "Banana" "Naranja")
echo ${FRUTAS[1]}  # Muestra "Banana"

```

### 13. **Expresiones Aritméticas:**

Puedes realizar operaciones matemáticas utilizando la doble paréntesis `(( ))`:

```bash
NUM1=5
NUM2=3
RESULTADO=$((NUM1 + NUM2))
echo "La suma es: $RESULTADO"

```

### 14. **Cadenas y Longitud de Cadenas:**

Manipula cadenas de texto y obtén la longitud de una cadena:

```bash
CADENA="Hola, mundo"
echo ${#CADENA}   # Muestra la longitud de la cadena
echo ${CADENA:6}  # Muestra "mundo"

```

### 15. **Case Statement:**

Estructura de control de casos:

```bash
FRUTA="Manzana"
case $FRUTA in
  "Manzana") echo "Es una manzana." ;;
  "Banana") echo "Es una banana." ;;
  *) echo "No es ni manzana ni banana." ;;
esac

```

### 16. **Operadores Lógicos:**

Utiliza operadores lógicos para combinar expresiones:

```bash
EDAD=25
if [ $EDAD -gt 18 ] && [ $EDAD -lt 30 ]; then
  echo "Eres un adulto joven."
fi

```

### 17. **Leer Archivos:**

Lee archivos línea por línea:

```bash
while IFS= read -r LINEA; do
  echo "Línea: $LINEA"
done < archivo.txt

```

### 18. **Variables de Entorno:**

Accede y define variables de entorno:

```bash
echo "El directorio actual es: $PWD"
export MI_VARIABLE="Valor"

```

### 19. **Archivos y Directorios:**

Verifica la existencia de archivos o directorios:

```bash
if [ -e archivo.txt ]; then
  echo "El archivo existe."
fi

if [ -d directorio ]; then
  echo "El directorio existe."
fi

```

### 20. **Funciones Avanzadas:**

Retorno de valores y parámetros por referencia:

```bash
function suma {
  local RESULTADO=$(( $1 + $2 ))
  echo $RESULTADO
}

resultado=$(suma 3 4)
echo "La suma es: $resultado"

```

### 21. **Debugging:**

Habilita la opción de debugging para rastrear errores:

```bash
#!/bin/bash
set -x  # Activa el modo debugging
# Resto del script
set +x  # Desactiva el modo debugging

```

### 22. **Expansión de Comandos:**

Puedes ejecutar comandos dentro de una cadena y almacenar el resultado en una variable:

```bash
FECHA=$(date +%Y-%m-%d)
echo "Hoy es $FECHA"

```

### 23. **Expresiones Regulares:**

Puedes utilizar expresiones regulares para realizar coincidencias:

```bash
if [[ "$NOMBRE" =~ ^[A-Za-z]+$ ]]; then
  echo "El nombre es válido."
else
  echo "El nombre no es válido."
fi

```

### 24. **Subshells:**

Puedes ejecutar comandos en un subshell, lo que significa que las variables locales no afectan al script principal:

```bash
(
  VARIABLE="Valor en subshell"
  echo $VARIABLE
)
echo $VARIABLE  # Esto no afecta al valor de la variable en el subshell

```

### 25. **Redirección avanzada:**

Además de la redirección estándar (`>`, `<`), puedes redirigir la entrada y salida de comandos:

```bash
comando1 2>&1 | comando2  # Combina la salida estándar y el error estándar

```

### 26. **Manejo de Archivos y Streams:**

Manipula archivos y streams con comandos como `grep`, `sed` y `awk`:

```bash
cat archivo.txt | grep "patrón" | sed 's/buscar/reemplazar/' | awk '{print $2}'

```

### 27. **Funciones Recursivas:**

Bash admite funciones recursivas:

```bash
factorial() {
  if [ $1 -eq 0 ]; then
    echo 1
  else
    echo $(( $1 * $(factorial $(( $1 - 1 ))) ))
  fi
}

resultado=$(factorial 5)
echo "El factorial de 5 es $resultado"

```

### 28. **Manipulación de Arrays:**

Bash permite la manipulación avanzada de matrices:

```bash
MI_ARRAY=(elemento1 elemento2 elemento3)
echo "Número de elementos en el array: ${#MI_ARRAY[@]}"
echo "Elementos del array: ${MI_ARRAY[@]}"

```

### 29. **Traps de Señales:**

Usa `trap` para capturar señales y manejarlas en tu script:

```bash
trap 'echo "Se recibió una señal de interrupción." && exit 1' INT

```

### 30. **Operaciones de Bitwise:**

Bash admite operaciones de bits:

```bash
NUM1=5
NUM2=3
RESULTADO=$((NUM1 & NUM2))
echo "El resultado de la operación AND bitwise es $RESULTADO"

```

### 31. **Manipulación de Fechas:**

Utiliza el comando `date` para manipular fechas y tiempos:

```bash
FECHA_ACTUAL=$(date +"%Y-%m-%d %H:%M:%S")
echo "La fecha y hora actual es: $FECHA_ACTUAL"

```

### 32. **Arrays Asociativos:**

A partir de Bash 4, puedes usar arrays asociativos para asignar valores a claves:

```bash
declare -A ASOCIATIVO
ASOCIATIVO["nombre"]="Juan"
ASOCIATIVO["edad"]=25
echo "Nombre: ${ASOCIATIVO["nombre"]}, Edad: ${ASOCIATIVO["edad"]}"

```

### 33. **Evaluación Perezosa:**

Puedes utilizar el operador `&&` para ejecutar un comando solo si el comando anterior tuvo éxito:

```bash
comando1 && echo "El comando 1 tuvo éxito" || echo "El comando 1 falló"

```

### 34. **Manejo de Opciones con `getopts`:**

Para manejar opciones de línea de comandos de manera eficiente:

```bash
while getopts ":abc:" OPCION; do
  case $OPCION in
    a) echo "Opción a";;
    b) echo "Opción b";;
    c) echo "Opción c con valor: $OPTARG";;
    \\?) echo "Opción inválida: -$OPTARG";;
  esac
done

```

### 35. **Programación Orientada a Objetos:**

Aunque Bash no es un lenguaje orientado a objetos, puedes simular objetos y métodos:

```bash
# Definición de objeto
Persona() {
  nombre="$1"
  edad="$2"
}

# Método de objeto
saludar() {
  echo "Hola, soy $nombre y tengo $edad años."
}

# Uso del objeto
persona1=$(Persona "Juan" 30)
saludar "$persona1"

```

### 36. **Manipulación de Cadenas con `sed` y `awk`:**

Utiliza `sed` y `awk` para manipular y procesar cadenas de texto:

```bash
echo "Hola, mundo" | sed 's/mundo/marte/'
echo "Juan 25" | awk '{print $1}'  # Muestra "Juan"

```

### 37. **Generación de Números Aleatorios:**

Genera números aleatorios con `$RANDOM` o `shuf`:

```bash
NUMERO=$((RANDOM % 100))
echo "Número aleatorio: $NUMERO"

NUMERO=$(shuf -i 1-100 -n 1)
echo "Número aleatorio: $NUMERO"

```

### 38. **Programación Funcional con `map` y `filter`:**

Aunque Bash no tiene funciones incorporadas como `map` y `filter`, puedes emular su comportamiento:

```bash
# Función map
map() {
  local FUN="$1"
  shift
  for ELEM in "$@"; do
    $FUN "$ELEM"
  done
}

# Función filter
filter() {
  local FUN="$1"
  shift
  for ELEM in "$@"; do
    if $FUN "$ELEM"; then
      echo "$ELEM"
    fi
  done
}

# Uso de map y filter
doble() {
  echo $(($1 * 2))
}

es_par() {
  [ $(($1 % 2)) -eq 0 ]
}

NUMEROS=(1 2 3 4 5)
DOBLE_NUMEROS=($(map doble "${NUMEROS[@]}"))
PARES=($(filter es_par "${NUMEROS[@]}"))

```

### 39. **Uso de `select` para Menús Interactivos:**

Crea menús interactivos con `select`:

```bash
opciones=("Opción 1" "Opción 2" "Opción 3" "Salir")
select opcion in "${opciones[@]}"; do
  case $opcion in
    "Opción 1") echo "Seleccionaste la Opción 1";;
    "Opción 2") echo "Seleccionaste la Opción 2";;
    "Opción 3") echo "Seleccionaste la Opción 3";;
    "Salir") break;;
    *) echo "Opción inválida";;
  esac
done

```

### 40. **Manejo de Errores y Excepciones:**

Implementa un manejo de errores más robusto con el uso de `trap` y la función `exit`:

```bash
function ejecutar_comando {
  $1 || { echo "Error al ejecutar $1"; exit 1; }
}

trap 'echo "Se produjo un error inesperado"; exit 1;' ERR

ejecutar_comando "comando1"
ejecutar_comando "comando2"

```

### 41. **Llamadas a APIs y Parsing JSON:**

Realiza solicitudes HTTP y analiza JSON usando herramientas como `curl` y `jq`:

```bash
RESPUESTA=$(curl -s "<https://api.example.com/data>")
VALOR=$(echo $RESPUESTA | jq ".key")
echo "Valor obtenido: $VALOR"

```

### 42. **Uso de `awk` para Procesamiento de Texto:**

`awk` es poderoso para procesar y analizar datos tabulares:

```bash
cat archivo.csv | awk -F',' '{print $1,$3}'  # Muestra la primera y tercera columna

```

### 43. **Uso de `find` y `grep` para Búsqueda de Archivos:**

Encuentra archivos y busca patrones dentro de ellos:

```bash
ARCHIVOS=$(find /ruta -name "*.txt")
for ARCHIVO in $ARCHIVOS; do
  grep "patrón" $ARCHIVO
done

```

### 44. **Manipulación de Fechas con `date` y `dateutils`:**

Realiza operaciones avanzadas con fechas:

```bash
FECHA_ACTUAL=$(date "+%Y-%m-%d")
FECHA_MANANA=$(date -d "tomorrow" "+%Y-%m-%d")
DIFERENCIA_DIAS=$(dateutils.ddiff $FECHA_ACTUAL $FECHA_MANANA)
echo "Diferencia en días: $DIFERENCIA_DIAS"

```

### 45. **Uso de `nc` (Netcat) para Comunicación en Red:**

`nc` permite la comunicación entre procesos a través de la red:

```bash
# Servidor
nc -l -p 1234

# Cliente
echo "Hola, servidor" | nc localhost 1234

```

### 46. **Verificación de Integridad de Archivos con `md5sum` o `sha256sum`:**

Calcula el hash de un archivo para verificar su integridad:

```bash
HASH=$(md5sum archivo.txt | awk '{print $1}')
echo "El hash MD5 de archivo.txt es: $HASH"

```

### 47. **Uso de `awk` y `sort` para Estadísticas:**

Procesa y analiza datos para obtener estadísticas:

```bash
cat datos.txt | awk '{print $2}' | sort | uniq -c | sort -nr

```

### 48. **Automatización de Tareas con `cron`:**

Programa tareas periódicas utilizando el cron job:

```bash
# Editar la tarea programada
crontab -e

# Ejemplo de ejecución diaria a las 2:30 AM
30 2 * * * /ruta/al/script.sh

```

### 49. **Uso de `printf` para Formateo de Salida:**

`printf` permite un mayor control sobre la formateo de la salida:

```bash
NOMBRE="Juan"
EDAD=25
printf "Nombre: %-10s Edad: %d\\n" "$NOMBRE" $EDAD

```

### 50. **Uso de `watch` para Observar Cambios:**

Observa los cambios en tiempo real en la salida de un comando:

```bash
watch -n 1 "ls -l"

```

---

### Scripting para ciberseguridad

### 1. **Análisis de Logs:**

Bash es útil para analizar logs y eventos de seguridad. Puedes buscar patrones sospechosos o realizar análisis de comportamiento:

```bash
grep "Acceso no autorizado" /var/log/auth.log

```

### 2. **Exploración de Red:**

Automatiza la exploración de red para identificar hosts activos, puertos abiertos, etc.:

```bash
nmap -sP 192.168.1.0/24

```

### 3. **Detección de Cambios en Archivos:**

Usa scripts para monitorear cambios en archivos críticos o configuraciones:

```bash
MD5_INICIAL=$(md5sum archivo_importante)
while true; do
  MD5_ACTUAL=$(md5sum archivo_importante)
  if [ "$MD5_INICIAL" != "$MD5_ACTUAL" ]; then
    echo "¡Alerta! El archivo ha cambiado."
    # Realizar acciones de respuesta a incidentes
    break
  fi
  sleep 60  # Comprobar cada minuto
done

```

### 4. **Escaneo de Vulnerabilidades:**

Integra herramientas de escaneo de vulnerabilidades y analiza los resultados:

```bash
nmap --script vuln 192.168.1.1

```

### 5. **Auditorías de Configuración:**

Automatiza auditorías de configuración para asegurar que los sistemas cumplen con las políticas de seguridad:

```bash
auditctl -w /etc/passwd -p wa

```

### 6. **Detección de Rootkits:**

Realiza chequeos regulares en busca de rootkits utilizando herramientas como `rkhunter` o `chkrootkit`:

```bash
rkhunter --check

```

### 7. **Recopilación de Información del Sistema:**

Automatiza la recopilación de información del sistema para análisis posterior:

```bash
echo "Información del Sistema:" > informacion.txt
uname -a >> informacion.txt
cat /etc/passwd >> informacion.txt

```

### 8. **Respuesta a Incidentes:**

Desarrolla scripts para ayudar en la respuesta a incidentes, como bloquear direcciones IP sospechosas o realizar copias de seguridad:

```bash
iptables -A INPUT -s IP_SOSPECHOSA -j DROP

```

### 9. **Generación de Contraseñas Seguras:**

Crea scripts que generen contraseñas seguras automáticamente:

```bash
openssl rand -base64 12

```

### 10. **Encriptación de Archivos:**

Automatiza la encriptación y desencriptación de archivos importantes:

```bash
# Encriptar
gpg -c archivo_secreto.txt

# Desencriptar
gpg archivo_secreto.txt.gpg

```

### 11. **Validación de Firma Digital:**

Usa scripts para verificar la integridad y autenticidad de archivos con firma digital:

```bash
gpg --verify archivo_firmado.sig archivo_original

```

### 12. **Escritura Segura de Scripts:**

Cuando escribes scripts para tareas de ciberseguridad, asegúrate de seguir prácticas seguras de codificación y evita vulnerabilidades comunes.

---

## Bash POO

Bash no es un lenguaje de programación orientado a objetos (POO) en el sentido tradicional. Sin embargo, es posible emular ciertos conceptos de la programación orientada a objetos utilizando funciones y variables en Bash. 

### 1. **Funciones como Métodos:**

En lugar de métodos, usamos funciones. Podemos organizar funciones relacionadas en un script y llamarlas según sea necesario.

```bash
# Definición de una "clase" (grupo de funciones relacionadas)
Persona() {
  nombre=""
  edad=0
}

# "Constructor" para inicializar un objeto
crear_persona() {
  local persona
  persona=$(Persona)
  echo "$persona"
}

# "Método" para establecer el nombre
set_nombre() {
  local objeto=$1
  local nuevo_nombre=$2
  eval "$objeto.nombre=\\"$nuevo_nombre\\""
}

# "Método" para obtener el nombre
get_nombre() {
  local objeto=$1
  eval "echo \\$$objeto.nombre"
}

# Uso de la "clase"
persona1=$(crear_persona)
set_nombre "$persona1" "Juan"
echo "Nombre: $(get_nombre "$persona1")"

```

### 2. **Propiedades de Objeto usando Variables:**

Usamos variables para simular propiedades de un objeto.

```bash
# Definición de una "clase"
Coche() {
  color=""
  velocidad=0
}

# Crear instancia de la "clase"
mi_coche=$(Coche)

# Establecer propiedades
mi_coche.color="Rojo"
mi_coche.velocidad=60

# Acceder a propiedades
echo "Color: ${mi_coche.color}, Velocidad: ${mi_coche.velocidad} km/h"

```

### 3. **Herencia (Simulada):**

Podemos simular la herencia mediante la reutilización de funciones.

```bash
# "Clase" base
Animal() {
  nombre=""
  sonido=""
}

# "Clase" derivada
Perro() {
  Animal
  raza=""
}

# Crear instancia de la "clase" derivada
mi_perro=$(Perro)

# Establecer propiedades
mi_perro.nombre="Fido"
mi_perro.sonido="Guau"
mi_perro.raza="Labrador"

# Acceder a propiedades
echo "Nombre: ${mi_perro.nombre}, Sonido: ${mi_perro.sonido}, Raza: ${mi_perro.raza}"

```

### 4. **Encapsulación (Simulada):**

Usamos convenciones de nomenclatura para simular encapsulación.

```bash
# "Clase"
CuentaBancaria() {
  _saldo=0  # Convención: el guion bajo indica encapsulación
}

# "Método" para obtener el saldo
get_saldo() {
  local objeto=$1
  eval "echo \\$$objeto._saldo"
}

# "Método" para depositar dinero
depositar() {
  local objeto=$1
  local cantidad=$2
  eval "$objeto._saldo=$(( $objeto._saldo + cantidad ))"
}

# Uso de la "clase"
mi_cuenta=$(CuentaBancaria)
depositar "$mi_cuenta" 100
echo "Saldo actual: $(get_saldo "$mi_cuenta")"

```

### 5. **Polimorfismo (Simulado):**

Puedes simular polimorfismo permitiendo que funciones actúen de manera diferente según los parámetros que reciben.

```bash
# "Clase" base
Figura() {
  dibujar() {
    echo "Dibujando una figura."
  }
}

# "Clase" derivada
Circulo() {
  Figura
  radio=0

  dibujar() {
    echo "Dibujando un círculo con radio $radio."
  }
}

# "Clase" derivada
Rectangulo() {
  Figura
  ancho=0
  altura=0

  dibujar() {
    echo "Dibujando un rectángulo de $ancho x $altura."
  }
}

# Función polimórfica
dibujar_figura() {
  local figura=$1
  $figura.dibujar
}

# Uso del "polimorfismo"
mi_circulo=$(Circulo)
mi_rectangulo=$(Rectangulo)

dibujar_figura "$mi_circulo"
dibujar_figura "$mi_rectangulo"

```

### 6. **Interfaces (Simuladas):**

Aunque Bash no admite interfaces como en lenguajes orientados a objetos, puedes simular interfaces utilizando convenciones de nombres.

```bash
# "Interfaz"
InterfazImprimible() {
  imprimir() {
    echo "Imprimiendo desde la interfaz."
  }
}

# "Clase" que implementa la "interfaz"
ClaseImplementadora() {
  InterfazImprimible
}

# Uso de la "interfaz"
objeto_implementador=$(ClaseImplementadora)
objeto_implementador.imprimir

```

### 7. **Manejo de Errores (Simulado):**

Puedes simular el manejo de errores usando funciones de retorno y códigos de error.

```bash
# "Clase"
Calculadora() {
  sumar() {
    local resultado=$(( $1 + $2 ))
    echo $resultado
  }

  restar() {
    local resultado=$(( $1 - $2 ))
    echo $resultado
  }
}

# Uso de la "clase" con manejo de errores simulado
mi_calculadora=$(Calculadora)

resultado_suma=$(mi_calculadora.sumar 5 3) || { echo "Error al sumar."; exit 1; }
resultado_resta=$(mi_calculadora.restar 5 "a") || { echo "Error al restar."; exit 1; }

echo "Resultado de la suma: $resultado_suma"
echo "Resultado de la resta: $resultado_resta"

```

---

## Mas Conceptos

### 1. **Subshells:**

Un subshell es un nuevo proceso de shell creado dentro de un shell existente. Puedes ejecutar comandos en un subshell utilizando paréntesis `( )` o con la palabra clave `$( )`. Los cambios realizados en un subshell no afectan al shell principal.

Ejemplo:

```bash
# Subshell con paréntesis
( comandos )

# Subshell con $()
variable=$(comando)

```

### 2. **Procesos en Segundo Plano:**

Puedes ejecutar comandos en segundo plano agregando un `&` al final del comando. Esto permite que el shell principal continúe ejecutando otros comandos mientras el comando en segundo plano se ejecuta.

Ejemplo:

```bash
comando_en_segundo_plano &

```

### 3. **Variables de Entorno:**

Las variables de entorno son variables que están disponibles para todos los procesos hijos de un shell. Puedes establecerlas usando `export` y acceder a ellas en otros scripts o sesiones de la shell.

Ejemplo:

```bash
export MI_VARIABLE="Mi Valor"

```

### 4. **Comodines (Wildcards):**

Los comodines son caracteres especiales que se utilizan para hacer coincidir archivos o nombres de directorios. Algunos comodines comunes son `*` (coincide con cualquier cadena de caracteres) y `?` (coincide con un solo carácter).

Ejemplo:

```bash
ls *.txt   # Lista todos los archivos con extensión .txt

```

### 5. **Expansión de Comandos:**

La expansión de comandos permite utilizar la salida de un comando como argumento para otro comando. Puedes hacer esto utilizando comillas invertidas `` o `$()`.

Ejemplo:

```bash
resultado=$(comando)

```

### 6. **Heredoc:**

Heredoc (documentos aquí) te permite insertar bloques de texto directamente en un script de shell. Es útil para la entrada multilinea o la creación de archivos de texto.

Ejemplo:

```bash
cat <<EOF
Texto
multilinea
EOF

```

### 7. **Variables Especiales:**

La shell proporciona varias variables especiales, como `$0` (nombre del script), `$1`, `$2`, ... (parámetros posicionales), `$#` (número de parámetros), `$?` (estado de salida del último comando), etc.

Ejemplo:

```bash
echo "Nombre del script: $0"

```

### 8. **Ejecución Condicional con `&&` y `||`:**

Puedes ejecutar comandos condicionalmente utilizando `&&` (AND lógico) y `||` (OR lógico). El comando después de `&&` se ejecuta solo si el comando anterior tiene éxito, mientras que el comando después de `||` se ejecuta solo si el comando anterior falla.

Ejemplo:

```bash
comando_exitoso && echo "Éxito" || echo "Fallo"

```

### 9. **Manipulación de Archivos:**

Bash proporciona potentes comandos para manipular archivos. Puedes realizar operaciones como copiar, mover, renombrar y eliminar archivos.

```bash
# Copiar un archivo
cp archivo.txt destino/

# Mover un archivo
mv archivo.txt nuevo_directorio/

# Renombrar un archivo
mv antiguo_nombre.txt nuevo_nombre.txt

# Eliminar un archivo
rm archivo.txt

```

### 10. **Procesos en Segundo Plano:**

Puedes ejecutar comandos en segundo plano para liberar la terminal.

```bash
# Ejecutar un comando en segundo plano
comando_en_segundo_plano &

# Ver los procesos en ejecución
jobs

# Detener un proceso en segundo plano
kill %1  # Donde 1 es el número de trabajo mostrado por "jobs"

```

### 11. **Variables Especiales:**

Bash tiene variables especiales que almacenan información sobre la ejecución del script.

```bash
# Obtener el PID (Identificador de Proceso) del script
echo "El PID del script es $$"

# Obtener el número de argumentos pasados al script
echo "Número de argumentos: $#"

# Obtener los argumentos del script
echo "Argumentos del script: $@"

```

### 12. **Manipulación de Strings:**

Bash proporciona varias formas de manipular cadenas de texto.

```bash
# Longitud de una cadena
cadena="Hola, mundo"
echo "La longitud de la cadena es ${#cadena}"

# Extracción de subcadena
subcadena=${cadena:0:4}
echo "La subcadena es $subcadena"

# Reemplazar parte de una cadena
nueva_cadena=${cadena/Hola/Adiós}
echo "La nueva cadena es $nueva_cadena"

```

### 13. **Compresión y Descompresión:**

Bash es compatible con varias utilidades para comprimir y descomprimir archivos.

```bash
# Comprimir un archivo
tar -czvf archivo.tar.gz archivo/

# Descomprimir un archivo
tar -xzvf archivo.tar.gz -C destino/

```

### 14. **Manejo de Señales:**

Puedes capturar y manejar señales enviadas al script.

```bash
trap 'echo "Señal recibida. Saliendo."' SIGINT

# Bucle infinito para esperar señales
while true; do
  sleep 1
done

```

### 15. **Lectura Segura de Contraseñas:**

Lee contraseñas sin mostrarlas en la pantalla.

```bash
echo -n "Ingrese su contraseña: "
read -s contrasena
echo "Contraseña ingresada."

```

### 16. **Creación de Funciones con Parámetros Opcionales:**

Permite funciones con parámetros opcionales utilizando valores predeterminados.

```bash
funcion_con_parametro() {
  parametro=${1:-"Valor Predeterminado"}
  echo "El parámetro es: $parametro"
}

funcion_con_parametro          # Utiliza el valor predeterminado
funcion_con_parametro "Nuevo"  # Utiliza el valor proporcionado

```

### 17. **Ejecución Condicional:**

Ejecuta un comando solo si otro comando tuvo éxito.

```bash
comando1 && echo "El comando1 tuvo éxito" || echo "El comando1 falló"

```

### 18. **Expansión Aritmética:**

Realiza operaciones matemáticas directamente en la línea de comandos.

```bash
resultado=$((5 + 3))
echo "El resultado de la suma es $resultado"

```

### 19. **Instalación Condicional de Paquetes:**

Puedes verificar si un paquete está instalado antes de usarlo.

```bash
# Verificar si curl está instalado
if command -v curl &> /dev/null; then
  echo "curl está instalado"
else
  echo "curl no está instalado"
fi

```

### 20. **Uso de `trap` para Limpieza al Salir:**

`trap` permite ejecutar comandos antes de salir del script, útil para la limpieza.

```bash
limpiar() {
  echo "Limpiando antes de salir..."
  # Agregar comandos de limpieza aquí
}

trap limpiar EXIT

```

---

## Palabras Reservadas

Las palabras reservadas son aquellas que tienen un significado especial para la shell. Se utilizan para comenzar y finalizar los comandos compuestos de la shell.

Las siguientes palabras son reconocidas como reservadas cuando no están entre comillas y son la primera palabra de un comando (ver excepciones abajo):

```bash
if then elif else fi time
for in until while do done
case esac coproc select function
{ } [[ ]] !

```

`in` se reconoce como una palabra reservada si es la tercera palabra de un comando `case` o `select`. `in` y `do` se reconocen como palabras reservadas si son la tercera palabra en un comando `for`.

---

## Funciones en la Shell

Las funciones en la shell permiten agrupar comandos bajo un nombre único para su ejecución posterior. Se declaran de la siguiente manera:

```bash
nombre_funcion () {
  comandos
}

```

o

```bash
function nombre_funcion {
  comandos
}

```

Al ejecutar `nombre_funcion` como un comando, se ejecutan los comandos asociados. Las funciones se ejecutan en el contexto actual de la shell, sin crear un nuevo proceso.

Cuando una función se ejecuta, los argumentos se convierten en parámetros posicionales y el parámetro especial `#` se actualiza. El estado de salida de la función es el estado del último comando ejecutado en su cuerpo.

Las variables locales se pueden declarar con `local`. Estas son visibles solo para la función y las funciones que llama. Cuando una función se completa, las variables locales desaparecen y los valores anteriores se restauran.

```bash
funcion_ejemplo() {
  local variable_local="Hola"
  echo $variable_local
}

funcion_ejemplo  # Salida: Hola

```

Las funciones pueden ser recursivas, y la variable `FUNCNEST` limita la profundidad de la pila de llamadas. `return` finaliza una función y permite la ejecución continua después de la llamada.

```bash
funcion_recursiva() {
  if [ $1 -eq 0 ]; then
    return
  fi
  echo $1
  funcion_recursiva $(( $1 - 1 ))
}

funcion_recursiva 3  # Salida: 3 2 1

```

En resumen, las funciones son una herramienta poderosa para organizar y reutilizar código en la shell.