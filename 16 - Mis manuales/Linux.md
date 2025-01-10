# Linux

Creado: 13 de octubre de 2023 20:14

1. `ls` (List):
    - Descripción: Este comando se utiliza para listar los archivos y directorios en el directorio actual.
    - Uso: Simplemente escribe `ls` en la terminal para listar el contenido del directorio actual. Puedes agregar opciones, como `l` para obtener una lista detallada o `a` para mostrar archivos ocultos.
2. `cd` (Change Directory):
    - Descripción: Cambia el directorio actual al directorio especificado.
    - Uso: Ejecuta `cd` seguido de la ruta del directorio al que deseas cambiar. Por ejemplo, `cd /ruta/al/directorio` te llevará a ese directorio.
3. `pwd` (Print Working Directory):
    - Descripción: Muestra la ruta completa del directorio actual.
    - Uso: Simplemente ejecuta `pwd`, y te mostrará la ubicación actual en la estructura de directorios.
4. `mkdir` (Make Directory):
    - Descripción: Crea un nuevo directorio en la ubicación especificada.
    - Uso: Ejecuta `mkdir` seguido del nombre del nuevo directorio. Por ejemplo, `mkdir nombre_del_directorio` creará un directorio con ese nombre en el directorio actual.
5. `rmdir` (Remove Directory):
    - Descripción: Elimina un directorio vacío.
    - Uso: Ejecuta `rmdir` seguido del nombre del directorio que deseas eliminar. Ten en cuenta que solo puedes eliminar directorios vacíos con este comando.
6. `rm` (Remove):
    - Descripción: Elimina archivos o directorios.
    - Uso: Para eliminar un archivo, ejecuta `rm` seguido del nombre del archivo. Para eliminar un directorio y su contenido, usa la opción `r` (recursivo). Por ejemplo, `rm archivo.txt` eliminará el archivo y `rm -r directorio` eliminará un directorio y todo su contenido.
7. `cp` (Copy):
    - Descripción: Copia archivos o directorios.
    - Uso: Ejecuta `cp` seguido del nombre del archivo o directorio que deseas copiar y la ubicación de destino. Por ejemplo, `cp archivo.txt destino/` copiará el archivo en el directorio de destino.
8. `mv` (Move):
    - Descripción: Mueve o renombra archivos y directorios.
    - Uso: Ejecuta `mv` seguido del nombre del archivo o directorio que deseas mover y la ubicación de destino. También puedes utilizarlo para renombrar archivos al especificar un nuevo nombre en lugar de una ubicación.
