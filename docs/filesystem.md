# File System Standar
Existe un estándar para organizar los archivos en el filesystem de Linux: FHS (File System Hierarchy). Esto vuelve al Linux un sistema más predecible basando en consistencia, lo que lo hace
más fácil de mantener y trabajar, en general, sobre él.

# Directorios
**Todo** en Linux es un archivo. Esta premisa es importante porque no existen ejecutables como en Windows. Su equivalente en Linux sería un archivo con extensión `.sh`, que no es ni más ni menos
que un script de bash con permisos de ejecución.
El directorio raíz (`/`) contiene todos los demás directorios con sus respectivas funciones:

`/etc`: Se guardan configuraciones de las herramientas.
`/var`: Este directorio contiene archivos dinámicos como logs de aplicaciones (`/var/log`), caché (`/var/cache`)
`/usr`:
`/tmp`: Se guardan los archivos temporales (equivalentes a %temp% en Windows). Estos archivos se guardan en memoria y se eliminan cuando se apaga el equipo. Pueden ser generados por las propias
aplicaciones, o bien, por el usuario.
`/home`: Contiene todos los datos de los usuarios que existan en el sistema, cada uno con su respectivo directorio.
`/bin`: Se almacenan los ejecutables propios del sistema, como por ejemplo, `ls`, `nano`, `cat`, `mv`, `cp`, etc. En versiones modernas de Linux, existe un symlink de `/bin` a `/usr/bin` (`/bin -> /usr/bin`)
`/sbin`: Guarda ejecutables propios del sistema, pero que en su mayoría sólo pueden (o deberían) ser ejecutados por el usuario `root`
