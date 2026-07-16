# Inicio
## Instalación del primer Servidor Linux
En primera instancia, se debió instalar desde cero un servidor Linux. Se optó por dos opciones básicas, orietandas a servidores en entornos corporativos: Ubuntu Server y AlmaLinux.

En la instalación de la primera opción elegida, tuve el primer traspié. Utilizando Hyper-V, levanté la virtual con los parámetros de configuración estándar y como VM de Gen 2.
El primer inconveniente no era posible iniciar la máquina virtual, sólo quedaba el logo del hipervisor con un fondo negro y, tras varios minutos sin hacer nada, arrojaba la siguiente pantalla.

<img width="400" height="300" alt="hyperv-error" src="https://github.com/user-attachments/assets/e31f003d-3da8-473f-b8ff-a66ed1690804" />

### Troubleshooting
Tras una breve investigación, la respuesta salió fácil a la luz en internet. El problema era que tenía activado el modo de inicio seguro en la configuración de la VM.
Al desactivar por completo el Secure Boot, la máquina inició y pude realizar la instalación sin inconvenientes, pero algo me decía que no era lo correcto. Investigando más a fondo,
entendí que el modo Arranque Seguro está para verificar la veracidad del fabricante que emite ese bootloader (para el caso de Ubuntu Server, es **shimx64.efi**).
La cadena de certificación se es:

`Shim -> GRUB -> Kernel Linux -> SO`

Si bien Ubuntu ha trabajado con Microsoft para que la firma del bootloader sea tomada como válida, tenía configurado por defecto la Plantilla de arranque seguro para Microsoft Windows. Es por esto, que no se reconocía la firma.
Al cambiar a "Entidad de certificación UEFI de Microsoft", la VM arrancó sin ningún problema.

---

## Comenzando con las tareas
Como primer paso, se ejecutó `sudo apt update` seguido de `sudo apt upgrade`. Por último, `sudo reboot`. Esta es una de las buenas prácticas más recomendadas después de instalar cualquier distribución Linux.

La principal razón es que la imagen ISO representa el estado del sistema en el momento en que fue creada. Con el paso del tiempo, los desarrolladores publican actualizaciones que corrigen errores, solucionan vulnerabilidades de seguridad y mejoran el funcionamiento de los paquetes incluidos originalmente en esa imagen. Al actualizar el sistema, se incorporan todas esas mejoras antes de comenzar a utilizar el servidor.

Otro motivo importante es la resolución de dependencias. Mantener el sistema actualizado facilita la instalación de nuevas aplicaciones, ya que el gestor de paquetes puede resolver sus dependencias utilizando versiones recientes y compatibles de las bibliotecas del sistema. En cambio, si un servidor permanece mucho tiempo sin actualizar, es más probable que durante la instalación de nuevos paquetes sea necesario actualizar una gran cantidad de dependencias, aumentando la complejidad del proceso y la posibilidad de encontrar conflictos entre versiones. Además, ante la aparición de una vulnerabilidad crítica, un sistema que recibe actualizaciones periódicas podrá aplicar el parche correspondiente de forma mucho más rápida y con un menor impacto sobre el resto del software instalado.

## Ejercicios
- Crear un directorio de trabajo personal dentro de tu home
    - Se crea con el comando `mkdir` un nuevo directorio llamado "workspace" dentro del directorio del usuario creado en la instalación del servidor (`/home/sysadmin/`)
- Explorar `/`, `/home`, `/etc`, `/var`, `/usr`
    - Respecto a los directorios que se pide investigar (`/`, `/home`, `/etc`, `/var`, `/usr`), se hace una explicación con palabras propias en la documentaicón del respositorio <link>
- Crear un archivo de documentación inicial
    - Se crea con el comando `touch` el archivo "documentación-inicial.md" dentro de `/home/sysadmin/workspace/`
- Identificar dónde se almacenan configuraciones, logs y datos de usuarios
    - Las configuraciones de herramientas se guardan en `/etc`. Los logs, se guardan en `/var/log`. Los datos de usuarios, se guardan en `/home/<user>` (en este caso, sería `/home/sysadmin`). No ahondaré en detalles en esta respuesta porque las explicaciones
      se encontrarán en la carpeta de documentación.


## Lo realizado

### Checkpoint

- [X]  Creé mi espacio de trabajo
- [X]  Exploré los directorios principales
- [ ]  Documenté qué función cumple cada directorio
- [X]  Identifiqué dónde viven los logs
- [X]  Identifiqué dónde viven las configuraciones