9. `touch`:
    - Descripción: Crea un archivo vacío con el nombre especificado.
    - Uso: Simplemente ejecuta `touch` seguido del nombre del archivo que deseas crear. Por ejemplo, `touch nuevo_archivo.txt` creará un archivo vacío llamado "nuevo_archivo.txt".
    1. `cat` (Concatenate):
    - Descripción: Muestra el contenido de uno o varios archivos en la terminal.
    - Uso: Simplemente ejecuta `cat` seguido de uno o varios nombres de archivos. Por ejemplo, `cat archivo.txt` mostrará el contenido del archivo en la terminal.
    1. `less` y `more`:
    - Descripción: Estos comandos permiten ver archivos de texto página por página, lo que es útil para visualizar archivos extensos.
    - Uso: Ejecuta `less nombre_de_archivo` o `more nombre_de_archivo`. Luego, puedes desplazarte hacia arriba o abajo utilizando las teclas de flecha o la barra espaciadora. Para salir, presiona la tecla "q".
    1. `grep` (Global Regular Expression Print):
    - Descripción: Busca patrones en un archivo de texto y muestra las líneas que coinciden con esos patrones.
    - Uso: Ejecuta `grep patrón archivo` para buscar un patrón específico en un archivo. Por ejemplo, `grep "palabra_a_buscar" archivo.txt` mostrará todas las líneas que contienen "palabra_a_buscar" en el archivo.
    1. `echo`:
    - Descripción: Muestra texto en la pantalla o redirige texto a un archivo.
    - Uso: Simplemente ejecuta `echo "texto"` seguido del texto que deseas mostrar en la pantalla. Puedes redirigir la salida a un archivo con `echo "texto" > archivo.txt`.
    1. `man` (Manual):
    - Descripción: Muestra el manual o documentación de un comando específico.
    - Uso: Ejecuta `man nombre_de_comando` para obtener información detallada sobre cómo usar ese comando. Por ejemplo, `man ls` proporcionará el manual del comando `ls`.
    1. `chmod` (Change Mode):
    - Descripción: Cambia los permisos de archivos y directorios, permitiendo o denegando el acceso a usuarios y grupos.
    - Uso: Utiliza `chmod` seguido de la notación octal (por ejemplo, `chmod 755 archivo.txt`) o la notación simbólica (por ejemplo, `chmod u+r archivo.txt`) para cambiar los permisos.
    1. `chown` (Change Owner):
    - Descripción: Cambia el propietario de archivos y directorios.
    - Uso: Ejecuta `chown nuevo_propietario archivo` para cambiar el propietario de un archivo. Por ejemplo, `chown nuevo_usuario archivo.txt` cambiará el propietario del archivo.
    1. `ps` (Process Status):
    - Descripción: Muestra información sobre los procesos en ejecución en el sistema.
    - Uso: Ejecuta `ps` para obtener una lista de procesos en ejecución. Puedes usar diferentes opciones para personalizar la salida, como `ps aux` para obtener información más detallada.
    1. `kill`:
    - Descripción: Detiene un proceso en ejecución enviándole una señal de terminación.
    - Uso: Ejecuta `kill ID_de_proceso` para detener un proceso específico. El ID de proceso se obtiene a través de `ps` u otros comandos.
    1. `find`:
    - Descripción: Busca archivos y directorios en una jerarquía de directorios.
    - Uso: `find` seguido de la ruta de inicio y opciones de búsqueda. Por ejemplo, `find /ruta/inicial -name "*.txt"` buscará archivos con extensión `.txt` en el directorio especificado.
    1. `tar` (Tape Archive):
    - Descripción: Permite la compresión y extracción de archivos y directorios en archivos de respaldo.
    - Uso: `tar` seguido de opciones como `cvzf` para crear un archivo tar comprimido y `xvf` para extraerlo. Por ejemplo, `tar -czvf archivo.tar.gz directorio/` comprimirá un directorio en un archivo tar.gz.
    1. `cpio` (Copy In and Out):
    - Descripción: Permite copiar archivos a y desde archivos cpio, que son otro formato de archivo de respaldo.
    - Uso: Puedes crear un archivo cpio con `find` y luego copiar archivos en él con `cpio`. Por ejemplo, `find /ruta/inicial -type f | cpio -ov > archivo.cpio` crea un archivo cpio a partir de una lista de archivos.
    1. `dd` (Data Description):
    - Descripción: Copia y convierte archivos y bloques de datos.
    - Uso: Es útil para crear imágenes de discos o copiar datos de un lugar a otro. Por ejemplo, `dd if=/dev/sda of=imagen_de_disco.img` copiará el contenido de `/dev/sda` a un archivo de imagen de disco.
    1. `ssh` (Secure Shell):
    - Descripción: Permite acceder de forma segura a otros sistemas a través de una conexión SSH.
    - Uso: `ssh usuario@servidor` establece una conexión SSH con un servidor remoto. Luego, se te pedirá que ingreses la contraseña o utilices autenticación mediante clave.
    1. `scp` (Secure Copy):
    - Descripción: Copia archivos de forma segura entre sistemas locales y remotos a través de SSH.
    - Uso: `scp origen usuario@servidor:destino` copiará un archivo desde el sistema local al sistema remoto a través de SSH.
    1. `rsync`:
    - Descripción: Sincroniza archivos y directorios de forma eficiente entre sistemas locales y remotos.
    - Uso: `rsync opciones origen destino` permite realizar copias incrementales y sincronización de datos entre sistemas.
    1. `wget`:
    - Descripción: Descarga archivos desde la web a través de HTTP, HTTPS o FTP.
    - Uso: `wget URL` descargará el archivo especificado en la URL a tu sistema local.
    1. `curl`:
    - Descripción: Permite realizar solicitudes HTTP y mostrar la respuesta en la terminal.
    - Uso: `curl URL` obtendrá el contenido de la URL y lo mostrará en la terminal.
    1. `top`:
    - Descripción: Muestra una lista en tiempo real de los procesos en ejecución y su uso de recursos.
    - Uso: Simplemente ejecuta `top` en la terminal para ver una lista actualizada de procesos. Puedes utilizar atajos de teclado para realizar acciones, como matar procesos.

**Comandos de superusuario:**

1. `su` (Switch User):
    - Descripción: Permite cambiar al usuario superusuario (root) o a otro usuario.
    - Uso: Para cambiar al superusuario, ejecuta `su` y proporciona la contraseña de root. Para cambiar a otro usuario, ejecuta `su nombre_de_usuario`.
2. `sudo` (Superuser Do):
    - Descripción: Permite a un usuario común ejecutar comandos con permisos de superusuario.
    - Uso: Antepon el comando que deseas ejecutar con `sudo`. Por ejemplo, `sudo apt-get update` actualizará el sistema utilizando `apt`.

**Comandos de instalación y desinstalación de paquetes:**

1. `apt` (Advanced Package Tool):
    - Descripción: Utilizado en sistemas basados en Debian (como Ubuntu) para gestionar paquetes.
    - Uso:
        - `apt update`: Actualiza la lista de paquetes.
        - `apt install nombre_del_paquete`: Instala un paquete.
        - `apt remove nombre_del_paquete`: Desinstala un paquete.
        - `apt search término_de_búsqueda`: Busca paquetes.
2. `yum`:
    - Descripción: Utilizado en sistemas basados en Red Hat (como CentOS) para gestionar paquetes.
    - Uso:
        - `yum update`: Actualiza los paquetes.
        - `yum install nombre_del_paquete`: Instala un paquete.
        - `yum remove nombre_del_paquete`: Desinstala un paquete.
        - `yum search término_de_búsqueda`: Busca paquetes.
3. `dpkg` (Debian Package):
    - Descripción: Utilizado en sistemas basados en Debian para trabajar con paquetes de manera más directa.
    - Uso:
        - `dpkg -i paquete.deb`: Instala un paquete desde un archivo .deb.
        - `dpkg -r nombre_del_paquete`: Desinstala un paquete.
        - `dpkg -l`: Lista todos los paquetes instalados.

**Comandos de procesos generales:**

1. `ps` (Process Status):
    - Descripción: Muestra información sobre los procesos en ejecución.
    - Uso:
        - `ps`: Muestra los procesos del usuario actual.
        - `ps aux`: Muestra una lista detallada de todos los procesos en el sistema.
2. `kill`:
    - Descripción: Detiene procesos en ejecución.
    - Uso: Usa `kill` seguido del ID de proceso (PID) para detener un proceso. Por ejemplo, `kill PID` detendrá el proceso con ese PID.
3. `top`:
    - Descripción: Muestra una lista en tiempo real de los procesos y su uso de recursos.
    - Uso: Simplemente ejecuta `top` en la terminal para ver una lista actualizada de procesos. Puedes utilizar atajos de teclado para realizar acciones, como matar procesos.
4. `htop`:
    - Descripción: Una alternativa más avanzada a `top` con una interfaz de usuario más amigable.
    - Uso: Ejecuta `htop` en la terminal para obtener una vista en tiempo real de los procesos.